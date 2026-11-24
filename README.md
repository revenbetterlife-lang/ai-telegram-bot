# AI Telegram Bot

An AI-powered Telegram bot built as an n8n workflow: it receives messages on Telegram, answers them with Google Gemini, and sends the reply back automatically.

## The workflow

1. **Telegram Trigger** - receives every new message sent to the bot.
2. **Ask Gemini** - sends the message text to the Gemini API.
3. **Build Reply** - a Code node that extracts the answer from the Gemini response and keeps the chat id.
4. **Send Reply (Telegram)** - sends the AI answer back to the same chat.

## Setup

1. Create a bot with [@BotFather](https://t.me/BotFather) on Telegram and copy the bot token.
2. Import `workflow.json` into n8n (Workflows, Import from File).
3. Add a Telegram credential in n8n with the bot token, and select it on both Telegram nodes (replacing the `PASTE_CREDENTIAL_ID` placeholders).
4. Add a Gemini API key from [Google AI Studio](https://aistudio.google.com/) as a Query Auth credential (parameter `key`) and select it on the "Ask Gemini" node.
5. Activate the workflow and send your bot a message.

## Notes

- No real tokens or API keys are included in this repo; they stay in your own n8n credential store.
- Built with n8n, the Telegram Bot API, and the Google Gemini API.
- A natural next step is an AI Agent node with memory so the bot keeps context across messages.
