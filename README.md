# Financial Data Extractor using Langchain and Groq LLM

## Overview

This web application, built with Streamlit, utilizes a Langchain template and the Groq large language model (LLM) to extract key financial data points (Revenue and Earnings Per Share - EPS) from news articles. The application takes text from a news article as input and returns the estimated and actual values for Revenue and EPS in a structured format.

## Functionality

The core functionality of this application is to:

1.  **Accept News Article Text:** Users can input the text content of a news article into the application.
2.  **Extract Financial Data:** The application uses a Langchain prompt template and the Groq LLM to identify and extract the reported (actual) and potentially forecasted (estimated) revenue and EPS figures mentioned in the article.
3.  **Present Data:** The extracted data is then displayed in a clear table format within the Streamlit application, showing the "Measure," "Estimated" value, and "Actual" value.

## Technical Details

This project leverages the following key technologies:

* **Streamlit:** An open-source Python library used to create the interactive web application, providing the user interface for input and output.
* **Langchain:** A framework designed to simplify the creation of applications using large language models. In this project, Langchain is used for:
    * **Prompt Templating:** Defining a structured prompt that guides the Groq LLM to extract the specific financial information.
    * **Chaining:** Connecting the prompt template with the Groq LLM to form an execution pipeline.
    * **Output Parsing:** Using `JsonOutputParser` to ensure the LLM's response is structured as a JSON object for easy processing.
* **Groq LLM:** The application utilizes the `llama-3.3-70b-versatile` model from Groq for its natural language understanding and information extraction capabilities.

## Usage

To use the application deployed at [https://langchaintemplate.streamlit.app/](https://langchaintemplate.streamlit.app/):

1.  Navigate to the provided URL in your web browser.
2.  Locate the input area where you can paste the text content of a news article.
3.  Paste the news article text into the input field.
4.  The application will process the text and display the extracted financial data (Revenue and EPS) in a table showing the estimated and actual values.

## Code Structure

The project likely contains the following main files:

* `main.py`: This file contains the Streamlit application code, including the user interface elements and the logic to call the data extraction function.
* `data_extractor.py`: This file contains the core logic for extracting the financial data using Langchain and the Groq LLM. It defines the prompt template, initializes the Groq LLM, and processes the input article text.
* `requirements.txt`: This file lists the Python dependencies required to run the application, such as `streamlit`, `langchain`, and `langchain-groq`.

## Environment Variables/Secrets

The application relies on the `GROQ_API_KEY` to authenticate with the Groq API. This API key should be securely managed as a **secret** within the Streamlit Cloud application settings. It is accessed in the code using `st.secrets["GROQ_API_KEY"]`.

## Dependencies

The required Python libraries for this project are listed in the `requirements.txt` file. Ensure these dependencies are installed in your environment if you are running the application locally or when deploying to a platform other than Streamlit Cloud.
