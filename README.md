[![MseeP.ai Security Assessment Badge](https://mseep.net/pr/darinkishore-inbox-mcp-badge.png)](https://mseep.ai/app/darinkishore-inbox-mcp)

# Inbox MCP

Transform your inbox into an intelligent, LLM-powered assistant—**instantly**.

Easily manage, organize, and streamline your email using conversational language, powered by robust, batch-friendly tools built on [Nylas v3](https://nylas.com). Compatible out-of-the-box with Gmail, Outlook, iCloud, Yahoo, and virtually any IMAP service (even your work email!).

Tools are carefully crafted with clear descriptions and consistent parameters optimized for seamless integration with various LLMs. Responses are provided as easily parsable XML blocks, allowing the LLM to effortlessly handle your requests.

Tested extensively in real-life workflows, Inbox MCP significantly reduces cognitive load, efficiently handling tasks you’d rather automate.

Nylas includes **5 free connected accounts**, so you can get started immediately—without spending a dime.

---

## ✨ Real-life examples (things you'll actually say)


| You casually say…                                                                         | Inbox MCP effortlessly handles it by…                                                                 |
| ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| *“take a look at my inbox and LMK what's important and what i have to act on”*            | Reviewing your messages, quickly identifying actionable emails, and summarizing what needs attention. |
| *“Find the unimportant emails from my last 100 and move them to the Unimportant folder.”* | Intelligently filtering out low-priority emails and neatly organizing them out of sight.              |
| *“Archive everything older than two weeks, except starred emails.”*                       | Batch-archiving older emails while safely preserving your starred messages.                           |
| *“Summarize and forward the latest AWS alerts to my team.”*                               | Compiling recent AWS alerts into a concise summary and sending it off immediately.                    |


---

## 🎯 Why use Inbox MCP?

- **Inbox Zero, Simplified:** Quickly automate email management using natural language instructions.
- **Efficient Triage:** Instantly categorize, prioritize, and batch-process emails effortlessly.
- **Easy Setup:** Hassle-free onboarding with direct account connections. No OAuth tokens, proxies, or complex setups.

---

## 📌 Quick Setup: Creating a Nylas Account

1. Sign up at: [Nylas Dashboard](https://dashboard-v3.nylas.com/register?utm_source=docs&utm_medium=devrel-surfaces&utm_campaign=&utm_content=quickstart).
2. Grab your API key from the sidebar (`API KEY`).  
   ![API Key location](api_key_loc.png)
3. Navigate to `Grants`, click `Add Test Grant` (top-right), and connect your email account.  
   ![Grant ID location](grant_loc.png)
4. Note your API key and Grant ID (shown in the grants table).

---

## 🚀 Get started (in under a minute)

### Easy Smithery Installation (Interactive)

Inbox MCP integrates seamlessly with MCP clients like Claude Desktop, Cursor, Windsurf, and more.

**Interactive one-liner installation (recommended):**
```bash
npx -y @smithery/cli@latest install "@darinkishore/inbox-mcp" --client claude
```

This will prompt you for your Nylas credentials (`nylasAccessToken` and `nylasGrantId`). For other supported MCP clients, replace `claude` with your preferred client:

```bash
npx -y @smithery/cli@latest install "@darinkishore/inbox-mcp" --client cursor # or windsurf, vscode, etc.
```

---

## 🛠️ Manual local setup (optional)

If you prefer manual control for local development:

```bash
git clone https://github.com/darinkishore/Inbox-MCP.git
cd Inbox-MCP
npm install && npm run build
```

Then in your MCP client's `mcp-config.json`:

```jsonc
{
  "mcpServers": {
    "nylas-email": {
      "command": "node dist/index.js",
      "workingDirectory": "/absolute/path/to/Inbox-MCP",
      "env": {
        "NYLAS_ACCESS_TOKEN": "...",
        "NYLAS_GRANT_ID": "..."
      }
    }
  }
}
```

---

## 🔧 Daily workflow tools (optimized)

| Tool                             | What it does (in plain English)                                          |
| -------------------------------- | ------------------------------------------------------------------------ |
| **`filter_emails`**              | Find emails quickly by folder, unread status, dates, or flags.           |
| **`triage_update_emails`**       | Batch-update emails as read/unread, starred/unstarred, or move folders.  |
| **`batch_archive_emails`**       | Archive groups of emails safely and quickly.                             |
| **`search_emails`**              | Search emails rapidly with simple keyword queries.                       |
| **`read_emails`**                | Fetch complete emails formatted neatly in Markdown, ideal for summaries. |
| **`send_email` / `draft_email`** | Easily compose and send (or draft) new emails.                           |
| **Folder management tools**      | (`list_`, `create_`, `update_`, `delete_`, `get_or_create_`)             |

---

## 🗺️ Roadmap

- Enhanced provider-native search (advanced queries, multi-term searches)
- Calendar and contacts integration
- Expanded toolset and automation capabilities

---

## 👩‍💻 Developer-friendly

- Clean TypeScript (v5.2), minimal dependencies
- Robust built-in retries (exponential back-off + jitter)
- Contributions warmly welcomed—let's make email management better together!

---

## 📄 License & Support

Licensed under [MIT](LICENSE).

If Inbox MCP makes your day easier, please ⭐️—your star helps others discover it too!