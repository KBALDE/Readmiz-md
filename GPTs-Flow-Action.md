# GPTs Flow and Action

GPTs provide the ability to deeply customize ChatGPT for specific use cases along with custom capabilities. You can create a GPT that:

- Has custom ``instructions`` which determine the way the GPT interacts with users
- Includes tools like browsing, DALL·E, and Code Interpreter
- Comes with preset starter prompts for new and returning users
- Has custom ``actions`` which allow you to connect the GPT to APIs


**Actions** allow GPTs to integrate external data or interact with the real-world, such as connecting GPTs to ``databases, plugging them into your emails, or making them your shopping assistant, all through APIs``.


## GPT action flow
To build a GPT with an action, it is important to understand the end-to-end flow.


1.	**Create a GPT in the ChatGPT UI**

- Manually configure or use the GPT builder to create a GPT
- Identify the API(s) you want to use

2. Go to the "**Configure**" tab in the GPT editor and select "Create new action"

- You will be presented with 3 main options: selecting the authentication schema for the action, inputting the schema itself, and setting the privacy policy URL.

- The Schema follows the **OpenAPI specification format** (not to be confused with OpenAI) to define how the GPT can access an external API.


3. Fill in the details for the schema, authentication, and privacy policy.
- When selecting an authentication method, you will have 3 options, "None", "API Key", and "OAuth".
- For the schema, you can take an existing OpenAPI specification you have for your API or create a new one. If you have already published an OpenAPI specification online, you can import it via the "Import from URL" button.
- The privacy policy URL is displayed to the user when they open a GPT and select the drop down in the top left corner showing the name of the GPT.

4. Determine the **visibility of your GPT**
-  By default, GPTs are not accessible to everyone
-  When you go to save a GPT, you will have the option to "Publish to" a certain audience: "Only me", "Anyone with a link", or "Everyone".
