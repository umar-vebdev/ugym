# Handoff — uGym (Client App)

**Обновлено** 2026-11-20
**Текущий этап:** M0 — Фундамент проекта
**Текущая задача** `M0-01` — Flutter-каркас Android и iOS

## Что сделано в последней сессии

- Создан отдельный каталог и заготовка репозитория **uGym** (`/home/umar/ugym-mobile/uGym`).
- Перенесены спецификации:
  - `docs/specs/uGym_Mobile_TZ.md`
  - `docs/specs/uCraft_Design_System.md`
  - OpenAPI-контракты бэкенда `docs/api/*.yaml` (10 файлов)
- Настроены шаблоны управления разработкой с ИИ-агентом: `AGENTS.md`, `docs/TASKS.md`, `docs/HANDOFF.md`, `docs/DECISIONS.md`.

## Актуальное состояние окружения

- Flutter SDK и Dart SDK установлены в `/home/umar/development/flutter`.
- Android SDK и `adb` установлены в `/home/umar/Android/Sdk`.
- `java` — установлена (`/usr/bin/java`).
- Сборка iOS на текущей Linux-машине недоступна (потребуется macOS + Xcode или облачный CI позже).

## Точный следующий шаг

1. Создать каркас Flutter в существующем репозитории.
2. Подключить общий визуальный стиль Material 3 и проверить предпросмотр клиентского интерфейса.

