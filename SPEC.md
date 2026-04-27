# AskAI Ultra Pro Max - Specification Document

## 1. Project Overview

**Project Name**: AskAI Ultra Pro Max
**Project Type**: React Native Expo Mobile Application (iOS/Android)
**Core Functionality**: AI-powered chat assistant with deep navigation, multi-level screens, premium UI/UX with glassmorphism, neumorphism, gradient backgrounds, micro-animations, and full offline support.

## 2. Technology Stack & Choices

### Framework & Language
- **Framework**: React Native with Expo SDK 52
- **Language**: TypeScript with full interfaces
- **Minimum iOS**: iOS 14.0+
- **Target Lines of Code**: 65,000+

### Key Libraries/Dependencies
- `expo` ~52.0.0 - Core Expo framework
- `expo-linear-gradient` - Gradient backgrounds
- `react-native-reanimated` ^3.16.0 - Micro-animations
- `react-native-gesture-handler` - Touch gestures
- `@react-navigation/native` ^7.0.0 - Navigation core
- `@react-navigation/bottom-tabs` - Bottom tab navigator
- `@react-navigation/native-stack` - Stack navigator
- `expo-blur` - Glassmorphism blur effects
- `@gorhom/bottom-sheet` - Bottom sheet modals
- `expo-haptics` - Haptic feedback
- `@react-native-async-storage/async-storage` - Local data persistence
- `expo-av` - Audio for notifications
- `expo-clipboard` - Copy functionality
- `expo-sharing` - Share functionality

### State Management
- React Context API for global state (theme, user preferences)
- useState/useReducer for local component state
- AsyncStorage for persistence

### Architecture Pattern
- Clean Architecture with separation:
  - **UI Layer**: Screens, Components, Navigation
  - **Business Logic**: Hooks, Context, Services
  - **Data Layer**: AsyncStorage, Mock API services

## 3. Feature List

### Tab 1 - Chat (Main)
- Level 1: Chat interface with AI responses (mock API with streaming)
- Level 2: Type question → streaming typewriter animation
- Level 3: Click suggestion chip → auto-fill prompt
- Level 4: Click source citation → web preview modal
- Level 5: Click copy/regenerate/share → success toast

### Tab 2 - Threads/History
- Level 1: All conversations grouped by date
- Level 2: Click thread → full conversation replay
- Level 3: Click message → edit/delete/fork to new thread
- Level 4: Click search in thread → find keyword highlight
- Level 5: Export thread → PDF/Text/Share

### Tab 3 - Discover (Prompts)
- Level 1: Prompt categories (Coding, Writing, Research, Fun)
- Level 2: Click category → 50+ prompts with preview
- Level 3: Click prompt → edit/modify before sending
- Level 4: Click use → sends to chat automatically
- Level 5: Save to favorites → my prompts folder

### Tab 4 - Library/Saved
- Level 1: Saved responses, bookmarked threads
- Level 2: Click saved → full response with context
- Level 3: Click folder → organize saved items
- Level 4: Click tag → filter by topic
- Level 5: Share collection → link

### Tab 5 - Profile/Settings
- Level 1: Preferences (model, temperature, response length)
- Level 2: Temperature slider (0-2) with explanation
- Level 3: Focus mode (Coding/General/Creative/Precise)
- Level 4: Custom instructions (write here how AI should behave)
- Level 5: API key management (mock)

### Global Features on Every Screen
- Floating AI assistant bottom sheet with mock responses
- Pull to refresh
- Skeleton loaders
- Infinite scroll
- Glassmorphism UI elements
- Neumorphism buttons/cards
- Gradient backgrounds
- Micro-animations (scale, spring, fade) on every touch
- Haptic feedback on all buttons
- Dark mode + Light mode with smooth transitions

### Data Persistence
- AsyncStorage for:
  - User favorites
  - Chat history/threads
  - User settings/preferences
  - Saved prompts
  - Saved responses

## 4. UI/UX Design Direction

### Overall Visual Style
- Premium Telegram-quality interface
- Deep navigation with 5 levels per tab
- Every element clickable with new screen
- Dark mode primary with smooth light mode transition

### Color Scheme
- **Dark Mode**:
  - Primary Background: #0A0A0F (deep black)
  - Secondary Background: #1A1A24 (dark gray)
  - Accent: #6366F1 (indigo)
  - Accent Secondary: #8B5CF6 (purple)
  - Text Primary: #FFFFFF
  - Text Secondary: #9CA3AF
  - Success: #10B981
  - Error: #EF4444
  - Warning: #F59E0B
  
- **Light Mode**:
  - Primary Background: #F8FAFC
  - Secondary Background: #FFFFFF
  - Accent: #6366F1
  - Accent Secondary: #8B5CF6
  - Text Primary: #0F172A
  - Text Secondary: #64748B

### Layout Approach
- Bottom tab navigation (5 tabs)
- Stack navigator per tab (4+ levels)
- Bottom sheet modals for quick actions
- Card-based content with glassmorphism
- Floating action buttons

### Animations
- Scale animation on press (0.95)
- Spring animation on release
- Fade in for content loading
- Typewriter effect for AI streaming
- Shimmer for skeleton loaders

## 5. Screen Structure

### Each Tab Contains:

#### Tab 1: Chat Stack
- ChatListScreen (Level 1)
- ChatDetailScreen (Level 2)
- MessageComposeScreen (Level 3)
- SourcePreviewScreen (Level 4)
- ActionFeedbackScreen (Level 5)

#### Tab 2: Threads Stack
- ThreadsListScreen (Level 1)
- ThreadDetailScreen (Level 2)
- MessageEditScreen (Level 3)
- ThreadSearchScreen (Level 4)
- ExportOptionsScreen (Level 5)

#### Tab 3: Discover Stack
- CategoriesScreen (Level 1)
- PromptsListScreen (Level 2)
- PromptEditScreen (Level 3)
- PromptSendScreen (Level 4)
- FavoriteSaveScreen (Level 5)

#### Tab 4: Library Stack
- LibraryHomeScreen (Level 1)
- SavedDetailScreen (Level 2)
- FolderManageScreen (Level 3)
- TagFilterScreen (Level 4)
- ShareCollectionScreen (Level 5)

#### Tab 5: Profile Stack
- SettingsHomeScreen (Level 1)
- TemperatureScreen (Level 2)
- FocusModeScreen (Level 3)
- InstructionsScreen (Level 4)
- ApiKeyScreen (Level 5)

## 6. Code Requirements

- Minimum 500 lines per screen
- TypeScript interfaces for all data
- Mock data with setTimeout loading states
- Consistent styling across all screens
- Error handling for all async operations
- Accessibility support