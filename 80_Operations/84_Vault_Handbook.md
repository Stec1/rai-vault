# RAi Vault — Інструкція та архітектура роботи

> Operating handbook для rai-vault.
> Читається founder'ом і будь-яким новим агентом як перший документ для розуміння системи.
> Останнє оновлення: 2026-04-16

---

## SECTION 1 — Що таке rai-vault

`rai-vault` — структурована операційна пам'ять проєкту RAi. Це окремий Obsidian/GitHub repository, який існує паралельно з основним product repo RAi.

**Що це:**
- Founder operating system для планування, рішень, execution continuity
- Довготривала memory layer для AI-assisted роботи (Claude, ChatGPT, Codex)
- Архів рішень, аудитів, issue execution, prompts та handoff контексту

**Чим відрізняється від RAi repo:**
- RAi repo = код, docs, міграції, runtime — implementation truth
- rai-vault = контекст, рішення, plans, prompts, memory — operating truth

**Навіщо існує:**
Проєкт ведеться через multi-agent workflow (GPT, Claude, Codex). Без зовнішньої пам'яті кожна сесія починається з нуля, рішення губляться в чатах, issue execution втрачає контекст між сесіями, а founder змушений тримати все в голові.

**Яку проблему вирішує:**
- Контекст не живе в чатах — він живе у vault
- Кожен issue має готовий context layer до початку роботи
- Кожен merge лишає слід
- Будь-який новий агент швидко в'їжджає в проєкт
- Founder завжди бачить current state, next action, risks

---

## SECTION 2 — Основна логіка vault

**Два джерела істини:**
- `RAi repo` = implementation truth (код, архітектура, docs)
- `rai-vault` = memory truth (контекст, рішення, execution history)

Ці два шари не дублюють один одного. Repo docs описують що система робить; vault описує як і чому проєкт приймав рішення, що було зроблено, що далі.

**Чому не можна тримати все в чатах:**
- Чати — ephemeral. Закрив вкладку — втратив контекст
- Пошук по чатах ненадійний
- Агенти не можуть читати твої попередні чати
- Немає versioning, немає diff, немає audit trail

**Чому vault важливий для founder workflow:**
- Одна точка входу для будь-якого питання про проєкт
- Handoff між агентами стає тривіальним — достатньо дати шлях до файлу
- Рішення накопичуються, а не перевигадуються
- Issue execution не залежить від того, хто саме виконує

**Базове правило:** якщо це корисна пам'ять — вона має жити у vault. Якщо це код чи runtime — у repo.

---

## SECTION 3 — Опис усіх основних секцій

### 00_MOC — Maps of Content

**Відповідає за:** навігацію по vault.

**Що зберігається:** MOC-файли (Map of Content) з посиланнями на ключові ноди кожної зони.

**Що НЕ має бути:** контент, рішення, прости нотатки. MOC — лише навігація.

**Як використовувати:** стартова точка. Перший файл, який відкриває founder або новий агент — `00_MOC_RAi.md`.

---

### 10_Foundation — Foundational context

**Відповідає за:** базові визначення проєкту.

**Що зберігається:** визначення RAi, термінологічний словник, core principles. Все що рідко змінюється і задає рамку проєкту.

**Що НЕ має бути:** execution деталі, тактичні рішення, поточний стан.

**Як використовувати:** читається один раз на старті. Онови тільки якщо змінюється фундаментальне розуміння проєкту.

---

### 20_Product — Продуктовий шар

**Відповідає за:** продуктове бачення на рівні vault.

**Що зберігається:** короткі сумаризації Product Vision, MVP Scope, Domain Model, Observatory Model, Publication Model, Reputation Model, Monetization Model.

**Що НЕ має бути:** повні специфікації (вони в repo `docs/vision.md`, `docs/mvp-contract.md`, `docs/world-structure.md`). Vault містить лише operating-level виклад + посилання на repo.

**Як використовувати:** швидкий reference коли агенту потрібен продуктовий контекст без читання всього repo.

---

### 30_Architecture — Архітектурний шар

**Відповідає за:** operating-level опис архітектури.

**Що зберігається:** System Architecture summary, Infrastructure State, Deployment State, Database Model overview, API Surface overview, Env and Secrets Map, Integrations Map.

**Що НЕ має бути:** повний tech stack contract (він у repo `docs/architecture.md`). Vault фіксує стан інфраструктури, не специфікацію.

