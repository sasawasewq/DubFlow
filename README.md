# 🎙️ DubFlow - AI-Powered YouTube Video Dubbing

Transform any YouTube video into multiple languages with AI-powered dubbing technology. DubFlow automatically extracts transcripts, translates content, generates natural-sounding speech, and creates professionally dubbed videos.

![DubFlow Demo](https://img.shields.io/badge/Status-Active-brightgreen) ![Node.js](https://img.shields.io/badge/Node.js-v18+-blue) ![Next.js](https://img.shields.io/badge/Next.js-v13+-black) 
### 🏠 Home Page
![HomePage](images/Screenshot%202025-06-08%20162120.png)

### 🎬 Dubbing a YouTube Video
![Dubbing a YouTube video](images/Screenshot%202025-06-08%20162211.png)

### 🌐 Language Selection
![Language Selection](images/Screenshot%202025-06-08%20162227.png)

### ⚙️ Processing
![Processing](images/Screenshot%202025-06-08%20162256.png)

### 📺 Dubbed Video Display
![Dubbed Video display](images/Screenshot%202025-06-08%20162539.png)



## ✨ Features

- 🎬 **YouTube Video Processing**: Seamlessly download and process YouTube videos
- 📝 **Smart Transcript Extraction**: Advanced transcript fetching with multiple fallback strategies
- 🌍 **Multi-Language Translation**: Support for 16+ languages using RapidAPI Google Translator
- 🔊 **Natural Speech Generation**: High-quality text-to-speech using Google TTS
- ⏰ **Precise Audio Alignment**: Maintains original timing and synchronization
- 🎭 **Professional Video Merging**: Combines dubbed audio with original video
- 📊 **Real-time Progress Tracking**: Live updates during processing
- 🚀 **Modern UI/UX**: Beautiful gradient interface with animations

## 🎯 Supported Languages

- Spanish (Español)
- French (Français)
- German (Deutsch)
- Italian (Italiano)
- Portuguese (Português)
- Russian (Русский)
- Japanese (日本語)
- Korean (한국어)
- Chinese (中文)
- Hindi (हिंदी)
- Arabic (العربية)
- Dutch (Nederlands)
- Polish (Polski)
- Turkish (Türkçe)
- Thai (ไทย)
- Vietnamese (Tiếng Việt)

## 🏗️ Architecture

### Backend (Node.js/Express)
- **Transcript Extraction**: Enhanced retry logic with multiple fallback methods
- **Translation Service**: RapidAPI Google Translator integration
- **Audio Processing**: FFmpeg for audio manipulation and merging
- **Video Processing**: yt-dlp/youtube-dl for reliable video downloads
- **Text-to-Speech**: Google TTS (gTTS) for natural voice generation

### Frontend (Next.js/React)
- **Modern UI**: Tailwind CSS with gradient animations
- **Real-time Updates**: Live progress tracking and status updates
- **Responsive Design**: Mobile-first approach with beautiful animations
- **Error Handling**: Comprehensive error messages and user guidance

## 🚀 Quick Start

### Prerequisites

- Node.js v18 or higher
- npm or yarn
- FFmpeg installed on your system
- yt-dlp or youtube-dl installed
- RapidAPI account with Google Translator access

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/dubflow.git
   cd dubflow
   ```

2. **Install backend dependencies**
   ```bash
   cd backend
   npm install
   ```

3. **Install frontend dependencies**
   ```bash
   cd ../frontend
   npm install
   ```

4. **Set up environment variables**
   
   Create a `.env` file in the backend directory:
   ```env
   PORT=3001
   RAPIDAPI_KEY=your_rapidapi_key_here
   ```

5. **Install system dependencies**
   
   **On macOS:**
   ```bash
   brew install ffmpeg yt-dlp
   ```
   
   **On Ubuntu/Debian:**
   ```bash
   sudo apt update
   sudo apt install ffmpeg yt-dlp
   ```
   
   **On Windows:**
   - Download FFmpeg from https://ffmpeg.org/download.html
   - Download yt-dlp from https://github.com/yt-dlp/yt-dlp

### Running the Application

1. **Start the backend server**
   ```bash
   cd backend
   npm start
   ```
   The backend will run on http://localhost:3001

2. **Start the frontend development server**
   ```bash
   cd frontend
   npm run dev
   ```
   The frontend will run on http://localhost:3000

3. **Open your browser** and navigate to http://localhost:3000

## 📚 API Documentation

### POST /api/dub-video
Processes a YouTube video for dubbing.

**Request Body:**
```json
{
  "videoUrl": "https://www.youtube.com/watch?v=VIDEO_ID",
  "targetLanguage": "spanish"
}
```

**Response:**
```json
{
  "success": true,
  "jobId": "uuid-here",
  "downloadUrl": "/downloads/uuid/dubbed_video.mp4",
  "message": "Video dubbed successfully!",
  "transcriptSegments": 150,
  "translationErrors": 0
}
```

### POST /api/check-transcript
Validates transcript availability before processing.

**Request Body:**
```json
{
  "videoUrl": "https://www.youtube.com/watch?v=VIDEO_ID"
}
```

### GET /api/job-status/:jobId
Checks the status of a dubbing job.

**Response:**
```json
{
  "status": "completed",
  "downloadUrl": "/downloads/jobId/dubbed_video.mp4"
}
```

### GET /api/health
Health check endpoint.

## 🔧 Configuration

### Environment Variables

| Variable | Description | Required | Default |
|----------|-------------|----------|---------|
| `PORT` | Backend server port | No | 3001 |
| `RAPIDAPI_KEY` | RapidAPI key for Google Translator | Yes | - |

### Customization Options

- **Batch Size**: Adjust translation batch size in the backend code
- **Retry Logic**: Configure retry attempts and delays for transcript fetching
- **Audio Quality**: Modify FFmpeg settings for different audio quality
- **Language Support**: Add new languages by updating the language maps

## 🎨 Frontend Customization

The frontend uses Tailwind CSS for styling. Key customization options:

- **Color Scheme**: Modify gradient colors in the component
- **Animations**: Adjust animation delays and durations
- **Layout**: Customize the responsive grid system
- **Progress Indicators**: Modify loading states and progress displays

## 🐛 Troubleshooting

### Common Issues

1. **"No transcript found" error**
   - Ensure the video has captions enabled
   - Try videos with manual subtitles instead of auto-generated ones
   - Check if the video is publicly accessible

2. **Translation failures**
   - Verify your RapidAPI key is correct and active
   - Check your RapidAPI subscription limits
   - Monitor API rate limiting

3. **Video download issues**
   - Ensure yt-dlp is installed and updated
   - Check if the video is available in your region
   - Try different video formats or quality settings

4. **FFmpeg errors**
   - Verify FFmpeg is properly installed
   - Check system PATH configuration
   - Ensure sufficient disk space for processing

### Debug Mode

Enable debug logging by setting:
```env
DEBUG=true
```

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines

- Follow ESLint configuration
- Write descriptive commit messages
- Add tests for new features
- Update documentation as needed

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [youtube-transcript](https://github.com/Kakulukian/youtube-transcript) for transcript extraction
- [RapidAPI](https://rapidapi.com/) for translation services
- [FFmpeg](https://ffmpeg.org/) for video/audio processing
- [yt-dlp](https://github.com/yt-dlp/yt-dlp) for reliable YouTube downloads
- [Google TTS](https://github.com/zlargon/google-tts) for speech synthesis



**Made with ❤️ for content creators worldwide**
