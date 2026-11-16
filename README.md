# AI Powered News Summarizer

An AI-powered news automation workflow built using **n8n, Google Gemini, NewsAPI, and Gmail**. It allows users to retrieve recent news articles, generate concise AI-powered summaries, and receive formatted news briefings directly through email.

## Overview

The AI Powered News Summarizer is designed to automate the process of collecting and summarizing news.

Users can interact with the workflow through a chat interface to request news from different categories or specific topics. The AI Agent processes the request, retrieves relevant articles using NewsAPI, summarizes the available information using Google Gemini, and can send the results to the user's email through Gmail.

## Features

- **Conversational Interface:** Interact with the news assistant using natural language.
- **AI-Powered Summarization:** Uses Google Gemini to generate concise summaries of retrieved articles.
- **Dynamic News Retrieval:** Fetch news based on categories and specific search keywords.
- **Multiple News Categories:** Supports technology, business, entertainment, health, science, sports, and general news.
- **Custom Article Count:** Retrieve a requested number of articles, with five articles as the default.
- **Email Automation:** Send formatted news briefings directly to an email address.
- **Greeting Recognition:** Responds to basic greetings without unnecessarily fetching news.
- **Automated Workflow:** Connects news retrieval, summarization, and email delivery in one workflow.

## Technologies Used

| Technology | Purpose |
|---|---|
| n8n | Workflow automation |
| Google Gemini | AI model and summarization |
| NewsAPI | News article retrieval |
| Gmail API | Automated email delivery |
| HTTP Request | API communication |
| AI Agent | Request processing and tool orchestration |
| Simple Memory | Conversation context |

## Workflow Architecture

The workflow follows this sequence:

1. **Chat Trigger:** Receives the user's message.
2. **AI Agent:** Understands the request and decides which tools are required.
3. **Google Gemini:** Processes requests and generates article summaries.
4. **NewsAPI:** Retrieves news articles based on the selected category, keyword, and article count.
5. **Gmail:** Sends the formatted news briefing when email delivery is requested.

### Workflow Diagram

```text
             User Chat
                 |
                 v
           Chat Trigger
                 |
                 v
              AI Agent
                 |
        +--------+--------+
        |                 |
        v                 v
     getNews           sendMail
        |                 ^
        v                 |
     NewsAPI               |
        |                 |
        v                 |
   Gemini Summarization --+
        |
        v
   Chat Response
```

## Example Usage

### 1. Retrieve News

**User:**
"Show me the latest 5 technology news headlines."

The workflow retrieves five technology-related articles and generates concise summaries.

### 2. Search Specific Topics

**User:**
"Fetch the latest artificial intelligence news."

The workflow uses the technology category and the specific search keyword to retrieve relevant articles.

### 3. Email News Briefing

**User:**
"Fetch 5 technology news articles and email them to example@gmail.com."

The workflow:
1. Retrieves the requested articles.
2. Summarizes the available articles.
3. Generates a professionally formatted HTML email.
4. Sends the briefing through Gmail.

### 4. General Conversation

**User:**
"Hi"

The assistant responds conversationally without invoking the news retrieval or email tools.

## Setup and Installation

### Prerequisites

Before importing the workflow, you need:

- An n8n account or self-hosted n8n instance.
- A Google Gemini API key.
- A NewsAPI API key.
- A Gmail account with OAuth2 authorization configured in n8n.

### Installation Steps

1. Clone or download this repository.
2. Open your n8n instance.
3. Import `AI-News-Summarizer-GitHub.json`.
4. Configure your Google Gemini API credentials.
5. Configure your NewsAPI HTTP Header Auth credentials.
6. Connect your Gmail OAuth2 account.
7. Verify the node connections and test the workflow.

**Important:** Credentials are not included in the exported workflow. You must configure your own API keys and Gmail authorization.

## Security

- API keys and authentication credentials should never be committed to GitHub.
- Use n8n's credential management system to store sensitive information.
- Configure your own credentials after importing the workflow.

## Future Improvements

- Support for additional news sources.
- Personalized news categories and preferences.
- Scheduled daily news briefings.
- Improved article filtering and relevance ranking.
- Support for additional email providers.

## Author

**Abhishek Bisht**

GitHub: https://github.com/saarthack

---

*Built using n8n, Google Gemini, NewsAPI, and Gmail.*
