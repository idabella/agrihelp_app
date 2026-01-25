# AgriHelp - Agricultural AI Assistant
---
<br>
<div align="center">
   <img src="images/backhome.png" width="900">
</div>

<br>
<br>
An intelligent agricultural assistant that helps farmers diagnose crop diseases, get farming advice, and receive treatment recommendations in multiple languages (Darija, Arabic, French).

## ✨ Features

**Core Functionality**
- 🌾 AI-powered agricultural advice and crop disease diagnosis
- 📸 Image analysis for disease detection
- 💊 Automated treatment recommendations
- 💬 Conversation history and persistent chat sessions

**User Experience**
- 📱 Mobile-first responsive design
- 🌍 Multi-language support (Darija, Arabic, French)
- 🔐 Secure authentication system
- 🎨 Modern UI built with shadcn/ui and Tailwind CSS

## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- npm or yarn

### Installation

```bash
# Clone and install
git clone <YOUR_GIT_URL>
cd agrihelp-app
npm install

# Configure environment
cp .env.example .env
# Edit .env with your API keys

# Start development server
npm run dev
```

Visit `http://localhost:5173`

### Environment Variables

```env
VITE_API_BASE_URL=http://localhost:3000
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_key
```

## 📁 Project Structure

```
src/
├── api/                    # API configuration and endpoints
├── services/              # Backend integrations (LLM, image analysis)
├── pages/                 # Route components
│   ├── auth/             # Authentication pages
│   └── Index.tsx         # Main chat interface
├── components/           # Reusable UI components
├── hooks/                # Custom React hooks
└── types/                # TypeScript definitions
```

## 🔌 Backend Integration

### Required API Endpoints

**Chat & LLM**
```typescript
POST /api/llm/chat      // Send message to AI
POST /api/llm/stream    // Stream AI responses
```

**Image Analysis**
```typescript
POST /api/image/upload           // Upload image
POST /api/image/analyze          // Analyze for diseases
POST /api/image/analyze-base64   // Analyze base64 image
```

**Authentication**
```typescript
POST /api/auth/signin    // User login
POST /api/auth/signup    // User registration
POST /api/auth/signout   // User logout
POST /api/auth/refresh   // Refresh token
```

### Usage Examples

**Send a chat message:**
```typescript
import { sendMessageToLLM } from '@/services';

const response = await sendMessageToLLM({
  message: 'What is wrong with my tomato plant?',
  language: 'darija',
  imageUrl: 'https://...',
});
```

**Analyze an image:**
```typescript
import { uploadAndAnalyzeImage } from '@/services';

const result = await uploadAndAnalyzeImage(file, 'arabic');
console.log(result.detections);  // Detected diseases
console.log(result.treatment);   // Treatment plan
```

For detailed integration guides, see [`src/services/README.md`](src/services/README.md) and [`src/api/README.md`](src/api/README.md).

## 🛠️ Tech Stack

| Category | Technology |
|----------|-----------|
| Framework | React 18 + TypeScript |
| Build Tool | Vite |
| Styling | Tailwind CSS |
| UI Components | shadcn/ui |
| Routing | React Router v6 |
| State Management | TanStack Query |
| Form Validation | React Hook Form + Zod |
| Backend | Supabase (optional) |

## 📱 Routes

| Path | Page | Description |
|------|------|-------------|
| `/` | Landing | Homepage with features |
| `/signin` | Sign In | User authentication |
| `/signup` | Sign Up | User registration |
| `/chat` | Chat | AI assistant interface |

## 🌍 Multi-Language Support

Supports three languages with RTL for Arabic:
- **Darija** (Moroccan Arabic)
- **Arabic** (Modern Standard Arabic)
- **French**

Language affects UI text, AI responses, and treatment recommendations.

## 🎨 Design System

**Colors**
- Primary: Deep Olive Green `hsl(140 30% 28%)`
- Accent: Wheat Gold `hsl(42 85% 55%)`
- Background: Green-to-teal gradient

**Typography**
- Latin: Nunito
- Arabic: IBM Plex Sans Arabic

**Mobile-First Principles**
- Minimum touch target: 44×44px
- Responsive scales: `text-base sm:text-lg md:text-xl`
- Mobile-first CSS utilities

## 📦 Scripts

```bash
npm run dev          # Start development server
npm run build        # Production build
npm run lint         # Run ESLint
npm run preview      # Preview production build
```

## 🚢 Deployment

```bash
# Build for production
npm run build

# Deploy to Vercel/Netlify
# 1. Connect your Git repository
# 2. Set environment variables
# 3. Deploy automatically on push
```

## 📋 Development Guidelines

**Code Style**
- Use TypeScript for all new code
- Functional components with hooks
- Implement proper error handling
- Follow mobile-first CSS patterns

**Component Best Practices**
- Keep components focused and small
- Extract reusable logic into hooks
- Use composition over inheritance
- Maintain consistent naming (PascalCase for components)

## 🎯 Roadmap

**Phase 1 - Backend Integration**
- [ ] Connect LLM API (OpenAI/Gemini)
- [ ] Integrate image analysis service
- [ ] Implement real authentication

**Phase 2 - Enhanced Features**
- [ ] Conversation history persistence
- [ ] Offline support & PWA
- [ ] Push notifications

**Phase 3 - Scale & Analytics**
- [ ] Admin dashboard
- [ ] Analytics and monitoring
- [ ] Multi-region support

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

MIT License - see LICENSE file for details

## 🆘 Support

- 📖 Documentation: Check `src/services/README.md` and `src/api/README.md`
- 🐛 Issues: Open an issue on GitHub
- 💬 Questions: Contact the development team

---

Built with ❤️ for farmers everywhere
