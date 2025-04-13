# AI Writing Assistant

This project is an **AI Writing Assistant** that uses Groq's API to summarize and rewrite text, checks for basic plagiarism, and saves the writing history in a SQLite database. It helps users improve their writing by providing concise summaries, professional rewrites, and plagiarism detection.

## Features
- **Summarize Text**: Generate concise summaries of input paragraphs using Groq's API.
- **Rewrite Text**: Rewrite paragraphs in a clearer, more professional tone.
- **Basic Plagiarism Check**: Detect common phrases that might indicate plagiarism.
- **Save Writing History**: Store original text, summaries, and rewritten versions in a SQLite database.
- **View History**: Retrieve and display past writing records with timestamps.

## Prerequisites
To run this project, you need:
- Python 3.6 or higher
- A Groq API key (Obtain from [https://console.groq.com/keys](https://console.groq.com/keys))
- Required Python libraries: `requests`, `sqlite3` (included in Python), `datetime`, `time`

## Installation
1. **Clone the Repository** (if applicable):
   ```bash
   git clone <repository-url>
   cd <repository-name>
2. Install Dependencies: Install the required Python library requests using pip:
   pip install requests
4. Set Up Your Groq API Key:
5. Replace "আপনার API কী" in the code with your actual Groq API key:

GROK_API_KEY = "your_groq_api_key"
You can obtain your API key from https://console.groq.com/keys.
## Usage
Run the Script: Execute the Python script to start the AI Writing Assistant:
bash

##  python ai_writing_assistant.py
Interact with the Assistant:
The script will prompt you to enter a paragraph:

🧠 Welcome to AI Writing Assistant (Powered by Groq)!
✍️ Enter your paragraph:
Input your text (e.g., "Education is the key to success in life.") and press Enter.
View Results: The assistant will:
Generate a summary of your text.
Rewrite your text in a professional tone.
Check for basic plagiarism.
Save the results to a SQLite database (writing_history.db).
Display the summary, rewritten text, and plagiarism report:

🔍 Generating summary...
📚 Summary: Education is essential for achieving success in life.
🔁 Rewriting for clarity...
🔁 Rewritten: Education serves as the fundamental pathway to achieving success in life.
🕵️ Checking basic plagiarism...
⚠️ Plagiarism Report: ⚠️ Possible Plagiarism Detected in these lines:
Education is the key to success
✅ Writing saved to your personal history.
View Writing History (Optional):
Uncomment the show_history() call at the end of the script to view all saved writing records:

This will display all past entries with timestamps.
Code Structure
## API Integration:
Uses Groq's API (https://api.groq.com/openai/v1/chat/completions) with the llama3-8b-8192 model for summarization and rewriting.
Includes a retry mechanism to handle rate limit errors (429 Too Many Requests).
## Functions:
summarize_text(): Summarizes input text.
rewrite_text(): Rewrites text in a professional tone.
check_basic_plagiarism(): Checks for common phrases that might indicate plagiarism.
save_to_db(): Saves results to a SQLite database.
show_history(): Displays writing history.
ai_writing_assistant(): Main function to run the assistant.
## Database
The script creates a SQLite database named writing_history.db.
It contains a table writings with the following columns:
id: Auto-incremented primary key.
input_text: Original input text.
summary: Summarized text.
rewritten_text: Rewritten text.
timestamp: Date and time of the entry.
## Limitations
Plagiarism Checker: The plagiarism detection is basic and only checks for a predefined list of common phrases.
Rate Limits: Groq's API has rate limits (e.g., 1 request/second, 60 or 1200 requests/hour depending on the model). The script includes a retry mechanism to handle rate limit errors.
Model Dependency: The script uses the llama3-8b-8192 model. Check Groq's documentation for other supported models if needed.
Troubleshooting
## API Key Error:
If you get a 401 Unauthorized error, ensure your Groq API key is correct. Generate a new key from https://console.groq.com/keys if needed.
Rate Limit Error:
If you encounter a 429 Too Many Requests error, the script will automatically retry after a delay. If the issue persists, contact Groq to increase your rate limit.
Model Error:
If the llama3-8b-8192 model is unavailable, check Groq's documentation for supported models and update the model field in the payload.
Contributing
Feel free to fork this repository, make improvements, and submit pull requests. Suggestions for enhancing the plagiarism checker or adding new features are welcome!

## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgments
Powered by Groq's API for AI-driven text processing.
Built with Python and SQLite for lightweight database storage.

