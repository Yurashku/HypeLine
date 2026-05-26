# AI Agent Handoff

Use this document to continue work on HypeLine / HypEnt with another AI agent.

## Project goal

HypeLine is a system for supporting product improvement and pilot workflows. It helps transform a raw idea into a testable hypothesis, choose metrics, collect evidence, assess hypothesis priority, interpret pilot results, and store reusable knowledge.

## Current loop

```text
сырая идея
  -> уточняющий диалог с пользователем
  -> проверяемая гипотеза
  -> набор метрик
  -> основания и аналоги
  -> оценка качества и приоритета гипотезы
  -> пилот
  -> разбор результата
  -> запись в память пилотов
  -> поддержка следующих гипотез
```

## Key decisions

- Do not restore the `Capability Block` layer unless explicitly asked.
- AI Interviewer is a separate reusable task for dialogic form filling.
- Hypothesis ranking is not limited to predicted ATE. It is a multi-criteria assessment of hypothesis quality and priority.
- Exploratory post-pilot findings are not confirmed learning.
- Targeting, segment effects, and policy evaluation on historical data are an extended research layer.

## Current task portfolio

1. ИИ-интервьюер для заполнения рабочих форм.
2. Перевод сырой идеи в проверяемую гипотезу.
3. Выбор метрик и дизайн измерения.
4. Основания, контраргументы и аналоги.
5. Оценка качества и приоритета гипотез.
6. Разбор результата пилота.
7. Память пилотов.
8. Логика повторного запуска после неоднозначного результата.
9. Таргетинг, сегментные эффекты и оценка политик на исторических данных.
10. Причинные сигналы из внешних инструментов.
11. Качество рабочих материалов и экспертное обсуждение.
12. Банк примеров.
13. Вводный пакет для внешней команды.

## Recommended next steps

1. Review `docs/research/RESEARCH_TASK_PORTFOLIO.md` before meetings with collaborators.
2. Choose which tasks belong to the first research wave.
3. Expand selected tasks into deeper briefs only after the meeting.
4. Build initial examples for the bank of cases.
5. Update `SOURCE_OF_TRUTH.md` and `DECISION_LOG.md` after new decisions.
