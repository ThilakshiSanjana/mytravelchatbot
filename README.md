# LankaTravelMate - Chatbot Project

![Description of Pictures](C:\Users\User\Desktop\images_chatbot)

Welcome to the **LankaTravelMate Chatbot**\! This project provides an interactive chatbot to help you with travel information in Sri Lanka, including details on destinations, hotels, and transportation. This guide will walk you through the setup and usage of the application.

-----

## 🚀 Getting Started

To get started, you'll need to download the project and set up your local environment.

### ⬇️ Download the Project

1.  Visit the GitHub repository.
2.  Click on the green **"Code"** button and select **"Download ZIP"**.
3.  Extract the downloaded `ZIP` file to a location on your computer.

### ⚙️ Environment Setup

Make sure you have the following prerequisites installed:

  * **Python** (version 3.8 or later)
  * **SQLite**
  * A suitable IDE (e.g., **Visual Studio Code**)

Next, install the required Python libraries. Open your terminal or command prompt, navigate to the project directory, and run the following command:

```bash
pip install flask nltk sqlite3
```

Finally, download the necessary NLTK packages by running the Python interpreter and executing these commands:

```python
import nltk
nltk.download('punkt')
nltk.download('wordnet')
```

-----

## 🗂️ Project Structure

The project directory contains several key files and folders:

  * `app.py`: The main Flask web application.
  * `chatbot_engine.py`: Handles processing user queries.
  * `db_manager.py`: Manages all database operations.
  * `learning.py`: Captures and logs unknown questions.
  * `text_processing.py`: Cleans and processes text input.
  * `LankaTravelMate.sql`: The SQLite database file.
  * `static/`: Contains frontend assets like CSS and JavaScript.
  * `templates/`: Holds the `index.html` file.

-----

## 🛠️ Database Configuration

Before launching the chatbot, you need to set up the database.

1.  Ensure the `LankaTravelMate.sql` file is in the root project directory.
2.  Open your terminal and navigate to the project folder.
3.  Launch SQLite by typing:
    ```bash
    sqlite3 LankaTravelMate.sql
    ```
4.  If the database is not initialized, run the following command to create the tables:
    ```sql
    .read LankaTravelMate.sql
    ```
5.  Verify the tables were created successfully with:
    ```sql
    .tables
    ```
6.  Exit SQLite by typing `.exit`.

-----

## 🚀 Launching the Chatbot

With the database ready, you can now launch the Flask server.

1.  From the project root directory in your terminal, run the command:
    ```bash
    python app.py
    ```
2.  The server will start and display a message indicating it's running at **`http://127.0.0.1:5000/`**.
3.  Open your web browser and navigate to this address to access the chatbot.

-----

## 🤖 How to Use

Simply type your queries in the chat window using natural language. The chatbot can answer questions like:

  * "Show me hotels in Kandy"
  * "Tell me about Sigiriya"
  * "How to travel from Colombo to Galle?"

The chatbot uses **Natural Language Processing (NLP)** to understand your requests and provide relevant information about Sri Lankan travel.

-----

## 📈 Learning and Improvements

When the chatbot encounters a question it doesn't know, it automatically logs the query into the database for future training. This allows developers to review unanswered questions and periodically update the knowledge base to improve the chatbot's performance over time.

-----

## 🗺️ Integrating Google Maps API (Optional)

For developers who want to add map functionality, you can integrate the Google Maps API.

1.  Create a project on the **Google Cloud Console**.
2.  Enable the **Google Maps JavaScript API**.
3.  Generate an **API key**.
4.  Open `index.html` and replace the placeholder in the script source URL with your actual key:

<!-- end list -->

```html
<script src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY_HERE&callback=initMap" async defer></script>
```

-----

## 🩹 Troubleshooting

Encountering an issue? Try these quick fixes:

  * **`Flask` is not recognized:** Reinstall it using `pip install flask`.
  * **NLP errors:** Ensure all required NLTK packages are downloaded.
  * **Chatbot won't load:** Verify `app.py` is running. If port 5000 is in use, launch on a different port:
    ```bash
    flask run --port=5001
    ```
