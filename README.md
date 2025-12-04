# LINE & Facebook Social Media Automation (n8n + OpenAI)

This repository documents a social media automation workflow I built using:

- **LINE Messaging API**
- **Facebook Page (Graph API)**
- **n8n (workflow automation)**
- **OpenAI / ChatGPT**

Although the original n8n instance has expired, I recorded a full execution demo on YouTube so the logic and behaviour of the system are still visible.

---

## 🎯 Project Overview

The goal of this project was to **automatically generate and publish social media posts** based on user input.

**High-level flow:**

1. User sends a message to a **LINE bot** (e.g. a topic or short description).  
2. n8n receives the webhook from LINE.  
3. n8n calls **OpenAI / ChatGPT** to:
   - Generate a Facebook-ready post
   - Optionally translate / rephrase / summarise  
4. The generated content is stored (e.g. in a datastore / sheet).  
5. n8n uses the **Facebook Graph API** to post the content to a **Facebook Page**.  
6. n8n sends a confirmation message back to LINE.

This shows how to combine **messaging apps, social media, automation tools and AI** into one end-to-end workflow.

---

## 🧩 Tech Stack

- **LINE Developer**  
  - Messaging API, webhook, channel access token.  
- **Facebook Developer**  
  - App configuration, Page access token, Graph API for Page posts.  
- **n8n**  
  - Webhook trigger, HTTP Request nodes, conditional logic (If / Switch), error handling, data storage nodes.  
- **OpenAI / ChatGPT**  
  - Content generation, natural language processing.  

---

## 📌 Workflow Diagram

![Workflow Diagram](workflow-diagram.png)

---

## 🎥 Demo Video

[📹 Click to watch the full automation demo on YouTube](https://www.youtube.com/watch?v=fQMmORggsjU)

---

## 💡 What I Learned

- How to configure **LINE** and **Facebook** developer credentials & permissions.  
- How to design a **multi-step automation workflow** with branching logic, fallback/error handling, and data persistence.  
- How to integrate **AI-generated content** into real-world processes via APIs.  
- Basics of building a scalable automated backend with minimal maintenance.

---

## 🚀 Possible Future Improvements

- Rebuild the workflow on a self-hosted or cloud n8n instance (since the previous one expired).  
- Add support for multiple platforms (e.g. Instagram, Telegram, email, blog).  
- Add a web dashboard to review and approve generated posts before publishing.  
- Log analytics (post times, engagement, errors) and feed back to improve prompts or workflow logic.

---

## 🧑‍💻 About Me

I’m a junior developer interested in building automation tools, integrating APIs and using AI to support business workflows.  
This project demonstrates my ability to build real-world, end-to-end automated tools — not just isolated scripts.  


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