**Як використовувати:** для readiness checks, risk scans, перевірки alignment між implementation і очікуваним станом.

---

### 40_Execution — Execution memory

**Відповідає за:** пам'ять виконання кожного issue + поточний стан проєкту.

**Що зберігається:**
- `00_Current_State.md` — snapshot проєкту на сьогодні
- `01_Next_Action.md` — найближчий крок
- `ISSUE-XX/` папки для кожного issue: Readiness, Prompt_For_Claude, Prompt_For_Code, Result

**Що НЕ має бути:** код, docs з repo, discussion логи чатів.

**Як використовувати:** перший файл перед будь-якою дією — `00_Current_State.md`. Перед початком issue — створити папку і заповнити Readiness.

---

### 50_Prompts — Reusable prompt library

**Відповідає за:** бібліотеку prompts і шаблонів.

**Що зберігається:**
- `Templates/` — структурні шаблони (Issue Handoff, Decision Record, Audit Report, Current State Update, Merge Report)
- `Activation_Prompt_Library.md` — 20 ready-to-use команд для агента
- Підпапки для prompts за типом: Claude, Code, Audit, UI, Infra

**Що НЕ має бути:** одноразові prompts для конкретного issue (вони живуть у `40_Execution/ISSUE-XX/`).

**Як використовувати:** переносиш prompt у цю бібліотеку тільки коли він стає reusable — тобто використовуватиметься більше одного разу.

---

### 60_Audits — Audit trail

**Відповідає за:** історію аудитів проєкту.

**Що зберігається:** repo audits, vault audits, verification reports, phase retrospectives. Кожен файл з датою в назві: `YYYY-MM-DD_[scope]_Audit.md`.

**Що НЕ має бути:** короткі поточні перевірки (вони йдуть у Current_State). Audit — формальний документ з findings і recommendations.

**Як використовувати:** запускати аудит після завершення фази, перед важливим merge, перед зміною стратегії.

---

### 70_Decisions — Decision log

**Відповідає за:** всі ключові рішення проєкту на operating level.

**Що зберігається:** Decision Records (DL-001, DL-002...) за шаблоном: Status, Context, Decision, Consequences. Плюс `Decision_Index.md` для навігації.

**Що НЕ має бути:** ідеї, гіпотези, exploratory thinking (це в `100_Notes/`).

**Як використовувати:** створити DL-XXX тільки коли рішення прийнято і воно впливає на проєкт далі. Синхронізувати з repo `docs/decision-log.md` коли це архітектурне рішення.

---

### 80_Operations — Operating rules

**Відповідає за:** правила роботи команди/founder'а з проєктом.

**Що зберігається:** Working Model, Agent Roles, Handoff Rules, Agent Usage Instructions.

**Що НЕ має бути:** execution деталі конкретних issue.

**Як використовувати:** reference для розуміння як ми працюємо. Новий агент читає цю секцію після `00_MOC`.

---

### 90_Archive — Архів

**Відповідає за:** застарілі, замінені або завершені артефакти, які варто зберегти для history, але прибрати з активного простору.

**Що зберігається:** старі версії MOC, застарілі templates, закриті execution threads, outdated audits.

**Що НЕ має бути:** активні документи, які ще використовуються.

**Як використовувати:** переносити сюди тільки коли документ замінений або явно застарілий. Не видаляти — архівувати.

---

### 100_Notes — Exploratory zone

**Відповідає за:** ідеї, гіпотези, стратегічне thinking founder'а.

**Що зберігається:** Ideas Backlog, Scaling Hypotheses, Business Model Notes, будь-які дослідницькі нотатки зі статусом (idea / exploring / ready-for-review / promoted / archived).

**Що НЕ має бути:** затверджені рішення (вони в `70_Decisions/`), продуктові специфікації, execution plans.

**Як використовувати:** писати вільно. Коли ідея зріє — promote у Decision. Див. правила у `100_Notes/README.md`.

---

## SECTION 4 — Як працювати з issue через vault

Кожен issue має власну папку: `40_Execution/ISSUE-XX/`.

**Обов'язкові файли для кожного issue:**

1. `ISSUE-XX_Readiness.md` — preconditions, dependencies, risks, go/no-go verdict
2. `ISSUE-XX_Prompt_For_Claude.md` — prompt для readiness/audit від Claude
3. `ISSUE-XX_Prompt_For_Code.md` — фінальний prompt, який іде в Code/Codex
4. `ISSUE-XX_Result.md` — що було зроблено після merge

