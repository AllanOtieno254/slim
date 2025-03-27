# Simple AI Chatbot using n8n and LLM
![Simple AI Chatbot main workflow](https://github.com/user-attachments/assets/d7b2a098-d73b-4883-8da4-37f378abf7cc)

## Workflow Process and Steps

### Overview
The chatbot workflow in **n8n** is designed to handle user queries efficiently by integrating a Large Language Model (LLM) to process responses. The workflow consists of multiple nodes that work together to automate the chatbot interactions.

### **Step-by-Step Workflow Execution**

#### **1. Trigger Node (Webhook or Chat Input Node)**
- This node acts as the entry point for the chatbot.
- It listens for incoming messages from a chat application, API request, or any other source.
- The received user message is passed to the next node.

#### **2. Memory Node (Optional - Store Previous Conversations)**
- This node stores past interactions with users to maintain conversational context.
- It can be implemented using **Redis, a database, or n8n’s built-in storage**.
- The memory node ensures continuity in responses, especially for multi-turn conversations.

#### **3. AI Agent Node (Processing the User Input)**
- This node processes user queries and structures them for the AI model.
- It may include prompt engineering to guide the chatbot’s behavior.
- Example prompt setting:
  ```json
  {
    "system_message": "You are an AI assistant. Answer all questions accurately."
  }
  ```

#### **4. DeepSeek Chat Model Node (LLM Processing)**
- The processed user input is sent to this node where an LLM like **DeepSeek, OpenAI’s GPT, or another model** generates a response.
- The node requires an **API Key** to connect with the AI service.
- The AI response is then passed to the next node.

#### **5. Response Node (Sending Back the AI Output)**
- This node formats the AI-generated text and sends it back to the user.
- It ensures that the response is clear, structured, and delivered correctly via the chat interface.

#### **6. Logging & Monitoring Node (Optional - Store Chat Data)**
- This node logs conversation history for future reference or analytics.
- It can store interactions in a **database, Google Sheets, or a logging service**.

---

# Features
✅ **Automated chatbot responses** powered by an LLM  
✅ **n8n workflow** for seamless automation  
✅ **Memory retention** to recall past interactions  
✅ **Customizable AI prompts** for different use cases  
✅ **Scalable and extendable** for advanced functionalities  

---

# Prerequisites
Before setting up this chatbot, ensure you have the following installed:  
- **n8n** (self-hosted or cloud version)  
- **Node.js** (v16+ recommended)  
- **Docker** (optional, for containerized deployment)  
- **API key** for the LLM (OpenAI, DeepSeek, etc.)  
- **Basic knowledge of n8n workflows**  

---

# Installation

## **1. Install n8n**  
You can install n8n globally on your system:  
```sh
npm install -g n8n
```
Or run it using Docker:  
```sh
docker run -it --rm -p 5678:5678 n8nio/n8n
```

## **2. Start n8n**  
Run the following command to start n8n:  
```sh
n8n start
```
Access the n8n UI at **`http://localhost:5678`**  

---

# Project Workflow

The chatbot workflow consists of the following key components:

1. **Trigger Node:** Captures user input  
2. **AI Agent Node:** Processes messages using an LLM  
3. **Memory Node:** Stores conversation history  
4. **DeepSeek Chat Model Node:** Calls the AI model to generate responses  
5. **Response Node:** Sends replies back to the user  

![Workflow Diagram](Simple%20AI%20Chatbot%20main%20workflow.png)  

---

# How It Works

1. A **chat message is received** via a trigger (e.g., webhook, chat app, API).  
2. The **AI Agent** processes the input and manages memory.  
3. The **DeepSeek Chat Model** (or any LLM) generates a response.  
4. The **response is stored** in memory and returned to the user.  

---

# Configuration

To configure the chatbot, update the **AI Agent Node** settings:

- **System Message:** Define AI behavior and instructions
- **Memory Storage:** Enable session-based memory
- **API Key:** Add the LLM provider’s API key

Example system message:
```json
{
  "system_message": "You are an expert AI assistant. Answer all user queries clearly, accurately, and concisely."
}
```

---

# Usage

## **1. Run the Chatbot**  
Start the chatbot by activating the n8n workflow.  

## **2. Send a Message**  
Use the integrated chat interface or API endpoint to send a query.  

## **3. Get an AI Response**  
The chatbot will return an intelligent response based on your input.  

---

# Troubleshooting

## **1. AI Model Not Responding**  
- Ensure your API key is valid.  
- Check if the LLM service is operational.  

## **2. Memory Not Retaining Conversations**  
- Verify the memory node configuration in n8n.  
- Use a database integration for persistent memory.  

---

# Customization

🔹 **Integrate with WhatsApp, Telegram, or Slack** for real-time AI conversations.  
🔹 **Modify the system message** to change the AI’s personality.  
🔹 **Enhance memory retention** by using databases like PostgreSQL.  

---

# Future Improvements

🚀 **Multi-turn conversations** with enhanced context awareness  
🚀 **Voice-to-text integration** for spoken queries  
🚀 **Sentiment analysis** to adjust response tone  
🚀 **Advanced AI models** like GPT-4 or Claude  

---

# Contributing

Want to improve this chatbot?

1. Fork this repository.  
2. Create a feature branch.  
3. Submit a pull request with your changes.  

---

# License
This project is licensed under the **MIT License**.  

---
