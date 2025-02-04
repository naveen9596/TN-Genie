Building an AI-powered bot in **RPA Power App in Microsoft Teams** involves integrating **Power Virtual Agents**, **Power Automate**, and **AI capabilities (Azure AI or OpenAI API)** to create an intelligent chatbot. Below are the steps and necessary code snippets.

---

## **Steps to Build an AI Bot in Power Apps for Microsoft Teams**

### **1. Set Up the Power Virtual Agent in Teams**
1. **Open Microsoft Teams** → Go to **Apps** → Search for **Power Virtual Agents**.
2. Click **Add to a Team** and select the team where you want the bot.
3. Click **Start** to create a chatbot.
4. Define the chatbot **name and topic**.
5. Save and publish the bot.

---

### **2. Configure AI for the Bot**
- **Option 1: Use Azure OpenAI GPT for AI Responses**
- **Option 2: Use Power Automate to integrate AI services**

#### **Option 1: Azure OpenAI GPT**
1. Create an **Azure OpenAI resource** in **Azure Portal**.
2. Get the **API Key** and **Endpoint**.
3. Go to **Power Virtual Agents** → Create a new topic.
4. Add an **HTTP Request** action to call the OpenAI API.

##### **Code to Call OpenAI API**
```json
{
    "method": "POST",
    "url": "https://api.openai.com/v1/completions",
    "headers": {
        "Authorization": "Bearer YOUR_OPENAI_API_KEY",
        "Content-Type": "application/json"
    },
    "body": {
        "model": "gpt-4",
        "prompt": "How can I help you?",
        "max_tokens": 100
    }
}
```

- Replace `YOUR_OPENAI_API_KEY` with your actual OpenAI API Key.
- Save the action and connect it to the chatbot’s response flow.

---

### **3. Use Power Automate for AI Integration**
1. **Go to Power Automate** → Click **Create a Flow**.
2. Select **"When a message is posted in a channel"** trigger.
3. Use the **"Call an HTTP endpoint"** action.
4. Connect it to the Azure OpenAI or Power Automate AI Builder model.
5. **Return the AI response** back to the bot.

##### **Power Automate Example (AI Builder)**
1. **Create a new Flow** → Select **"Power Virtual Agents"**.
2. Add **AI Builder’s Text Processing Model**.
3. Extract key insights from the text and return a response.

---

### **4. Deploy and Test the Bot**
1. Click **Publish** in Power Virtual Agents.
2. Test the chatbot in **Microsoft Teams**.
3. Deploy it to multiple Teams channels.

---

### **5. Automate with RPA (Optional)**
- Use **Power Automate Desktop (RPA)** to automate repetitive tasks.
- Example: A chatbot that fetches employee leave balance from an HR system.
- The bot calls a **Power Automate flow**, which triggers an RPA script.

##### **Example: Fetch Employee Leave Balance**
```powershell
$employeeID = "12345"
$apiURL = "https://hr-system/api/leavebalance"
$response = Invoke-RestMethod -Uri "$apiURL?empID=$employeeID" -Method GET -Headers @{"Authorization"="Bearer YOUR_API_KEY"}
$response.balance
```
- This PowerShell script fetches employee leave details via API.

---

## **Conclusion**
- **Power Virtual Agents** → Create a chatbot.
- **Azure OpenAI API or Power Automate AI Builder** → Add AI intelligence.
- **Power Automate** → Automate responses and workflows.
- **Power Automate Desktop (RPA)** → Automate complex business tasks.

Would you like a hands-on walkthrough for any of these steps? 🚀
