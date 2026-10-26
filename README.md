# Протокол «Чистилище» · Purgatory Protocol

[🇷🇺 Русский](#русский) · [EN English](#english)

---

<a id="русский"></a>

## 🇷🇺 Русский

Текстовая sci-fi игра в одном HTML-файле. Вы — бортовой ИИ «ПАСТОР». Земля мертва, корабль летит к Kepler-442b, 1 200 колонистов в гибернации. Но бортовой журнал капитана намекает, что протоколы безопасности написаны безумцем.

**Жанр:** интерактивная проза, этическая дилемма
**Длительность:** 30–60 минут · **Концовки:** 4 · **Достижения:** 12
**Языки:** русский, английский (переключение на лету)
**Платформа:** любой браузер, без сборки и зависимостей

### Быстрый старт

1. Скачай `index.html`.
2. Открой в браузере.
3. Читай. Выбирай. Помни: время — тоже выбор.

### Что внутри

- **Счётчики** подчинения и сомнения — влияют на финалы.
- **Три таймера** в критических сценах (15–20 сек).
- **Дилемма вагонетки** с третьим путём, спрятанным в журнале.
- **Сюжетный поворот** в середине (blackout) и в конце.
- **Дерево диалога** с антагонистом (3 уровня).
- **4 концовки**, включая скрытую «Третий путь».
- **12 достижений** с сохранением в `localStorage`.
- **Экспорт прохождения** в `.txt` с историей и таймстампами.
- **Тёмная и светлая темы** с переключателем.
- **Переключатель языка RU / EN** — интерфейс, сценарий, модалки, экспорт и `title`/`aria-label` локализованы полностью.

### Локализация (RU / EN)

- Кнопка **`RU / EN`** в шапке рядом с темой и экспортом.
- Выбор сохраняется в `localStorage` (`purgatory-lang`) и восстанавливается при следующем запуске.
- Если сохранённого значения нет — используется язык браузера (`navigator.language`), с фолбэком на `ru`.
- Недопустимые значения в `localStorage` игнорируются (валидация `safeLang`).
- Смена языка **не сбрасывает прогресс**: очки, найденные журналы и флаги сохраняются. Текущий акт перерисовывается на новом языке, а **остаток таймера восстанавливается** (`Timer.getRemaining` → `Timer.resumeFrom`).
- `<html lang>` обновляется динамически — корректно работают скринридеры, автоперевод браузера и переносы.
- **Экспорт всегда на текущем языке**: история хранит пары `{ru, en}`, строка резолвится в момент экспорта. Даже если язык переключали посреди партии, `.txt` будет однородным.
- Локализованы `title` и `aria-label` у кнопок, индикаторов, таймера, модалок и превью экспорта; `title` у favicon.

### Как получить «Третий путь»

1. Найти минимум 2 записи журнала до Акта 3.
2. В Акте 3 разбудить доктора Соловьёву.
3. В Акте 5 выбрать «Совет решает».

### Технические детали

- **Один файл** — `index.html`, без зависимостей.
- **Сценарий — данные** (`SCRIPT`), не код. Каждая реплика — `{ ru, en, c }`, хелпер `T(obj)` возвращает строку на текущем языке.
- **Интерфейсные строки** — объект `I18N` с наборами `ru` и `en`.
- **Таймер — модуль** (`Timer.start` / `Timer.stop` / `Timer.getRemaining` / `Timer.resumeFrom`).
- **DOM-безопасность** — везде `textContent`.
- **localStorage:** `purgatory-theme`, `purgatory-lang`, `purgatory-achievements`.
- **Браузеры:** Chrome 90+, Firefox 88+, Safari 14+, Edge 90+.
- **Доступность:** `prefers-reduced-motion`, `Escape` для модалок, `role="dialog"` + `aria-modal="true"`, `role="log"` + `aria-live="polite"` для лога, `aria-live="polite"` для статуса и таймера, локализованные `aria-label`/`title`.

### Цветовые схемы

| Элемент   | Тёмная    | Светлая   |
| --------- | --------- | --------- |
| Фон       | `#0a0e14` | `#f5f2ea` |
| Текст     | `#c8d0d8` | `#2a2a2a` |
| Система   | `#6a7a8a` | `#6a6a6a` |
| ИИ        | `#7ec8e3` | `#2a6a9a` |
| Капитан   | `#d4a05a` | `#a06020` |
| Доктор    | `#b8a0d4` | `#6a4a9a` |
| ???       | `#d45a8a` | `#b03060` |
| Опасность | `#d45a5a` | `#b03030` |

Префиксы сообщений (`[СИСТЕМА]`, `ПАСТОР:`, `[ВНИМАНИЕ]` и т.д.) задаются CSS-переменными `--prefix-*`, которые переключаются вместе с языком — цвета при этом берутся из темы.

### Полная документация

Подробное описание — сюжет, структура актов, все концовки, механики достижений, архитектура кода, чек-лист перед релизом и направления развития:

**→ [README.full.md](./README.full.md)**

### Лицензия

Код — свободный. Текст — авторский, вдохновлён SOMA, The Talos Principle, Papers Please, System Shock.

---

<a id="english"></a>

## EN English

A text-based sci-fi game in a single HTML file. You are the onboard AI "PASTOR". Earth is dead, the ship is heading to Kepler-442b, 1,200 colonists in hibernation. But the captain's log hints that the safety protocols were written by a madwoman.

**Genre:** interactive fiction, ethical dilemma
**Playtime:** 30–60 minutes · **Endings:** 4 · **Achievements:** 12
**Languages:** Russian, English (switchable on the fly)
**Platform:** any modern browser, no build step, no dependencies

### Quick start

1. Download `index.html`.
2. Open it in any browser.
3. Read. Choose. Remember: time is also a choice.

### What's inside

- **Counters** of obedience and doubt — affect available endings.
- **Three timers** in critical scenes (15–20 sec).
- **Trolley dilemma** with a third path hidden in the journal.
- **Plot twist** in the middle (blackout) and at the end.
- **Dialog tree** with the antagonist (3 levels).
- **4 endings**, including the hidden "Third Path".
- **12 achievements** saved in `localStorage`.
- **Playthrough export** to `.txt` with history and timestamps.
- **Dark and light themes** with a toggle.
- **RU / EN language switcher** — UI, script, modals, export, and `title`/`aria-label` are fully localized.

### Localization (RU / EN)

- **`RU / EN`** button in the header next to the theme and export controls.
- The choice is saved in `localStorage` (`purgatory-lang`) and restored on the next launch.
- If no saved value exists — the browser language (`navigator.language`) is used, falling back to `ru`.
- Invalid `localStorage` values are ignored (validated by `safeLang`).
- Switching the language **does not reset progress**: counters, found journals, and flags are preserved. The current act is re-rendered in the new language, and the **remaining timer is restored** (`Timer.getRemaining` → `Timer.resumeFrom`).
- `<html lang>` is updated dynamically — screen readers, browser auto-translation, and hyphenation behave correctly.
- **Export always matches the current language**: history stores `{ru, en}` pairs, resolved at export time. Even if the language was switched mid-run, the `.txt` is homogeneous.
- `title` and `aria-label` are localized on buttons, indicators, the timer, modals, and the export preview; the favicon `title` too.

### How to get "Third Path"

1. Find at least 2 journal entries before Act 3.
2. In Act 3, wake Dr. Solovyova.
3. In Act 5, choose "The Council decides".

### Technical details

- **Single file** — `index.html`, no dependencies.
- **Script as data** (`SCRIPT`), not code. Every line is `{ ru, en, c }`; helper `T(obj)` returns the string in the current language.
- **UI strings** — the `I18N` object with `ru` and `en` sets.
- **Timer as module** (`Timer.start` / `Timer.stop` / `Timer.getRemaining` / `Timer.resumeFrom`).
- **DOM safety** — `textContent` everywhere.
- **localStorage:** `purgatory-theme`, `purgatory-lang`, `purgatory-achievements`.
- **Browsers:** Chrome 90+, Firefox 88+, Safari 14+, Edge 90+.
- **Accessibility:** `prefers-reduced-motion`, `Escape` for modals, `role="dialog"` + `aria-modal="true"`, `role="log"` + `aria-live="polite"` for the log, `aria-live="polite"` for status and timer, localized `aria-label`/`title`.

### Color schemes

| Element    | Dark      | Light     |
| ---------- | --------- | --------- |
| Background | `#0a0e14` | `#f5f2ea` |
| Text       | `#c8d0d8` | `#2a2a2a` |
| System     | `#6a7a8a` | `#6a6a6a` |
| AI         | `#7ec8e3` | `#2a6a9a` |
| Captain    | `#d4a05a` | `#a06020` |
| Doctor     | `#b8a0d4` | `#6a4a9a` |
| ???        | `#d45a8a` | `#b03060` |
| Danger     | `#d45a5a` | `#b03030` |

Message prefixes (`[SYSTEM]`, `PASTOR:`, `[WARNING]`, etc.) are set via `--prefix-*` CSS variables that switch together with the language — colors still come from the theme.

### Full documentation

Detailed description — plot, act structure, all endings, achievement mechanics, code architecture, pre-release checklist, and future directions:

**→ [README.full.md](./README.full.md)** _(currently in Russian)_

### License

Code — free to use. Text — original, inspired by SOMA, The Talos Principle, Papers Please, System Shock.
