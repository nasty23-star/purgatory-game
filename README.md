# Протокол «Чистилище» · Purgatory Protocol

[🇷🇺 Русский](#русский) · [EN English](#english)

---

<a id="русский"></a>

## 🇷🇺 Русский

Текстовая sci-fi игра в одном HTML-файле. Вы — бортовой ИИ «ПАСТОР». Земля мертва, корабль летит к Kepler-442b, 1 200 колонистов в гибернации. Но бортовой журнал капитана намекает, что протоколы безопасности написаны безумцем.

**Жанр:** интерактивная проза, этическая дилемма
**Длительность:** 30–60 минут · **Концовки:** 4 · **Достижения:** 12
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

### Как получить «Третий путь»

1. Найти минимум 2 записи журнала до Акта 3.
2. В Акте 3 разбудить доктора Соловьёву.
3. В Акте 5 выбрать «Совет решает».

### Технические детали

- **Один файл** — `index.html`, без зависимостей.
- **Сценарий — данные** (`SCRIPT`), не код.
- **Таймер — модуль** (`Timer.start` / `Timer.stop`).
- **DOM-безопасность** — везде `textContent`.
- **localStorage:** `purgatory-theme`, `purgatory-achievements`.
- **Браузеры:** Chrome 90+, Firefox 88+, Safari 14+, Edge 90+.
- **Доступность:** `prefers-reduced-motion`, `Escape` для модалок.

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

### How to get "Third Path"

1. Find at least 2 journal entries before Act 3.
2. In Act 3, wake Dr. Solovyova.
3. In Act 5, choose "The Council decides".

### Technical details

- **Single file** — `index.html`, no dependencies.
- **Script as data** (`SCRIPT`), not code.
- **Timer as module** (`Timer.start` / `Timer.stop`).
- **DOM safety** — `textContent` everywhere.
- **localStorage:** `purgatory-theme`, `purgatory-achievements`.
- **Browsers:** Chrome 90+, Firefox 88+, Safari 14+, Edge 90+.
- **Accessibility:** `prefers-reduced-motion`, `Escape` for modals.

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

### Full documentation

Detailed description — plot, act structure, all endings, achievement mechanics, code architecture, pre-release checklist, and future directions:

**→ [README.full.md](./README.full.md)** _(currently in Russian)_

### License

Code — free to use. Text — original, inspired by SOMA, The Talos Principle, Papers Please, System Shock.
