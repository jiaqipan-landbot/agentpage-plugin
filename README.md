# AgentPage

AgentPage puts a lead-catching chat on your website, and you set it up by asking Claude. Give Claude your website address and what a good enquiry looks like for your business. AgentPage reads your public pages, builds a chat that answers visitors from them first, then asks for a name and email, and for a phone number only if the visitor wants a call back. It emails you each new lead as soon as the visitor confirms their details, and each day (around 05:00 UTC, after any day with conversations) a short list of who to call back.

## What this plugin contains

- **A skill** (`skills/agentpage`) that tells Claude when to use AgentPage and how to guide you through creating the chat, installing the snippet on your site, checking that it is live, reading your leads, and deleting the chat.
- **A connection to the AgentPage connector** (`.mcp.json`), a remote server at `https://mcp.getagent.page/mcp`.

## What it does when you use it

The plugin contains no scripts, no hooks and no packages, and it runs nothing on your computer. It sends nothing anywhere by itself. When you ask for something, Claude calls AgentPage tools on that connector, and only then is data sent:

- to create or change a chat, the website address, business basics and settings you asked for;
- to list your chats, nothing; to read leads or a report, the chat's ID and a period;
- to delete a chat, its ID and your explicit confirmation;
- AgentPage returns your own chat settings and your own leads. A lead holds details a website visitor chose to give the chat: a name, an email address, a phone number if they asked for a call back, and their message.

In Claude Code, if you ask Claude to add the install snippet to your site, it edits a file in your project folder, and asks for your approval first. The connector itself is operated by AgentPage. It runs the chats on Landbot's platform, which acts as its service provider.

## Getting started

1. In the Claude desktop app or at claude.ai, add AgentPage as a connector and sign in with your email address. There is no password. If AgentPage is in the connectors directory, add it from there.
2. Add this plugin, then start a conversation in Claude Code or Cowork and switch AgentPage on.
3. Ask, for example: "Add a lead-catching chat to my website https://example.com. A good enquiry is someone asking for a quote. Send leads to me@example.com."

### Install this plugin from its repository

If you want the plugin before it appears in the directory, add this repository as a marketplace from a Claude Code session in the desktop app, then install the plugin:

```
/plugin marketplace add jiaqipan-landbot/agentpage-plugin
/plugin install agentpage@agentpage
```

The plugin only guides Claude. The AgentPage connector in step 1 is what does the work.

## Good to know

- AgentPage does not contact your leads. You decide who to call or write to.
- The chat tells every visitor that it is an automated assistant, and that notice cannot be removed.
- A visitor who leaves an email address and then drops off is still emailed to you, about 15 minutes later.
- You can ask Claude which chats you have and whether they are live. It finds your chat itself, so you do not need to keep its ID.
- It works on websites where you can add a snippet of code.
- AgentPage never asks for passwords, API keys or payment card numbers.

## Documentation, privacy and support

- Docs: https://getagent.page/docs
- Privacy policy: https://getagent.page/privacy
- Terms: https://getagent.page/terms
- Support: https://getagent.page/support

## Privacy

The plugin stores nothing. The AgentPage connector keeps account details, chat settings and visitor leads and transcripts (leads and transcripts are deleted after 90 days), and the privacy policy lists every provider it uses. It does not sell data, show advertising, or read your Claude conversations. See the privacy policy above for the full text.

## License

MIT. See `LICENSE`.
