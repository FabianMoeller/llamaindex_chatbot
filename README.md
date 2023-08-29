# LLamaIndex Chatbot

This repository contains code that implements a chatbot using the LLamaIndex library and the Streamlit framework. The chatbot is designed to provide responses to user questions related to a specified topic within a given set of documents. It utilizes the OpenAI GPT-3.5 model to generate informative responses.

## Prerequisites

Before running the code, ensure you have the following components set up:

1. **Python Environment:** Make sure you have Python installed (recommended version 3.6 or later).

2. **LLamaIndex and Streamlit Libraries:** You need to have the LLamaIndex and Streamlit libraries installed. You can install them using the following command:
   ```
   pip install llama_index streamlit
   ```
OR you just take use of the requirements.txt

3. **OpenAI API Key:** You need an OpenAI API key to use the GPT-3.5 model. If you don't have one, you can sign up for access on the openai website.

4. **`secrets.toml` File:** For added security, create a `secrets.toml` file in the directory .streamlit/secrets.toml. Add your OpenAI API key to this file as follows:
   ```toml
   [openai]
   api_key = "YOUR_OPENAI_API_KEY"
   ```

## Getting Started

1. Clone the repository or download the code files to your local machine.

2. Open the code file named `main.py` in your preferred code editor.

3. Prepare your data:
   - Organize your documents into subfolders inside the `data` directory. Each subfolder represents a specific topic that the chatbot will respond to.

4. Customize the system prompt (assistant's initial message) as needed:
   ```python
   service_context = ServiceContext.from_defaults(
       llm=OpenAI(
           model="gpt-3.5-turbo",
           temperature=0.5,
           system_prompt="Your system prompt here."
       )
   )
   ```

## Running the Chatbot

1. Open a terminal and navigate to the directory containing the `main.py` file.

2. Run the Streamlit app using the following command:
   ```
   streamlit run main.py
   ```

3. Your default web browser should automatically open and display the chatbot interface.

4. Select a topic from the dropdown menu corresponding to the subfolders you created within the `data` directory.

5. Start interacting with the chatbot by typing your questions in the input field and pressing Enter.

6. The chat history will display your messages and the chatbot's responses. The chatbot will generate responses based on the selected topic and the context provided.

## Additional Notes

- The chatbot utilizes LLamaIndex to index and search the documents within the selected topic. The `VectorStoreIndex` is constructed from the documents, and the `chat_engine` handles generating responses.

- The chatbot is designed to continue generating responses until the user switches to another topic or closes the application.

- For additional data in the chatbot, paste your documents into the relevant subfolders within the `data` directory.

- To fully utilize the script, ensure your `secrets.toml` file contains your valid OpenAI API key.

- If you encounter any issues, refer to the LLamaIndex and Streamlit documentation for troubleshooting.

---

Please note that this README provides a basic overview of the chatbot implementation. For more advanced customizations and integration options, consider referring to the documentation of the libraries used and exploring the code in the repository.
