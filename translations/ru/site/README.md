# Codex Skill Benchmark

Интерактивный просмотр подтверждений контролируемых измерений GPT-5.6-sol
в [Phelan164/codex-howto](https://github.com/Phelan164/codex-howto).

Страница сравнивает отсутствие навыка репозитория, `engineering-loop` v0.2.0
и компактный цикл v0.4.0 на небольшой backend-правке и средней реализации 2048.
Приёмка остаётся главным критерием; представлены токены, время, повторы,
условия эксперимента и ограничения без заявления, что навыки всегда эффективнее.

## Локальная разработка

Нужен Node.js `>=22.13.0`.
Работайте в [оригинальном site/](../../../site/README.md):

```bash
npm install
npm run dev
```

Откройте локальный адрес, выведенный сервером.

## Проверки

```bash
npm run build
npm run lint
npm test
```

`npm test` собирает production worker и проверяет серверный HTML:
данные benchmark, исходную ссылку и ограничения, без артефактов starter-preview.

## Источники

- [Измерение backend](https://github.com/Phelan164/codex-howto/blob/main/examples/measurements/gpt-5.6-sol-backend-boundary-2026-07-31.md)
- [Измерение 2048](https://github.com/Phelan164/codex-howto/blob/main/examples/measurements/gpt-5.6-sol-2048-game-2026-07-31.md)
- [Запрос воспроизведений](https://github.com/Phelan164/codex-howto/issues/23)

Сайт показывает подтверждения; это не независимое воспроизведение.
