# uGym — чек-лист задач

**Текущий этап:** M0 — Фундамент проекта
**Статусы:** `[ ]` не начата · `[~]` в работе · `[x]` готова · `[!]` заблокирована (причина в заметках)

## Правила ведения файла

- Нумерация: `M{этап}-{номер}`, подзадачи `M0-02a`, `M0-02b`.
- Завершённые задачи сворачиваются в одну строку в разделе «Готово».
- Подробное описание — только для активного этапа. Будущие этапы хранятся как эпики и раскрываются перед стартом.
- Одна задача = одна вещь, до ~5 файлов, проверяется командами `dart format`, `flutter analyze`, `flutter test`.

---

## Готово

*(пока нет завершённых задач)*

---

## Этап M0 — Фундамент проекта

**ТЗ:** [uGym_Mobile_TZ.md](../specs/uGym_Mobile_TZ.md) (разделы 2, 6.3, 7.1), [uCraft_Design_System.md](../specs/uCraft_Design_System.md) (разделы 2–9, 20–22)

- [ ] **M0-01** Инициализация Flutter-проекта `uGym` (`tj.ugym.client`), git-репозитория, строгих правил `analysis_options.yaml` и структуры каталогов `Feature-First`
  - Файлы: `pubspec.yaml`, `analysis_options.yaml`, `lib/main.dart`, структура `lib/core/` и `lib/features/`
  - Проверка: `flutter analyze && flutter test`
- [ ] **M0-02** Подключение общего пакета `ugym_core` и реализация дизайн-токенов uCraft (Midnight & Cobalt: цвета Light/Dark, типографика Inter + Geist Mono, отступы 4px, радиусы, elevation, motion)
  - Файлы: `ugym_core/lib/design_system/tokens/*`, `themes/*`
  - Проверка: `flutter test` (контраст и токены Light/Dark)
- [ ] **M0-03** Базовые UI-компоненты uCraft в `ugym_core` (Primary/Secondary/Tertiary/Destructive кнопки, TextField с состояниями, Standard/Interactive/Highlight карточки, Loading/Empty/Error состояния)
  - Проверка: widget-тесты в обеих темах
- [ ] **M0-04** Сетевой слой (`Dio`), flavor-конфиги (`dev` / `staging` / `prod`), интерцепторы (`Auth`, `Accept-Language`, `X-Request-Id`, `Idempotency-Key`), `ErrorMapper` и `SecureStorage` (Keychain/Keystore)
  - Проверка: unit-тесты интерцепторов и маппера ошибок
- [ ] **M0-05** Форматтеры (`MoneyFormatter` minor→TJS, `WeightFormatter` grams↔kg, `DateFormatter` UTC→local/Asia/Dushanbe), локализация `ru` / `tg` / `en` (ARB) и переключатель языка/темы
  - Проверка: unit-тесты форматтеров + проверка переключения локали
- [ ] **M0-06** Навигационный каркас (`GoRouter`, 5 вкладок: Главная / Залы / Абонементы / Активность / Профиль, `AuthGuard`) и экран проверки связи с `GET /api/v1/health`
  - Проверка: `dart format --output=none --set-exit-if-changed . && flutter analyze && flutter test`

---

## Будущие этапы (эпики — раскрыть перед стартом каждого)

- [ ] **M1 — Ядро: Auth + QR + Абонементы + Push** (Welcome, Login, Register 18+/PDPA, Email OTP, Reset Password, Logout, Profile/Delete Account, Главная, Мои абонементы, Сканер QR + 2-шаговый GeoFence, Личный 60с QR, Визиты, `device-tokens`)
- [ ] **M2 — Каталог + Заявки + Расписание** (Публичный каталог список + карта + фильтры, Карточка зала, Отзывы, Заявки на абонемент по `public_id`, Покупки/чеки, Расписание и запись)
- [ ] **M3 — Дневник тренировок (`Workouts`)** (Упражнения, Библиотека и конструктор планов, Живая сессия + таймер отдыха, SQLite `drift` офлайн-очередь синхронизации с `Idempotency-Key`, Графики прогресса и 1RM Эпли)
- [ ] **M4 — Полировка UX, QA и релиз в сторы** (Доступность, edge-cases офлайна, e2e-тесты, `PrivacyInfo.xcprivacy`, Data Safety, TestFlight / Google Play)
