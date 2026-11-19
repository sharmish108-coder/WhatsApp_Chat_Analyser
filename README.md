# WhatsApp Chat Analyser

**LINK: https://sriiwhatsappchatanalyser.streamlit.app/**

A Streamlit-based WhatsApp chat analytics dashboard that turns an exported WhatsApp `.txt` chat into useful conversation insights. Upload a chat export, choose a participant or analyse the complete conversation, and explore messaging patterns through useful metrics and visualisations.

## Features

* **Overall or individual analysis** — analyse the full conversation or a specific participant.
* **Message statistics** — total messages, words, media shared, and links shared.
* **Monthly timeline** — track message volume across months.
* **Daily timeline** — see how conversation activity changes over time.
* **Activity by day** — identify the days of the week with the most messages.
* **Activity by month** — compare messaging volume across months.
* **Hourly activity heatmap** — visualise when conversations are most active throughout the week.
* **Most active members** — view the most frequent contributors in an overall analysis.
* **Word cloud** — get a visual summary of frequently used words.
* **Top 20 words** — inspect the most common non-stop words.
* **Hinglish stop-word filtering** — removes common Hinglish words to make word analysis more meaningful.
* **Emoji analysis support** — emoji extraction functionality is included in the helper module.

## Tech Stack

* **Python**
* **Streamlit** — dashboard and UI
* **Pandas** — data processing and analysis
* **Matplotlib** — charts and timelines
* **Seaborn** — heatmap visualisation
* **WordCloud** — word-frequency visualisation
* **URLExtract** — link detection
* **Emoji** — emoji processing

## Project Structure

```text
WhatsApp_Chat_Analyser/
│
├── app.py
├── preprocessor.py
├── helper.py
├── stop_hinglish.txt
├── WhatsApp_Chat_Analyser.ipynb
├── requirements.txt
└── README.md
```

### File Overview

| File                           | Purpose                                          |
| ------------------------------ | ------------------------------------------------ |
| `app.py`                       | Streamlit dashboard and UI                       |
| `preprocessor.py`              | Parses WhatsApp exports and prepares the dataset |
| `helper.py`                    | Statistics, analysis and visualisation functions |
| `stop_hinglish.txt`            | Hinglish stop-word list                          |
| `WhatsApp_Chat_Analyser.ipynb` | Exploratory analysis notebook                    |
| `requirements.txt`             | Python dependencies                              |

## How It Works

```text
WhatsApp .txt Export
        ↓
    Preprocessing
        ↓
Structured DataFrame
        ↓
Filtering by User / Overall
        ↓
Statistical Analysis
        ↓
Charts + Word Analysis
        ↓
Conversation Insights
```

### 1. Export Your WhatsApp Chat

Export a WhatsApp conversation as a **`.txt` file** without media.

### 2. Upload the File

Open the Streamlit application and upload the exported `.txt` file from the sidebar.

### 3. Select Analysis Scope

Choose **Overall** to analyse the complete conversation or select an individual participant.

### 4. Run Analysis

Click **Run Analysis** to generate the dashboard.

## Installation

Clone the repository:

```bash
git clone https://github.com/Yuvika108/WhatsApp_Chat_Analyser.git
cd WhatsApp_Chat_Analyser
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate it on macOS/Linux:

```bash
source venv/bin/activate
```

On Windows:

```bash
venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## Run Locally

Start the Streamlit application:

```bash
streamlit run app.py
```

Open the local URL provided by Streamlit, usually:

```text
http://localhost:8501
```

## Analysis Modules

### Summary

Provides:

* Total messages
* Total words
* Media messages
* Links shared

### Timelines

Visualises:

* Monthly message trends
* Daily message activity

### Activity Map

Shows:

* Day-of-week activity
* Month-wise activity
* Hourly activity using a heatmap

### Most Active Members

For **Overall** analysis, the application displays the most active participants along with their percentage contribution to the conversation.

### Word Analysis

Provides:

* Word cloud
* Top 20 frequently used words
* Hinglish-aware stop-word filtering

## WhatsApp Export Format

The parser is designed around WhatsApp exports containing date, time, and sender information.

Example:

```text
12/05/25, 10:30 - Alice: Hey!
12/05/25, 10:31 - Bob: What's up?
```

Messages without a sender, such as system/group notifications, are handled separately as `group_notification`.

## Notes

* The project currently works with **WhatsApp `.txt` exports**.
* The preprocessing logic is designed around the WhatsApp date/time format used by the project.
* `stop_hinglish.txt` is used to filter common Hinglish words during word analysis.
* The project focuses on exploratory conversation analytics rather than sentiment or behavioural diagnosis.

## Future Improvements

* Sentiment analysis
* Detailed emoji analytics
* Response-time analysis
* Conversation streaks
* Media-type breakdown
* Interactive Plotly visualisations
* Support for additional WhatsApp export formats
* Comparison between multiple conversations
* Public deployment

## License

This project currently does not specify a license.
