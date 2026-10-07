# 🌤️ CrewAI Weather Assistant

A simple AI-powered weather assistant built with **CrewAI**, **Ollama (Llama 3.2)**, and the **OpenWeather API**.

The user enters a city name, and the CrewAI agent uses a custom Weather Tool to retrieve the current weather information from OpenWeather.

## 🚀 Features

* Accepts a city name from the user
* Uses CrewAI Agent, Task, and Crew
* Uses Ollama with Llama 3.2 as the local LLM
* Retrieves real-time weather information using OpenWeather API
* Displays:

  * Temperature
  * Humidity
  * Weather description
  * Wind speed
* Keeps API keys in environment variables

## 🏗️ Project Architecture

```text
User
  ↓
Enter City
  ↓
CrewAI Task
  ↓
CrewAI Agent
  ↓
Ollama (Llama 3.2)
  ↓
Weather Tool
  ↓
OpenWeather API
  ↓
Weather Information
```

## 🛠️ Technologies Used

* Python 3.11
* CrewAI
* Ollama
* Llama 3.2
* OpenWeather API
* Requests
* python-dotenv

## 📁 Project Structure

```text
Crewai_Weather/
│
├── app.py
├── requirements.txt
├── README.md
├── .env
└── .gitignore
```

> `.env` should remain local and must not be uploaded to GitHub.

## ⚙️ Prerequisites

Before running the project, install:

1. Python 3.11
2. Ollama
3. Llama 3.2 model
4. An OpenWeather API key

Check Ollama:

```bash
ollama --version
```

Check installed models:

```bash
ollama list
```

If Llama 3.2 is not installed:

```bash
ollama pull llama3.2
```

## 📦 Installation

Clone the repository:

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

Go into the project directory:

```bash
cd Crewai_Weather
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

Install the required Python packages:

```bash
pip install -r requirements.txt
```

## 🔑 Environment Variables

Create a `.env` file in the project directory:

```text
OPENWEATHER_API_KEY=your_openweather_api_key
```

Replace `your_openweather_api_key` with your actual OpenWeather API key.

**Never commit your `.env` file to GitHub.**

## ▶️ Run the Project

Make sure Ollama is running and Llama 3.2 is available.

Then run:

```bash
python app.py
```

The application will ask:

```text
Enter the city name:
```

For example:

```text
Enter the city name: Mumbai
```

The agent will retrieve the current weather information and display the result.

## 💡 Example Output

```text
FINAL RESULT:

City: Mumbai
Temperature: 29 °C
Humidity: 70%
Weather: broken clouds
Wind Speed: 4.2 m/s
```

The actual values will change because the application retrieves current weather data from OpenWeather.

## 🧠 How It Works

### 1. Ollama / Llama 3.2

Ollama runs the Llama 3.2 model locally on the computer.

```python
llm = LLM(
    model="ollama/llama3.2",
    base_url="http://localhost:11434"
)
```

### 2. Weather Tool

The custom CrewAI tool sends a request to OpenWeather:

```text
Weather Tool
     ↓
OpenWeather API
     ↓
Current Weather Data
```

### 3. Agent

The CrewAI agent is responsible for using the Weather Tool to obtain the requested information.

### 4. Task

The task tells the agent what it needs to accomplish.

The city is provided dynamically by the user.

### 5. Crew

The Crew coordinates the agent and task and executes the workflow.

## 🔐 Security

Never upload API keys or other secrets to GitHub.

The following file is intentionally excluded:

```text
.env
```

If an API key is accidentally exposed publicly, revoke/rotate that key and create a new one.

## 📚 What I Learned

This project demonstrates the basic CrewAI architecture:

```text
LLM
 ↓
Agent
 ↓
Task
 ↓
Crew
 ↓
Tool
 ↓
External API
```

It also demonstrates how a local LLM such as Llama 3.2 can be used with CrewAI instead of a cloud LLM provider.

## 🔮 Future Improvements

* Add support for weather forecasts
* Add multiple weather tools
* Add temperature conversion
* Add weather alerts
* Add a web interface
* Add conversation history
* Improve error handling
* Allow multiple cities in one request

## 👩‍💻 Author

**Vishala**

Built as a learning project to understand CrewAI, local LLMs, tools, agents, and API integration.