**Life cycle issue у vault:**

1. **Планування** — створити папку, заповнити Readiness з preconditions і risks
2. **Підготовка** — згенерувати Prompt_For_Code через агента (команда #3 з Activation Library)
3. **Execution** — Codex виконує за prompt, створюється PR
4. **Review** — перевірка diff проти acceptance criteria
5. **Merge** — після merge заповнюється Result + Merge Report
6. **Пам'ять** — оновлюється `00_Current_State.md` і `01_Next_Action.md`

**Як не втрачати execution context:**
- Readiness пишеться ДО початку роботи, не після
- Prompt_For_Code — не чорнетка, а фінальна версія, яка пішла в Codex
- Result пишеться одразу після merge, не "потім"
- Якщо в середині execution виникло рішення — одразу DL-XXX у `70_Decisions/`

---

## SECTION 5 — Як працювати з prompts

**Reusable vs one-time:**
- One-time prompt — для конкретного issue, живе в `40_Execution/ISSUE-XX/`
- Reusable prompt — використовується неодноразово, живе в `50_Prompts/`

**Коли prompt стає reusable:**
- Коли ти використав його вдруге — переноси в `50_Prompts/`
- Коли він працює для цілого класу задач (audit, readiness, review)
- Коли він стабільний і більше не потребує редагування

**Як зберігати prompts:**
- Назва файлу описує призначення: `Audit_Vault_Health.md`, `Readiness_Check_Generic.md`
- Всередині: коли використовувати / expected input / prompt body / expected output
- English для prompts, які йдуть в агентів; українська для пояснень founder'у

**Activation Prompt Library:**
Файл `50_Prompts/Activation_Prompt_Library.md` містить 20 команд для щоденної роботи з project agent. Це не повний каталог — це швидкий arsenal. Основні категорії:
- Audit / Readiness / Status (1, 2, 12, 20)
- Prompt preparation (3, 13, 16)
- Post-merge (4, 7, 8)
- Planning (5, 9, 18)
- Risk / Review (10, 11, 15)
- Scaling (14, 17, 19)
- Decision sync (6)

**Handoff між агентами:**
- GPT → strategy, framing, prompt shaping
- Claude → audit, readiness, handoff prep, memory architecture
- Code/Codex → execution

Handoff протокол: Claude готує prompt для Code, Code виконує, Claude робить merge report. Всі артефакти зберігаються у vault за issue ID.

---

## SECTION 6 — Як працювати з audit та merge reports

### Audit

**Коли робити:**
- Перед початком нової фази
- Після тривалої паузи в проєкті
- Перед великим архітектурним рішенням
- Періодично (раз на місяць — vault health check)

**Що зберігати в audit:**
- Scope — що саме перевіряли
- Findings — що знайшли
- Gaps — чого не вистачає
- Recommendations — що робити далі
- Outcome — verdict

**Формат:** шаблон у `50_Prompts/Templates/Template_Audit_Report.md`. Файл: `60_Audits/YYYY-MM-DD_[scope]_Audit.md`.

### Merge Report

**Навіщо:**
Зафіксувати що саме відбулось після merge, щоб memory проєкту не залежала від git log і PR description.

**Що фіксувати після merge:**
- What changed / Why it changed
- Files touched
- Issue relation
- Validation status
- Risks introduced
- Next action
- Checklist — що оновити у vault (Current_State, Next_Action, Decision_Index, Result)

**Формат:** шаблон у `50_Prompts/Templates/Merge_Report_Template.md`. Файл: `40_Execution/ISSUE-XX/ISSUE-XX_Merge_Report.md`.

**Зв'язок merge report → issue memory:**
Merge Report живе в папці issue. Коли хтось читає `ISSUE-XX/`, він бачить повний life cycle: Readiness → Prompts → Result → Merge Report. Це і є issue memory.

---

## SECTION 7 — Як працювати з decisions

**Чому decisions не мають жити в чатах:**
Рішення — це інвестиція. Через три місяці ти не пам'ятатимеш чому обрав Fastify замість Express, а новий агент не зможе це дізнатись. Decision Record робить рішення видимим, обґрунтованим і ревізованим.

**Коли створювати DL-XXX:**
- Обрано одну опцію з кількох альтернатив
- Рішення впливає на архітектуру, продукт, workflow або витрати
- Рішення буде впливати на проєкт довше ніж один issue

**Коли НЕ створювати:**
- Тактичні виборі в межах одного issue (вони в Result файлі)
- Ідея ще обговорюється (вона в `100_Notes/`)
- Рішення було повторенням попереднього (оновити існуючий DL)

**Idea vs Decision:**
- Ідея: "А що якщо зробити marketplace?" → `100_Notes/Ideas_Backlog.md`
- Рішення: "Marketplace буде в Phase 3. Причина: ...". → `70_Decisions/DL-XXX.md`

Перехід ідея → рішення завжди явний. Ідея не стає рішенням автоматично.

**Зв'язок decision ↔ issue ↔ repo:**
- У Decision Record посилання на issue, якщо рішення прийнято під час execution
- Якщо decision архітектурний — дзеркало в repo `docs/decision-log.md`
- У issue Result — посилання на DL-XXX, якщо рішення прийнято всередині issue

---

## SECTION 8 — Як працювати з 100_Notes

**Що це:** exploratory zone. Не source of truth. Простір для ідей до того, як вони стануть рішеннями.

**Як складати ідеї:**
- Групуй в тематичні файли (Ideas_Backlog, Scaling_Hypotheses, Business_Model_Notes), не роби файл на кожну ідею
- Кожна ідея має дату і статус: idea / exploring / ready-for-review / promoted / archived
- Короткий формат: таблиця або bullet. Не есе.

**Як не перетворити на хаос:**
- Щомісяця — revision. Архівуй застаріле, drop нерелевантне
- Якщо файл росте > 50 items — розбий на підфайли
- Не дублюй ідеї між файлами — чіткі тематичні межі
- Все що старше 3 місяці без руху → archived

**Як переводити ідеї в рішення:**
1. Ідея змінює статус idea → exploring, коли ти починаєш її обдумувати
2. exploring → ready-for-review, коли вона готова до формального рішення
3. Запускаєш агента: "Evaluate idea X for promotion to Decisions" (команда #17)
4. Якщо verdict — ready, створюєш `70_Decisions/DL-XXX.md` і лінкуєш назад
5. Статус ідеї → promoted

**Різниця між типами:**
- **Note** — одноразова думка, може не мати напрямку
- **Hypothesis** — стверджувальна ідея з falsification criteria ("це неправильно якщо...")
- **Backlog item** — потенційна задача, ще не сплановано
- **Decision** — прийняте і зафіксоване рішення

---

## SECTION 9 — Як масштабувати rai-vault

**Принцип росту:** vault росте разом з проєктом, а не наперед. Не створюй папку, поки в ній немає реального контенту.

**Що додавати далі (по потребі):**
- Більше Decision Records — з кожним значущим вибором
- Більше Audits — після кожної фази
- Більше reusable prompts у `50_Prompts/` — після повторення
- Product model notes у `20_Product/` — коли продуктовий шар потребує більше деталей
- Integrations і Deployment state apdates у `30_Architecture/` — з ростом інфраструктури

**Ознаки правильного росту:**
- Кожен merge лишає слід у vault
- Кожен issue має повну папку з 4+ файлами
- Decision_Index росте лінійно з важливими виборами
- 100_Notes не лише росте, але й промотується в Decisions
- Нові агенти в'їжджають в проєкт за < 30 хвилин через MOC

**Ознаки неправильного росту:**
- Файли з застарілим контентом які ніхто не оновлює
- Дублювання repo docs у vault
- 100_Notes росте, але нічого не промотується
- Issue папки з порожніми Result файлами
- `00_Current_State.md` не оновлений тижнями

**Коли створювати новий файл vs доповнювати існуючий:**
- Нова тема / новий scope → новий файл
- Розширення існуючої теми → доповнювати
- Файл > 300 рядків → розбивати на підфайли
- Новий issue → завжди нова папка

**Як не дублювати repo docs:**
- Vault містить operating-level summary + посилання на repo
- Якщо потрібна повна специфікація — читай repo
- Коли repo docs змінюються — vault не переписує, а оновлює summary, якщо воно суттєво відхилилось

---

## SECTION 10 — Практичний workflow founder'а

### Щоденний цикл

**Ранок (start of work):**
1. Відкрити `40_Execution/00_Current_State.md`
2. Відкрити `40_Execution/01_Next_Action.md`
3. Перейти до активного ISSUE-XX, перевірити Readiness
4. Визначити: готуємо prompt, виконуємо, ревʼюємо, мерджимо?

**Під час issue execution:**
1. Якщо потрібен prompt → команда #3 агенту (Code prompt)
2. Codex виконує
3. Review diff проти acceptance criteria
4. Якщо виникло рішення → `70_Decisions/DL-XXX.md`

**Після merge:**
1. Заповнити `ISSUE-XX_Result.md`
2. Створити `ISSUE-XX_Merge_Report.md` з шаблону
3. Оновити `00_Current_State.md`
4. Оновити `01_Next_Action.md`
5. Якщо merge значущий → `60_Audits/YYYY-MM-DD_Post_Merge_Audit.md`

**Коли запускати audit:**
- Перед початком нової фази — full audit (команда #1)
- Перед ризикованим merge — risk scan (команда #10)
- Після значущого merge — post-merge audit
- Щомісяця — vault health check (команда #20)

**Як використовувати Claude agent:**
- Для audit, readiness, prompt prep, merge reports, decision sync
- Не для написання product code
- Активація через команди з `Activation_Prompt_Library.md`

**Як використовувати Code/Codex:**
- Тільки з готовим prompt від Claude
- Вузький scope, чіткі acceptance criteria
- Завжди через PR, не прямим push у main
- Після merge — повернення в Claude для merge report

**Memory continuity:**
- Ніколи не залишати issue без Result після merge
- Ніколи не приймати рішення без DL-XXX
- Ніколи не тримати активний контекст тільки в чаті
- Перед закриттям робочої сесії — перевір Current_State і Next_Action актуальні

---

## SECTION 11 — Найважливіші правила

1. **Source of truth separation.** RAi repo = implementation truth. rai-vault = memory truth. Не плутати.

2. **No duplication.** Не дублювати repo docs у vault. Vault зберігає operating summary + посилання.

3. **No chat memory.** Якщо рішення, prompt або контекст важливі — вони у vault, не в чаті.

4. **Every merge leaves a trace.** Merge Report + оновлення Current_State після кожного merge. Без винятків.

5. **Every issue has a folder.** Мінімум 4 файли: Readiness, Prompt_For_Claude, Prompt_For_Code, Result.

6. **Decisions are explicit.** Рішення → DL-XXX. Ідея без DL — не рішення.

7. **Ideas live in 100_Notes, not everywhere.** Не розкидати ідеї по різних секціях.

8. **Templates over improvisation.** Для повторюваних артефактів — завжди шаблон з `50_Prompts/Templates/`.

9. **Reusable prompts get promoted.** Використав prompt удруге — переноси в `50_Prompts/`.

10. **Archive, don't delete.** Застаріле йде в `90_Archive/`, не видаляється.

11. **Current_State is the single daily entry point.** Починай день тут, закінчуй день тут.

12. **Audit before phase, retro after phase.** Аудит на вході, ретроспектива на виході.

13. **Agent input is narrow.** Чіткий scope → чіткий output. Нечіткий prompt — нечіткий результат.

14. **Small merges, clean history.** Не роздувати один PR. Розбивати на блоки.

15. **Read MOC first.** Будь-який новий агент або повернення до проєкту — старт з `00_MOC/00_MOC_RAi.md`.

---

## SECTION 12 — Короткий підсумок

`rai-vault` — це не нотатник. Це operating system проєкту RAi, винесена за межі мозку founder'а і за межі чатів.

**Чому це важливо:**
- Проєкт ведеться multi-agent workflow — без зовнішньої пам'яті агенти безпорадні
- Рішення і контекст накопичуються, а не випаровуються
- Новий агент в'їжджає в проєкт за хвилини
- Founder тримає фокус на рішеннях, а не на відновленні контексту

**Як використовувати правильно:**
- Repo — код. Vault — пам'ять. Два окремих світи, що працюють разом
- Кожен merge → слід у vault
- Кожне рішення → DL-XXX
- Кожна ідея → 100_Notes до promotion
- Кожен день → старт з Current_State

**Що це дає:**
Професійний workflow, в якому проєкт розвивається навіть коли founder переключається, агенти змінюються, сесії обриваються. Vault тримає цілісність. Repo тримає продукт. Founder тримає стратегію. Разом це працює як операційна система, а не як хаос notes.

Vault — це дисципліна, перетворена в інфраструктуру.
