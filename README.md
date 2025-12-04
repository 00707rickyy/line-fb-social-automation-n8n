# LINE & Facebook Social Media Automation (n8n + OpenAI)
This repository documents a social media automation workflow I built using:
- **LINE Messaging API**
- **Facebook Page (Graph API)**
- **n8n (workflow automation)**
- **OpenAI / ChatGPT**
Although the original n8n instance has expired, I recorded a full execution demo on YouTube so the logic and behaviour of the system are still visible.

## 🎯 Project Overview

The goal of this project was to **automatically generate and publish social media posts** based on user input.

**High-level flow:**

1. User sends a message to a **LINE bot** (e.g. a topic or short description).
2. n8n receives the webhook from LINE.
3. n8n calls **OpenAI / ChatGPT** to:
   - Generate a social media post
   - Optionally translate / rephrase / summarise
4. The generated content is stored (e.g. in a datastore / sheet).
5. n8n uses the **Facebook Graph API** to post the content to a **Facebook Page**.
6. n8n sends a confirmation message back to LINE.

This shows how to combine **messaging apps, social media, automation tools and AI** into one end-to-end workflow.
---

## 🧩 Tech Stack

- **LINE Developer**
  - Messaging API
  - Webhook / channel access token

- **Facebook Developer**
  - App configuration
  - Page access token
  - Facebook Graph API (Page posts)

- **n8n**
  - Webhook trigger
  - HTTP Request nodes
  - If / Switch / Error handling
  - Datastore or Google Sheet nodes
  - OpenAI / ChatGPT node

- **OpenAI / ChatGPT**
  - Content generation and rewriting

---

## 🔁 Workflow Design

Key steps inside the n8n workflow:

1. **Webhook (LINE)**
   - Receives user message and metadata (user ID, timestamp, text).

2. **Pre-processing**
   - Clean / normalise the message.
   - Optional: detect command type (e.g. “news post”, “promotion”, “general question”).

3. **OpenAI / ChatGPT Node**
   - Prompted with:
     - User message
     - Desired style (e.g. friendly / marketing / concise)
     - Language (Traditional Chinese)
   - Returns a suggested Facebook / LINE post.

4. **Data Storage**
   - Save:
     - Original user input
     - AI-generated text
     - Timestamps
     - Status (posted / pending)
   - Can be a Datastore in n8n or an external sheet/database.

5. **Facebook Page Post**
   - HTTP Request / dedicated node to call the **Graph API**.
   - Uses Page access token.
   - Publishes the generated text to the Page.

6. **Reply to LINE**
   - Sends a confirmation message back to the user:
     - e.g. “Your post has been published” or error message if failed.

7. **Error Handling**
   - If Facebook / OpenAI call fails:
     - Log the error
     - Send a friendly error message back to LINE
     - Keep the data for debugging
## 📌 Workflow Diagram

![Workflow Diagram](workflow-diagram.png)

---

## 🎥 Demo Video

A full run-through of the workflow (from LINE message to Facebook post) is available on YouTube:

👉 **Demo:** (https://www.youtube.com/watch?v=fQMmORggsjU)

This video shows:

- How the user interacts with the LINE bot  
- How n8n processes the message  
- How the Facebook Page post is created automatically  

---

## 💡 What I Learned

- How to configure **LINE** and **Facebook** developer settings (tokens, webhooks, permissions).
- How to design a **multi-step automation** in n8n, including:
  - Branching logic (If / Switch)
  - Error handling
  - Storing and reusing data across nodes
- How to integrate **OpenAI / ChatGPT** into a real workflow to generate useful content.
- How to debug issues related to:
  - Missing or expired tokens
  - Incorrect event types
  - Data structure mismatches between services

---

## 🚀 Possible Future Improvements

- Rebuild the workflow on a self-hosted n8n instance.
- Add support for more platforms (e.g. Instagram, Telegram, email).
- Add a simple web dashboard to review and approve posts before publishing.
- Log analytics (clicks / engagement) and feed back into the content generation prompts.

---

## 🧑‍💻 About Me

I am a junior candidate interested in:

- Automation and workflow tools (n8n, APIs, webhooks)  
- AI-assisted content generation  
- Integrating business processes with technical tools  

This project is part of my portfolio to demonstrate how I approach **real, end-to-end automation problems** instead of only writing isolated scripts.

