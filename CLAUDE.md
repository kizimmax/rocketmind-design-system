# Claude Code Context for Rocketmind

## 🎯 Project Overview
**Rocketmind** — SaaS платформа AI-агентов для ведения кейсов (проектов) с чат-интерфейсом.
- MVP 1.1 (февраль-март 2026)
- Web-only, no-code интеграция через n8n
- Единая дизайн-система для всего сервиса и лендинга

**PRD:** `docs/PRD Rocketmind AI Agent MVP 1.1 - от 20 февр. 2026.md`

---

## 🏗️ Архитектура Дизайна

### Единая Дизайн-Система
**Все экраны (лендинг + сервис) работают на одной design system:**

1. **Компоненты:**
   - UI Kit на основе **shadcn/ui** + кастомизация
   - Переиспользуемые компоненты: Button, Input, Modal, Card, Sidebar, Chat-bubble
   - Темизация (dark/light mode если нужна)

2. **Токены дизайна** (переменные в .pen файле):
   - Цветовая палитра (primary, secondary, neutral, success, warning, danger)
   - Типография (headings, body, captions)
   - Spacing & grid
   - Border radius, shadows

3. **Файлы дизайна:**
   - `.pen файлы` для визуального дизайна (Figma-подобный формат)
   - Одна design system → все экраны
   - Экспортировать компоненты в код через правила

### Экраны в Системе
1. **Лендинг** — CTA «Попробовать»
2. **Auth** — Email + Code flow (2 step)
3. **Main App** — Sidebar + Chat + Agent selector
4. **Agent Catalog** — Каталог агентов для добавления

---

## 📂 Key Files & Structure
```
/Rocketmind/
├── CLAUDE.md                    # ← ты здесь
├── docs/
│   └── PRD Rocketmind AI Agent MVP 1.1...
├── design/                      # Дизайн-система (создать если нет)
│   ├── system.pen              # Основной .pen файл design-system
│   ├── landing.pen             # Лендинг
│   ├── auth.pen                # Авторизация
│   └── app.pen                 # Главный интерфейс сервиса
├── design-system-docs/         # Веб-версия дизайн-системы (Next.js, localhost:3000)
│   └── src/                    # Исходный код документации
├── src/                        # Исходный код приложения (структура TBD)
├── assets/
└── .agent/
```

---

## 🎨 Design System Guidelines

### Правила при работе с дизайном:
1. **Переиспользование компонентов** — не создавать новый компонент, если есть похожий в system
2. **Токены вместо хардкода** — все цвета/размеры из переменных
3. **Responsive дизайн** — mobile-first подход
4. **Consistency** — один стиль button, input, card и т.д. везде
5. **Contrast & Accessibility** — WCAG AA минимум

### ⚠️ КРИТИЧЕСКИ ВАЖНО: Синхронизация дизайн-системы

**При любых изменениях в дизайн-системе ВСЕГДА обновлять ОБА источника:**

1. **`design/design-system.md`** — главный документ-источник правды (Markdown)
2. **`design-system-docs/`** — веб-версия документации (Next.js, запущена на http://localhost:3000)

**Никогда не обновлять только один из них.** Оба должны быть синхронизированы после каждого изменения.

### При добавлении экрана:
1. Смотри существующие компоненты в design system
2. Создай новый .pen файл для экрана ИЛИ добавь в existing
3. Используй компоненты через `ref` (component instances)
4. Переопределяй свойства через data bindings, а не создавай новые
5. Сделай скриншот и проверь consistency

---

## 💻 Frontend Stack
- **Инструмент:** Whip-coding (согласно техническому стеку)
- **UI Library:** shadcn/ui
- **Дизайн система:** Custom .pen file с переменными и компонентами
- **Стилизация:** Tailwind CSS (если нужна)

---

## 🔌 Backend/Integration
- **Logic:** n8n вебхуки
- **Data Model:** users, cases, agents, conversations, messages
- **Chat protokol:** Webhook-based message flow

---

## ✅ Success Criteria (из PRD)
1. ✅ Авторизация (email + code)
2. ✅ Автобутстрап по URL `/a/{agent_slug}`
3. ✅ Диалог в чате с ИИ-агентом
4. ✅ Результат/ссылка на оплату в системном сообщении

---

## 🚫 Out of Scope
- Живые эксперты в UI
- Сложные анимации
- Отдельный интерфейс авторизации эквайринга (все в чате)
- Личный кабинет эксперта

---

## 📋 Workflow для Разработки

### Когда нужно добавить экран:
1. **Дизайн первый:** Создай в .pen файле (используй design system)
2. **Проверка:** Скриншот → согласование
3. **Код:** Реализуй на основе дизайна

### Когда нужно добавить компонент:
1. Проверь, есть ли в design system уже что-то похожее
2. Если нет → добавь в system.pen как reusable компонент
3. Используй его через ref везде
4. Обнови документацию компонента в comments

### Когда нужно изменить дизайн-систему:
1. Обнови **`design/design-system.md`** (документ-источник правды)
2. Обнови соответствующие файлы в **`design-system-docs/src/`** (веб-документация)
3. Проверь отображение на http://localhost:3000

---

## 🛠️ Useful Commands
```bash
# Запуск веб-документации дизайн-системы
cd design-system-docs && npm run dev
# Открыть: http://localhost:3000
```

---

## 📌 Important Notes
- **Дизайн система = источник правды** для всех экранов
- Все вопросы стилизации решаются через переменные, не через локальный CSS
- Переиспользование > создание нового
- Сперва дизайн → потом код
- **design-system.md и design-system-docs всегда синхронизированы**

---

**Last updated:** 2026-03-10
**Version:** 1.1
