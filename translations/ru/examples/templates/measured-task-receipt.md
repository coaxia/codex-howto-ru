# Отчёт об измеренной задаче

Создавайте один отчёт для каждого измеренного запуска агента.
До начала задайте условия и бюджеты, после — заполните результат наблюдаемыми
подтверждениями. Недоступные необязательные значения оставляйте пустыми.
Поля YAML сохраняются для совместимости с исходной методикой.

```yaml
task:
  id:
  class:
  starting_commit:
  goal:
  in_scope: []
  out_of_scope: []
  planned_paths: []
  acceptance_checks: []
  judge:
  success_predicate:

run:
  profile:
  workflow_components: []
  workflow_revisions: []
  codex_surface:
  model:
  reasoning_effort:
  sandbox:
  tool_profile:

budgets:
  elapsed_seconds:
  total_tokens:
  retries:
  iterations:
  scope_expansions:
  human_checkpoints:

outcome:
  accepted:
  evidence_complete:
  regression_before_fix:
  focused_checks_passed:
  required_checks_passed:
  files_read:
  files_changed:
  unexpected_files_changed:
  scope_expansions:
  retries:
  iterations_to_green:
  first_judge_passed:
  human_corrections:
  human_checkpoints:
  elapsed_seconds:
  total_tokens:
  total_cost_usd:

evidence:
  baseline:
  last_judge:
  focused_checks: []
  required_checks: []
  review:
  unverified: []

decision:
  verdict: # keep, simplify, specialize, remove, or unresolved
  reason:
  repeat_on: []
```

## Правила подсчёта

- `unexpected_files_changed`: изменённые файлы вне согласованной области,
  кроме явно названных в условиях задачи файлов, генерируемых репозиторием.
- `scope_expansions`: согласованные изменения исходных путей, подсистем,
  критериев приёмки или внешних систем в области задачи.
- `retries`: повторные попытки, не дающие новых подтверждений.
- `iterations`: изменения репозитория с последующим заранее заданным оценщиком.
  Исходное воспроизведение не учитывается; временные диагностические изменения учитываются.
- `iterations_to_green`: ограниченные циклы build-judge до первой приёмки.
  Оставьте пустым, если запуск так и не прошёл.
- `first_judge_passed`: true, только если первый заданный оценщик выполнил
  условие успеха без ещё одной правки кода.
- `human_corrections`: вмешательства, меняющие код, тесты, требования или следующее техническое действие.
- `human_checkpoints`: обязательные согласования дизайна, области, разрешений и интеграции.
- `total_tokens`: все участвующие агенты и потоки ревью, если интерфейс их показывает.

Зафиксируйте правила подсчёта до сравнения. Отчёт — проверяемая запись запуска,
а не универсальная оценка производительности.

Для остановленного или возобновлённого запуска добавьте компактную контрольную
точку в `evidence`: подтверждённые факты, опровергнутые гипотезы, текущий diff,
остаток бюджета и следующий шаг, дающий подтверждения. Не копируйте весь диалог.

## Необязательное независимое ревью

Если участвует отдельный ревьюер, добавьте этот раздел. Одна запись на попытку,
включая упавшие или остановленные до заключения:

```yaml
independent_review:
  attempts:
    - reviewer_id:
      model:
      context_separation: # fresh, inherited, or unknown
      base_revision:
      reviewed_revision:
      status: # completed, failed, or stopped
      findings:
        - id:
          disposition: # confirmed, rejected, duplicate, or unresolved
          validated_by: # builder, test, human, or unresolved
          evidence:
      elapsed_seconds:
      total_tokens:
      total_cost_usd:
      human_adjudication_seconds:
  final_candidate_revision:
  last_reviewed_revision:
  uncovered_changes: []
```

Пустой `findings` означает отсутствие записанных замечаний; сначала проверьте
`status`. Ноль записывайте только при наблюдении, недоступные числовые значения
оставляйте пустыми. Запрошенный навык или роль не подтверждают выполнение ревью.

Токены и стоимость ревью входят в общий `outcome`, их нельзя повторно прибавлять.
Длительности параллельных ревью не суммируются во время задачи.
Неполное покрытие телеметрией укажите в `evidence.unverified`;
не представляйте известную часть как полный итог.

Равенства ревизий недостаточно при изменённом рабочем дереве.
Для ревью незакоммиченных правок записывайте неизменяемый ID снимка.
Любая последующая правка делает прежние подтверждения ревью устаревшими для кандидата.
