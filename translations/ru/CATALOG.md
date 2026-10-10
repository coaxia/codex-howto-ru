# Каталог

## Учебные модули

| Модуль | Основной результат |
|---|---|
| [00 · Модель работы](modules/00-mental-model/README.md) | Выбор интерфейса и формы задачи |
| [01 · Песочница и согласования](modules/01-sandbox-and-approvals/README.md) | Режимы разрешений с учётом риска |
| [02 · CLI и интерфейсы](modules/02-cli-and-surfaces/README.md) | Чек-лист безопасного первого сеанса |
| [03 · Запросы и планы](modules/03-prompts-and-plans/README.md) | Условия задачи из четырёх частей |
| [04 · AGENTS.md](modules/04-agents-md/README.md) | Корневые и вложенные инструкции |
| [05 · Инженерные навыки](modules/05-engineering-skills/README.md) | Структура и установка навыка |
| [06 · MCP и инструменты](modules/06-mcp-and-tools/README.md) | Выбор инструмента и проверка безопасности |
| [07 · Тестирование и ревью](modules/07-testing-and-review/README.md) | Цикл проверки и ревью |
| [08 · Субагенты](modules/08-subagents/README.md) | Делегирование с чёткими границами |
| [09 · Оркестрация](modules/09-orchestration/README.md) | Протокол параллельной работы |
| [10 · Эффективность контекста](modules/10-context-and-token-efficiency/README.md) | Бюджет контекста и требования к сводкам |
| [11 · Автоматизация и плагины](modules/11-automation-plugins-hooks/README.md) | Путь от запроса к автоматизации |
| [12 · Диагностика проблем](modules/12-troubleshooting/README.md) | Послойная диагностика |
| [13 · Живая wiki Codex](modules/13-living-codex-wiki/README.md) | Обобщение знаний с предварительным ревью |

## Устанавливаемые навыки

Исполняемые навыки остаются в оригинальном каталоге:

| Навык | Включённые материалы |
|---|---|
| [engineering-loop](../../skills/engineering-loop/SKILL.md) | `references/loop-contract.md`, `references/hard-debugging.md` |
| [build-frontend](../../skills/build-frontend/SKILL.md) | `references/verification.md` |
| [build-backend](../../skills/build-backend/SKILL.md) | `references/contracts-and-data.md` |
| [operate-devops](../../skills/operate-devops/SKILL.md) | `references/change-safety.md` |
| [review-code](../../skills/review-code/SKILL.md) | `references/review-checklist.md`, `references/review-lenses.md` |
| [test-software](../../skills/test-software/SKILL.md) | `references/test-strategy.md` |
| [review-security](../../skills/review-security/SKILL.md) | `references/threat-checklist.md` |
| [orchestrate-engineering](../../skills/orchestrate-engineering/SKILL.md) | `references/context-budget.md` |
| [maintain-codex-wiki](../../skills/maintain-codex-wiki/SKILL.md) | `references/source-policy.md`, `references/article-template.md`, `scripts/wiki_lint.py` |

## Живые знания

- [Codex Living Wiki](knowledge/README.md) — модель ревью и границы операций.
- [Индекс wiki](knowledge/index.md) — навигация по темам, решениям и экспериментам.
- [Реестр источников](../../knowledge/sources.json) — происхождение без внешних текстов в Git.
- [Базовый эксперимент эффективности wiki](knowledge/experiments/wiki-efficiency-baseline.md)
  — запланированное сравнение без wiki, с запросом и с сопровождением.

## Готовые примеры

- [Начальный `AGENTS.md`](../../examples/AGENTS.md)
- [Осторожная конфигурация проекта](../../examples/config/config.toml)
- [Агент исследования](../../examples/agents/explorer.toml)
- [Агент ревью](../../examples/agents/reviewer.toml)
- [Агент тестирования](../../examples/agents/test-runner.toml)
- [Общий запрос задачи](examples/prompts/task-template.md)
- [Запрос оркестрированного ревью](examples/prompts/orchestrated-review.md)
- [Периодический поиск расхождений документации](examples/prompts/scheduled-docs-drift.md)
- [Инженерная спецификация](examples/templates/engineering-spec.md)
- [Задачи с зависимостями](examples/templates/dependency-aware-tickets.md)
- [Передача результата](examples/templates/engineering-handoff.md)
- [Отчёт об измеренной задаче](examples/templates/measured-task-receipt.md)
- [Отчёт запуска оркестрации](examples/templates/orchestration-run-receipt.md)
- [Манифест редакции](examples/templates/edition-manifest.md)
- [Записи запусков инженерного цикла](../../examples/measurements/engineering-loop-runs.csv)
- [Пробный запуск оркестрации инцидента](../../examples/measurements/incident-orchestration-smoke-2026-08-11.md)
- [Локальный marketplace плагинов](../../examples/plugin-marketplace/.agents/plugins/marketplace.json)
- [Пример Stop hook](../../examples/hooks/validate-on-stop/hooks.json)
- [Маршрутизатор с явным вызовом](../../examples/skills/choose-engineering-flow/SKILL.md)
- [Матрица решений об оркестрации](resources/orchestration-decision-matrix.md)
- [Таблица оценки эффективности токенов](resources/token-efficiency-scorecard.md)
- [Навыки с учётом модели](resources/model-adaptive-skills.md)
- [Сравнение сторонних процессов](resources/third-party-workflow-profiles.md)
- [Набор для анонса](../../resources/community-launch-kit.md)
- [Создание редакции](resources/fork-an-edition.md)
- [Проверенные каналы распространения](../../resources/distribution-shortlist.md)
- [Заметки выпуска v0.3.0](../../resources/release-notes-v0.3.0.md)
- [Заметки выпуска v0.2.0](../../resources/release-notes-v0.2.0.md)

## Практические работы

- [Инженерный практикум](labs/engineering-playground/README.md) — frontend,
  backend и deployment-пример без зависимостей с намеренно внесёнными дефектами.
- [Benchmark оркестрации реагирования на инциденты](labs/incident-response-benchmark/README.md)
  — разделяемая full-stack задача для контролируемого сравнения одного агента и оркестрации.
- [Руководство по выступлению](PRESENTING.md) — 15-минутный план, демонстрация, измерения и анонс.
- [Протокол измерения инженерного цикла](resources/engineering-loop-measurement.md)
  — сравнение трёх вариантов навыка, критерии качества, метрики и правила решений.
- [Руководство сообщества](../../COMMUNITY.md) — ответственное участие, полезные форки и стандарты.

## Официальные справочники

- [Документация Codex](https://developers.openai.com/codex)
- [Быстрый старт](https://developers.openai.com/codex/quickstart)
- [Руководство по `AGENTS.md`](https://developers.openai.com/codex/guides/agents-md)
- [Навыки](https://developers.openai.com/codex/skills)
- [Субагенты и работа нескольких агентов](https://developers.openai.com/codex/subagents)
- [MCP](https://developers.openai.com/codex/mcp)
- [Безопасность и песочница](https://developers.openai.com/codex/security)
- [Справочник конфигурации](https://developers.openai.com/codex/config-reference)
- [Hooks](https://developers.openai.com/codex/config-advanced#hooks)
- [Неинтерактивный режим](https://developers.openai.com/codex/noninteractive)
- [Рекомендации](https://developers.openai.com/codex/learn/best-practices)
