# CV_Chatbot
An AI-powered interactive digital CV and portfolio assistant built with Gradio. It parses my resume, chats with potential employers       │ or clients on my behalf, and sends me real-time push notifications when visitors leave their contact info or ask questions it can't answer.

This repository contains `app.py`, an interactive AI chatbot designed to act as my digital representative on my portfolio website. Built using    
  **Gradio** and **OpenAI's SDK** (routed through Google's Gemini API), the app provides an engaging, conversational way for recruiters, clients,     
  and visitors to learn about my background, skills, and experience.

  **Automated CV Parsing:** Dynamically reads and extracts context from my resume PDF (`my_cv/Nayan_Sonune_CV_Updated2.pdf`) to ground the AI's   
  knowledge.
    * **Persona-Driven Chat:** The assistant acts in character as me, providing professional and accurate answers about my career trajectory.
    * **Lead Generation via Tool Calling:** Uses AI function calling to automatically collect a user's email address and notes if they are
  interested in getting in touch.
    * **Knowledge Gap Tracking:** Uses function calling to record any questions visitors ask that the AI doesn't know the answer to, allowing me to   
  update its context later.
    * **Real-Time Push Notifications:** Integrates with the **Pushover API** to instantly alert my phone whenever a visitor leaves their contact      
  details or asks an unknown question.

  **Tech Stack:**
  **Python**
    * **Gradio** (for the chat interface)
    * **OpenAI SDK / Gemini API** (for LLM orchestration and Tool Calling)
    * **PyPDF** (for document parsing)
    * **Pushover API** (for mobile push notifications)  
