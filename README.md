# 🧠 Economic Intelligence Platform (EIP)

**AI‑Powered Economic Research, Forecasting & Policy Simulation**

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Made with ❤️ by Saransh Shree Chitransh](https://img.shields.io/badge/Made%20with%20%E2%9D%A4%EF%B8%8F%20by-Saransh-blue)](https://github.com/SSChitransh)

---

## 📌 Overview

The **Economic Intelligence Platform (EIP)** is an interactive web application that combines:

- **Multi‑country macroeconomic dashboard** (9 countries, 24 years of data)
- **AI‑powered forecasting** (Linear, Polynomial, and Ensemble models)
- **Policy simulation lab** (adjust education, tax, trade, infrastructure)
- **Built‑in research paper** (formal analysis of education spending vs. poverty)
- **AI assistant** (EI) – a conversational agent that answers questions using either a **built‑in knowledge base** or an **optional cloud LLM** (Hugging Face) for deep, nuanced responses.

Built as a **single HTML file** with no external server required – runs entirely in your browser.

---

## 🚀 Live Demo

👉 [https://sschitransh.github.io/Saransh-Economic-Intelligence-Platform/](https://sschitransh.github.io/Saransh-Economic-Intelligence-Platform/)

---

## ✨ Key Features

### 📊 Interactive Dashboard
- Select from 9 countries (G7 + India, China)
- Choose between **4 forecasting models** (Linear, Polynomial², Polynomial³, Ensemble)
- View **7 macroeconomic indicators** (GDP, Inflation, Poverty, Education, Unemployment, Population, Trade)
- Each chart shows **historical data + 5‑year AI forecast with confidence intervals**
- Real‑time accuracy metrics (RMSE, MAE) for each model

### 🔮 AI Economic Forecasts
- Dedicated panel showing **GDP growth** and **Inflation** predictions for the next 5 years
- Forecast range and model accuracy displayed clearly

### 🧪 Policy Simulation Lab
- Adjust four policy levers:
  - 📚 Education Spending (% of GDP)
  - 💰 Tax Rate (%)
  - 🌐 Trade Openness (%)
  - 🏗️ Infrastructure Investment (%)
- See immediate projected impact on **GDP, Inflation, Poverty, Education Spending, and Unemployment**
- Color‑coded results (positive / negative / neutral)

### 📝 Research Paper
- Embedded publication‑ready paper covering:
  - Research question
  - Data & methodology
  - AI model performance
  - Key findings
  - Policy recommendations
  - Conclusion

### 📂 Download Center
- Download the **Research Paper** (TXT)
- Download high‑resolution **charts** (PNG): Scatter Plot, Poverty Trends, Heatmap
- Download the **Presentation** (PPTX)
- Download the **Source Code** (Jupyter Notebook IPYNB)

### 🤖 EI Assistant (Open‑Source AI Chat)
- Floating chat widget that works out‑of‑the‑box
- **Built‑in knowledge base** covering economics, geopolitics, technology, health, and more – no API key required
- **Optional cloud LLM** – add a free Hugging Face API key to unlock GPT‑level responses (Mistral‑7B)
- **Voice output** – toggle speech synthesis for AI responses
- **File upload** – upload PDFs, images, text files, CSVs, and DOCX for context‑aware conversations
- Friendly, conversational tone with memory (remembers your name)

---

## 🛠️ How It Works

1. **Dashboard** – Data is generated mathematically to mimic real‑world macroeconomic trends (World Bank / IMF style). Users can switch countries and models to explore different scenarios.
2. **Forecasting** – The Ensemble model averages Linear, Polynomial², and Polynomial³ predictions, reducing RMSE by 15‑20% on average.
3. **Policy Simulation** – A simplified causal model translates policy changes into economic outcomes, providing an educational tool for understanding trade‑offs.
4. **AI Assistant** – Uses either:
   - **Local knowledge base** (fast, offline, always available)
   - **Hugging Face Inference API** (when a key is provided) for advanced, context‑aware answers.

---

## 📁 Project Structure
.
├── index.html # Single‑file application (all HTML, CSS, JS)
├── README.md # This file
└── (optional) # Additional assets if you split the code


Everything is self‑contained in `index.html`. No external dependencies other than CDN libraries (loaded at runtime).

---

## 🚀 Getting Started

### Prerequisites
- A modern web browser (Chrome, Edge, Firefox, Safari)
- (Optional) A free [Hugging Face API key](https://huggingface.co/settings/tokens) for cloud LLM features

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/SSChitransh/Saransh-Economic-Intelligence-Platform.git
   cd Saransh-Economic-Intelligence-Platform

2. Open index.html in your browser – that’s it! No build tools or servers needed.

💡 Usage Guide
Dashboard
Use the dropdowns at the top of the dashboard to select a country and a forecasting model.

All 7 charts update automatically.

Hover over any chart for details.

Policy Simulation
Drag the sliders under the Policy Simulation Lab section.

Watch the projected impacts update instantly in the panel on the right.

EI Assistant
Click the EI floating button at the bottom‑right of the screen.

Without an API key: Ask any question – EI will respond using the built‑in knowledge base.

With an API key: Enter your Hugging Face key in the chat window’s input bar (it’s saved locally). Now EI will use Mistral‑7B for smarter, more detailed answers.

You can upload files (PDF, image, text, CSV, DOCX) by clicking the 📎 icon.

Click the 🔊 icon to toggle voice output.

Downloads
Scroll to the Download section at the bottom.

Click any button to download the corresponding file.

🧠 Technologies Used
Tool / Library	Purpose
HTML5 / CSS3 / JavaScript (ES6)	Core frontend
Plotly.js	Interactive charts
PptxGenJS	PPTX presentation generation
PDF.js	PDF parsing for file uploads
Tesseract.js	OCR for image uploads
Hugging Face Inference API	Cloud LLM (Mistral‑7B)
Google Fonts (Inter)	Typography
🎯 Why This Project Matters
This project demonstrates:

Real‑world problem solving: Education spending and poverty reduction are critical global issues.

AI integration: Combines traditional statistical forecasting with modern LLMs.

Policy impact simulation: Makes abstract economic concepts tangible.

User‑centric design: Single‑page application with a polished UI.

Open‑source ethos: All code is transparent, and the assistant can work completely offline.

🧪 Future Improvements
Add real‑time data fetching from World Bank / IMF APIs.

Extend forecasting with more advanced models (ARIMA, LSTM).

Add more countries and indicators.

Implement collaborative filtering for personalised policy recommendations.

Add a dark/light theme toggle.

Support for exporting simulation results as CSV.

🤝 Contributing
Contributions are welcome! Please open an issue or submit a pull request.

📄 License
This project is licensed under the MIT License – see the LICENSE file for details.

🙏 Acknowledgements
MIT Maker Portfolio – for inspiring this project.

Hugging Face – for providing accessible open‑source AI models.

World Bank & IMF – for the data patterns (mathematically simulated).

📬 Contact
Built with ❤️ by Saransh Shree Chitransh
GitHub: @SSChitransh
Project Link: https://github.com/SSChitransh/Saransh-Economic-Intelligence-Platform

Data without insights is just noise. Intelligence without empathy is just calculation...