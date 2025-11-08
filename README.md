# AI Chat Agent Workflow

[![n8n](https://img.shields.io/badge/n8n-workflow-FF6D5A?logo=n8n)](https://n8n.io) [![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4-412991?logo=openai)](https://openai.com) [![LangChain](https://img.shields.io/badge/LangChain-Integration-1C3C3C)](https://langchain.com)

## Автор

**Розробник:** Сергій Щербаков
**Email:** sergiyscherbakov@ukr.net
**Telegram:** @s_help_2010

### 💰 Підтримати розробку
Задонатити на каву USDT (BINANCE SMART CHAIN):
**`0xDFD0A23d2FEd7c1ab8A0F9A4a1F8386832B6f95A`**

---

Автоматизований робочий процес для створення інтелектуального чат-бота на платформі n8n з використанням моделі GPT-4 mini від OpenAI та LangChain інтеграції.

## 🚀 Можливості

- ✅ Обробка вхідних повідомлень користувачів
- 🧠 Інтелектуальні відповіді за допомогою OpenAI GPT-4 mini
- 💾 Контекстна пам'ять для збереження історії розмов
- 🔧 Розширювана архітектура з додатковими інструментами
- 🔄 Автоматичне керування сесіями

## 📋 Вимоги

- [n8n](https://n8n.io/) v1.0+
- OpenAI API ключ
- LangChain пакет для n8n (`@n8n/n8n-nodes-langchain`)

## 🛠 Встановлення

1. **Клонуйте або завантажте файл workflow:**
```bash
   git clone https://github.com/username/ai-chat-agent-workflow.git
```

2. **Імпортуйте workflow в n8n:**
   - Відкрийте n8n
   - Перейдіть до "Import from file"
   - Оберіть `My_workflow-1.json`

3. **Налаштуйте OpenAI API:**
   - Відкрийте вузол "OpenAI Chat Model"
   - Додайте ваш OpenAI API ключ
   - Збережіть налаштування

4. **Активуйте workflow:**
   - Натисніть кнопку "Active" в правому верхньому куті

## 🏗 Архітектура
```
┌─────────────────────┐    ┌─────────────┐
│ Chat Trigger        │───▶│ AI Agent    │
└─────────────────────┘    └─────────────┘
                                  │
                           ┌──────┴──────┐
                           ▼             ▼
                    ┌──────────────┐ ┌─────────────┐
                    │ OpenAI Model │ │ Memory      │
                    └──────────────┘ └─────────────┘
                           │             │
                           └──────┬──────┘
                                  ▼
                           ┌─────────────┐
                           │ Agent Tools │
                           └─────────────┘
```

### Компоненти

| Компонент | Тип | Опис |
|-----------|-----|------|
| **Chat Trigger** | `chatTrigger` | Точка входу для повідомлень |
| **AI Agent** | `agent` | Центральний обробник логіки |
| **OpenAI Model** | `lmChatOpenAi` | GPT-4 mini мовна модель |
| **Memory** | `memoryBufferWindow` | Буферна пам'ять контексту |
| **Agent Tools** | `agentTool` | Розширення функціональності |

## 🚦 Використання

1. **Запустіть workflow** в n8n
2. **Надішліть повідомлення** через налаштований тригер
3. **Отримайте відповідь** від AI агента
4. **Продовжуйте діалог** - контекст зберігається автоматично

## ⚙️ Конфігурація

### OpenAI налаштування
```json
{
  "model": "gpt-4-mini",
  "temperature": 0.7,
  "maxTokens": 1000
}
```

### Memory налаштування

- **Тип:** Buffer Window
- **Розмір вікна:** За замовчуванням
- **Збереження контексту:** Автоматично

## 🔧 Розширення

Для додавання нових інструментів до агента:

1. Створіть новий вузол типу `agentTool`
2. Підключіть його до вузла "AI Agent"
3. Налаштуйте параметри інструменту

## 🐛 Вирішення проблем

### Поширені помилки

| Помилка | Рішення |
|---------|---------|
| API ключ не працює | Перевірте правильність OpenAI API ключа |
| Workflow не активується | Переконайтеся, що всі залежності встановлені |
| Пам'ять не працює | Перевірте підключення Memory вузла |

## 📝 Ліцензія

MIT License - дивіться [LICENSE](LICENSE) файл для деталей.

## 🤝 Внесок у проект

1. Fork проект
2. Створіть feature branch (`git checkout -b feature/amazing-feature`)
3. Commit зміни (`git commit -m 'Add amazing feature'`)
4. Push до branch (`git push origin feature/amazing-feature`)
5. Відкрийте Pull Request

## ⭐ Підтримка

Якщо проект був корисним, поставте зірочку ⭐

---

**Зроблено з ❤️ для спільноти n8n**
