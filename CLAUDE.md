# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Life RPG (Role-Playing Game) application - a gamified life management and habit tracking system. Users level up their real-life character by completing tasks and developing skills. The project is built as a hybrid web/Android app using Capacitor.

## Technology Stack

- **Frontend**: Vanilla TypeScript with Vite
- **Styling**: CSS with custom theming system (dark/light modes)
- **Mobile**: Capacitor for Android deployment
- **Storage**: LocalStorage for data persistence
- **AI Integration**: Google Gemini API (@google/genai)

## Development Commands

**Local Development:**
```bash
npm install                 # Install dependencies
npm run dev                 # Start development server (localhost:5173)
npm run build              # Build for production
npm run preview            # Preview production build
```

**Android Development:**
```bash
npx cap sync android       # Sync web build to Android platform
npx cap open android       # Open in Android Studio
npx cap run android        # Build and run on Android device/emulator
```

## Architecture

### Core Structure
- **index.html**: Main app shell with navigation and modal system
- **index.tsx**: Single-file TypeScript application with complete game logic
- **index.css**: Comprehensive styling with theme system
- **capacitor.config.ts**: Mobile app configuration
- **android/**: Native Android project files

### Key Features
1. **RPG System**: Player levels, XP, core stats (STR, DEX, CON, INT, WIS, CHA)
2. **Task Management**: Daily tasks, weekly tasks, and quest system with rewards
3. **Character Development**: Secondary attributes, skills, achievements
4. **Calendar Integration**: Daily notes and checklists with quest conversion
5. **Data Visualization**: Radar chart for core stats, progress bars
6. **Punishment System**: Penalties for incomplete daily/weekly tasks

### Data Management
- All data stored in LocalStorage with JSON serialization
- Automatic daily/weekly task resets with punishment system
- Data migration support for backward compatibility
- IST timezone handling for consistent reset timing

## Important Configuration

### Environment Variables
- `GEMINI_API_KEY`: Required for AI features (set in .env.local)

### Mobile Configuration
- App ID: `com.LifeRPG.app`
- App Name: `LifeInRPG`
- Web directory: `dist`

### Development Setup
1. Vite serves on port 5173 with ngrok support for mobile testing
2. TypeScript with strict mode enabled
3. ES2020 target with React JSX support
4. Module resolution using bundler mode

## Testing and Deployment

- No formal test suite currently implemented
- Build verification: Run `npm run build` to ensure compilation
- Android deployment: Use Android Studio after `npx cap sync android`
- PWA support: Service worker registration included

## Code Structure Notes

- Single-page application with component-based navigation
- Modal system for forms and confirmations  
- Event-driven architecture with DOM event listeners
- Comprehensive state management in memory with LocalStorage persistence
- Responsive design with mobile-first approach