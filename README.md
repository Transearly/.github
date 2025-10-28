# 🌐 Transearly - AI-Powered Translation Platform

<div align="center">

![Transearly Banner](https://img.shields.io/badge/Transearly-AI%20Translation-5B67F5?style=for-the-badge)
[![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=for-the-badge&logo=nestjs&logoColor=white)](https://nestjs.com/)
[![React Native](https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactnative.dev/)
[![Google Cloud](https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white)](https://cloud.google.com/)

**Real-time multilingual translation platform powered by AI and Computer Vision**

[Features](#-features) • [Architecture](#-architecture) • [Quick Start](#-quick-start) • [Tech Stack](#-tech-stack) • [Team](#-team)

</div>

---

## 📖 About

**Transearly** is an innovative AI-powered translation platform that combines advanced computer vision with natural language processing to provide seamless, real-time translation services. The platform supports multiple translation modes including text, voice, image, and document translation.

### 🎯 Key Highlights

- **📸 Image Translation with OCR** - Detect and translate text in images using Google Cloud Vision API
- **🎤 Voice Translation** - Real-time speech-to-text translation
- **📄 Document Translation** - Support for PDF, DOCX, XLSX, PPTX, CSV formats
- **💬 Text Translation** - Fast and accurate text translation across 8+ languages
- **📱 Mobile-First Design** - Beautiful React Native mobile application
- **⚡ Real-time Processing** - WebSocket integration for live translation updates
- **🎨 Interactive UI** - Bounding box detection with tap-to-translate popups

---

## ✨ Features

### 🖼️ Image Translation
- **Smart OCR Detection** - Uses Google Cloud Vision API for accurate text detection
- **Interactive Bounding Boxes** - Tap on detected text regions to view translations
- **Multi-language Support** - Automatically detects and translates text in images
- **Paragraph Grouping** - Intelligently groups text into meaningful segments

### 🎙️ Voice Translation
- **Real-time Recording** - Record and translate voice input
- **Audio Playback** - Listen to original recordings
- **Multiple Languages** - Support for 8+ languages

### 📁 Document Translation
- **File Format Support** - PDF, DOCX, XLSX, PPTX, CSV
- **Batch Processing** - Queue-based translation for large documents
- **Progress Tracking** - Real-time translation progress via WebSocket
- **Format Preservation** - Maintains original document formatting

### 💬 Text Translation
- **Instant Translation** - Fast text-to-text translation
- **Context-Aware** - Preserves semantic meaning
- **Copy to Clipboard** - Easy result sharing

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    TRANSEARLY PLATFORM                       │
└─────────────────────────────────────────────────────────────┘

┌──────────────────────┐         ┌──────────────────────────┐
│   Mobile App         │         │   Backend API            │
│   (React Native)     │◄───────►│   (NestJS)               │
│                      │   REST  │                          │
│  • Camera Screen     │   WebSocket  • Translation Service │
│  • Voice Recording   │         │   • Queue Processing     │
│  • Text Input        │         │   • Google Vision OCR    │
│  • File Upload       │         │   • AI Translation       │
└──────────────────────┘         └──────────────────────────┘
                                           │
                    ┌──────────────────────┼──────────────────┐
                    │                      │                  │
              ┌─────▼──────┐      ┌───────▼──────┐   ┌──────▼─────┐
              │  Google    │      │  OpenRouter  │   │   Redis    │
              │  Cloud     │      │  (Gemini)    │   │   Queue    │
              │  Vision    │      │              │   │            │
              └────────────┘      └──────────────┘   └────────────┘
```

### Repository Structure

```
transearly/
├── transearly-api/          # Backend NestJS API Server
│   ├── src/
│   │   ├── modules/
│   │   │   └── translator/  # Translation services & controllers
│   │   ├── main.ts
│   │   └── app.module.ts
│   └── package.json
│
└── mobile-app/              # React Native Mobile Application
    ├── src/
    │   ├── screens/         # App screens
    │   ├── components/      # Reusable components
    │   ├── services/        # API integration
    │   └── navigation/      # Navigation setup
    └── package.json
```

---

## 🚀 Quick Start

### Prerequisites

- Node.js 18+
- npm or yarn
- Expo CLI (for mobile app)
- Google Cloud Vision API credentials
- OpenRouter API key

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-org/transearly.git
cd transearly
```

### 2️⃣ Setup Backend API

```bash
cd transearly-api
npm install

# Create .env file
cp .env.example .env

# Add your credentials to .env
GOOGLE_APPLICATION_CREDENTIALS=./google-cloud-key.json
OPENROUTER_API_KEY=your_openrouter_key
OPENROUTER_BASE_URL=https://openrouter.ai/api/v1/chat/completions
OPENROUTER_MODEL=google/gemini-2.0-flash-exp:free

# Start the server
npm run start:dev
```

The API will run on `http://localhost:5010`

### 3️⃣ Setup Mobile App

```bash
cd mobile-app
npm install

# Create .env file
cp .env.example .env

# Update API_URL in src/config/api.config.js
# For local development: http://YOUR_LOCAL_IP:5010

# Start the app
npm start
# or use tunnel mode
npm run tunnel
```

### 4️⃣ Google Cloud Vision Setup

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select existing one
3. Enable **Cloud Vision API**
4. Create a Service Account and download JSON key
5. Save the key as `google-cloud-key.json` in `transearly-api/`

---

## 🛠️ Tech Stack

### Backend
- **Framework**: NestJS (Node.js)
- **Queue**: Bull + Redis
- **OCR**: Google Cloud Vision API
- **AI Translation**: OpenRouter (Gemini Flash)
- **WebSocket**: Socket.io
- **Document Processing**: pdf-lib, mammoth, exceljs, pptxgenjs

### Mobile App
- **Framework**: React Native + Expo
- **UI Components**: React Native core components
- **Navigation**: React Navigation
- **HTTP Client**: Axios
- **Real-time**: Socket.io Client
- **Media**: Expo Camera, Expo Audio

### External Services
- **Google Cloud Vision API** - Text detection and OCR
- **OpenRouter** - AI translation (Gemini Flash model)
- **Redis** - Queue management

---

## 📱 Supported Languages

🇻🇳 Vietnamese | 🇬🇧 English | 🇪🇸 Spanish | 🇫🇷 French
🇩🇪 German | 🇯🇵 Japanese | 🇰🇷 Korean | 🇨🇳 Chinese

---

## 📸 Screenshots

### Image Translation
```
┌─────────────────────────────────┐
│  [<]  Image Translation    [🇻🇳] │
├─────────────────────────────────┤
│                                 │
│     ┌──────────────────┐        │
│     │  祝通宝玉萃院...  │◄─ Tap  │
│     └──────────────────┘        │
│                                 │
│  ┌─────────────────────────┐   │
│  │ Translation             │   │
│  │ Original: 祝通宝玉...    │   │
│  │ Translated: Chúc bạn... │   │
│  └─────────────────────────┘   │
│                                 │
│  [📷 Translate]                 │
└─────────────────────────────────┘
```

---

## 🎯 API Endpoints

### Translation Endpoints

```
POST   /translator/text              # Translate text
POST   /translator/image             # Translate image with OCR
POST   /translator/upload            # Upload document for translation
GET    /translator/status/:jobId     # Check translation job status
GET    /translator/download/:fileName # Download translated document
```

### Response Format (Image Translation)

```json
{
  "success": true,
  "targetLanguage": "Vietnamese",
  "segments": [
    {
      "position": {
        "x": 15.5,
        "y": 20.3,
        "width": 30.2,
        "height": 5.1
      },
      "original": "祝 通 宝 玉 萃 院 之 旅 充 满 快 乐",
      "translated": "Chúc chuyến đi đến học viện Ngọc Bảo Tụy đầy niềm vui"
    }
  ]
}
```

---

## 👥 Team

<table>
  <tr>
    <td align="center">
      <img src="https://via.placeholder.com/100" width="100px;" alt=""/>
      <br />
      <sub><b>Trương Nguyễn Tiến Đạt</b></sub>
      <br />
      <sub>Full-stack Developer</sub>
    </td>
    <td align="center">
      <img src="https://via.placeholder.com/100" width="100px;" alt=""/>
      <br />
      <sub><b>Nguyễn Minh Thắng</b></sub>
      <br />
      <sub>Backend Developer</sub>
    </td>
    <td align="center">
      <img src="https://via.placeholder.com/100" width="100px;" alt=""/>
      <br />
      <sub><b>Nguyễn Bá Trung Nguyên</b></sub>
      <br />
      <sub>Mobile Developer</sub>
    </td>
    <td align="center">
      <img src="https://via.placeholder.com/100" width="100px;" alt=""/>
      <br />
      <sub><b>Nguyễn Hữu Anh Tuấn</b></sub>
      <br />
      <sub>AI/ML Engineer</sub>
    </td>
  </tr>
</table>

---

## 📋 Project Status

✅ Text Translation
✅ Image Translation with OCR
✅ Voice Recording & Translation
✅ Document Translation (PDF, DOCX, XLSX, PPTX, CSV)
✅ Real-time WebSocket Updates
✅ Interactive Bounding Box UI
🚧 Multi-language Audio Output
🚧 Offline Translation Mode
🚧 Translation History & Favorites

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- **Google Cloud Vision API** for powerful OCR capabilities
- **OpenRouter** for AI translation services
- **NestJS** for the robust backend framework
- **Expo** for streamlined React Native development

---

## 📞 Contact

For questions or support, please open an issue or contact the team.

---

<div align="center">

**Made with ❤️ by the Transearly Team**

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/your-org/transearly)

</div>
