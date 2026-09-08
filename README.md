# CV_Chatbot
An AI-powered interactive digital CV and portfolio assistant built with Gradio. It parses my resume, chats with potential employers or clients on my behalf, and sends me real-time push notifications when visitors leave their contact info or ask questions it can't answer.

This repository contains `app.py`, an interactive AI chatbot designed to act as my digital representative on my portfolio website. Built using    
  **Gradio** and **OpenAI's SDK** (routed through Google's Gemini API), the app provides an engaging, conversational way for recruiters, clients,     
  and visitors to learn about my background, skills, and experience.

  **Automated CV Parsing:** Dynamically reads and extracts context from my resume PDF (`my_cv/Nayan_Sonune_CV_Updated2.pdf`) to ground the AI's knowledge.
  
  **Persona-Driven Chat:** The assistant acts in character as me, providing professional and accurate answers about my career trajectory.
  
  **Lead Generation via Tool Calling:** Uses AI function calling to automatically collect a user's email address and notes if they are interested in getting in touch.
  
  **Knowledge Gap Tracking:** Uses function calling to record any questions visitors ask that the AI doesn't know the answer to, allowing me to update its context later.
  
  **Real-Time Push Notifications:** Integrates with the **Pushover API** to instantly alert my phone whenever a visitor leaves their contact details or asks an unknown question.

# How it works
1.My CV (PDF) is parsed at startup and injected into the system prompt as the model's only source of truth

2.Every visitor message goes through an agent loop: the model can either reply directly or call one of the two tools above — the loop keeps running until the model produces a final text reply

3.Tool calls are executed locally and their results are fed back to the model so it can continue the conversation naturally

4.Notifications for unknown questions / new leads are pushed to my phone instantly via pushover

# Setup Pushover for Notifications
Pushover is a nifty tool for sending Push Notifications to your phone.

It's super easy to set up and install!

Simply visit https://pushover.net/ and click 'Login or Signup' on the top right to sign up for a free account, and create your API keys.

Once you've signed up, on the home screen, click "Create an Application/API Token", and give it any name (like Agents) and click Create Application.

Then add 2 lines to your `.env` file:

PUSHOVER_USER=_put the key that's on the top right of your Pushover home screen and probably starts with a u_  
PUSHOVER_TOKEN=_put the key when you click into your new application called Agents (or whatever) and probably starts with an a_

Remember to save your `.env` file, and run `load_dotenv(override=True)` after saving, to set your environment variables.

Finally, click "Add Phone, Tablet or Desktop" to install on your phone.

 # **Tech Stack:**
  
  **Python**
  **Gradio** (for the chat interface)
  **OpenAI SDK / Gemini API** (for LLM orchestration and Tool Calling)
  **PyPDF** (for document parsing)
  **Pushover API** (for mobile push notifications)  
