# Lushtára 🍽️

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](https://github.com/Syntax-Overlord/lushtara)

**Lushtára** is an AI-powered food translation and recommendation system that helps travelers navigate unfamiliar culinary environments with confidence. Using advanced computer vision and emotional intelligence algorithms, Lushtára transforms menu photos into personalized dining recommendations.

## 🌟 Key Features

### Intelligent Menu Processing

- **OCR & Translation**: Scans and translates physical menus in any supported language
- **Computer Vision**: Advanced image processing for accurate text extraction
- **Multi-language Support**: Real-time translation capabilities

### Personalized Recommendations

- **Cravin Rating Scale**: Proprietary 1-10 scoring system for dish alignment
- **5-Factor Analysis**: Considers taste profile, temperature, budget, weather, and portion size
- **Emotional Intelligence**: Understands and responds to user's culinary mood and preferences

### Travel-Optimized Experience

- **Low-bandwidth Design**: Optimized for poor internet connections
- **Quick Decision Making**: Reduces food selection uncertainty
- **Cultural Bridge**: Breaks down linguistic and cultural barriers

## 🚀 How It Works

1. **📸 Upload Menu**: Take a photo of any restaurant menu
2. **⚙️ Set Preferences**: Configure your 5 preference factors:
   - **Taste Profile**: Spicy, mild, sweet, savory, etc.
   - **Temperature**: Hot, cold, room temperature
   - **Budget**: Low, medium, high spending range
   - **Weather**: Current weather conditions
   - **Portion Size**: Small, medium, large, sharing
3. **🧠 AI Analysis**: Lushtára processes and translates the menu
4. **📊 Get Rankings**: Receive dishes ranked by Cravin Rating (1-10)
5. **🍽️ Make Decision**: Choose with confidence based on personalized scores

## 📊 Cravin Rating Scale

Our proprietary scoring system evaluates dishes on a 1-10 scale based on how well they match your preferences:

| Rating     | Meaning           | Description                                            |
| ---------- | ----------------- | ------------------------------------------------------ |
| 🔥 **10**  | **Perfect Match** | Strong emotional craving, ideal across all preferences |
| 🌟 **9**   | **Excellent**     | High resonance, minor deviation on 1 factor            |
| ✨ **8**   | **Very Good**     | Moderate craving, aligned on 3+ factors                |
| 👍 **7-6** | **Good**          | Partial match, some emotional relevance                |
| 😐 **5-4** | **Neutral**       | Low resonance, minimal alignment                       |
| 👎 **3-2** | **Poor**          | Poor fit, mostly incompatible                          |
| ❌ **1**   | **Avoid**         | Near-zero emotional match, not recommended             |

> 💡 **Pro Tip**: All dishes are ranked in descending order of Cravin Rating for easy decision-making

## 🛠️ Technical Architecture

### Core Technologies

- **Computer Vision**: Advanced OCR for menu text extraction
- **Natural Language Processing**: Multi-language translation and understanding
- **Machine Learning**: Preference-based recommendation algorithms
- **Responsive Design**: Optimized for mobile devices and poor connectivity

### AI Model Features

- **Emotional Intelligence**: Understands context and mood-based preferences
- **Cultural Adaptation**: Recognizes regional cuisine characteristics
- **Real-time Processing**: Fast analysis for immediate recommendations
- **Personalization**: Learns from user feedback and preferences

## 🎯 Use Cases

### 🌍 International Travel

- Navigate foreign restaurants with confidence
- Overcome language barriers in local eateries
- Discover authentic dishes aligned with your taste

### 🏙️ Urban Exploration

- Explore diverse neighborhood cuisines
- Make quick dining decisions in busy areas
- Find comfort food that matches your mood

### 🍜 Cultural Discovery

- Learn about new cuisines through personalized recommendations
- Understand local food culture and preferences
- Bridge cultural gaps through food

## 🔧 API Integration Guide

### Basic Usage

```bash
# Upload menu image and get recommendations
curl -X POST "https://api.lushtara.com/analyze" \
  -H "Content-Type: multipart/form-data" \
  -F "menu_image=@menu.jpg" \
  -F "preferences={
    \"taste\": \"spicy\",
    \"temperature\": \"hot\",
    \"budget\": \"medium\",
    \"weather\": \"cold\",
    \"portion\": \"large\"
  }"
```

### Response Format

```json
{
  "recommendations": [
    {
      "dish_name": "Szechuan Hot Pot",
      "cravin_rating": 9.2,
      "justification": "Perfect match for spicy preference and cold weather",
      "price_range": "$$",
      "translation": "四川火锅"
    }
  ],
  "total_items": 24,
  "processing_time": "1.2s"
}
```

## 🚀 Getting Started

### Prerequisites

- Node.js 16+ or Python 3.8+
- Valid API key (contact for access)
- Image processing capabilities

### Quick Start

1. **Clone the repository**

   ```bash
   git clone https://github.com/Syntax-Overlord/lushtara.git
   cd lushtara
   ```

2. **Install dependencies**

   ```bash
   npm install
   # or
   pip install -r requirements.txt
   ```

3. **Set up environment**

   ```bash
   cp .env.example .env
   # Add your API keys and configuration
   ```

4. **Run the application**

   ```bash
   npm start
   # or
   python app.py
   ```

## 🤖 AI Prompt Schema

For developers implementing the AI model:

### Context

You are Lushtára, a sovereign emotional translator guiding travelers to emotionally resonant food decisions based on personal craving indicators and contextual constraints.

### Task

Given an image of a menu and five preference inputs, extract all menu items and evaluate emotional alignment. Rank dishes from 1 to 10 on the Cravin Scale (10 = strongest emotional fit), then return a descending list with rationales.

### Instruction

- Extract menu items from image
- Ask for taste profile, temperature, budget, weather, and portion size preferences
- Internally formulate matching logic based on weighted criteria
- Score all items using the Cravin Rating Scale (1–10)
- Multiple items may share the same rating
- Sort results from highest to lowest resonance
- Output:
  - Ranked dish list
  - Cravin Rating (1–10 scale)
  - Brief justification for each
- Top 3 items must receive detailed explanations

### Invocation Format

> “Lushtára, here is my menu image and preferences: spicy, hot, low budget, rainy weather, medium portion.”

### Output Format

- **Dish List**: Ranked by Cravin Rating (desc)
- **Format**:

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

**Why MIT License?**

- ✅ Permits commercial use and integration
- ✅ Allows modifications and distribution
- ✅ Requires attribution to original authors
- ✅ No warranty liability
- ✅ Simple and widely adopted

## 🌟 Acknowledgments

- Thanks to all contributors and beta testers
- Special thanks to the international food community for feedback
- Powered by advanced AI and computer vision technologies

## 📞 Support & Contact

- **GitHub Issues**: [Report bugs or request features](https://github.com/Syntax-Overlord/lushtara/issues)
- **Email**: Contact for collaboration and technical queries
- **Documentation**: Full API documentation available upon request

---

<p align="center">
  Made with ❤️ for travelers and food enthusiasts worldwide
</p>
