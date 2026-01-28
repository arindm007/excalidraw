# Feature Comparison: Self-Hosted Excalidraw vs Excalidraw+

This document provides a comprehensive comparison between this self-hosted Excalidraw fork and the paid [Excalidraw+](https://plus.excalidraw.com/) service.

## 📋 Overview

This fork is based on the open-source Excalidraw project with modifications to enable self-hosting without Firebase. It provides a pluggable storage backend system that allows you to use HTTP-based storage (PostgreSQL) instead of Firebase.

## 🚀 Quick Feature Summary

| Feature Category | Self-Hosted (This Fork) | Excalidraw+ (Paid) |
|-----------------|------------------------|-------------------|
| **Core Drawing Tools** | ✅ Full Support | ✅ Full Support |
| **Real-time Collaboration** | ✅ Full Support | ✅ Full Support |
| **End-to-End Encryption** | ✅ Yes | ✅ Yes |
| **Export (PNG/SVG/JSON)** | ✅ Yes | ✅ Yes |
| **Self-Hosted Storage** | ✅ Yes (PostgreSQL) | ❌ Cloud Only |
| **AI Text-to-Diagram** | ❌ Not Available | ✅ Yes (Unlimited) |
| **AI Diagram-to-Code** | ❌ Not Available | ✅ Yes (Unlimited) |
| **Cloud Workspace** | ❌ Not Available | ✅ Yes |
| **Version History** | ❌ Not Available | ✅ Yes |
| **Mobile Apps** | ❌ Not Available | ✅ iOS & Android |
| **Team Management** | ❌ Not Available | ✅ Yes |
| **Priority Support** | ❌ Community Only | ✅ Yes |
| **Cost** | 🆓 Free | 💰 Subscription |
| **Data Control** | ✅ Full Control | ❌ Cloud-hosted |

## ✅ Features Available in This Self-Hosted Version

### Core Drawing Features
All the core drawing features of Excalidraw are available:

- ✅ **Free & Open Source** - MIT licensed
- ✅ **Infinite Canvas** - Canvas-based whiteboard with unlimited space
- ✅ **Hand-drawn Style** - Beautiful hand-drawn aesthetic
- ✅ **Dark Mode** - Full dark mode support
- ✅ **Shape Tools** - Rectangle, circle, diamond, arrow, line, free-draw, eraser
- ✅ **Text Support** - Add and edit text with various font options
- ✅ **Image Support** - Insert and manipulate images
- ✅ **Arrow Binding** - Connect arrows to shapes with labeled arrows
- ✅ **Undo/Redo** - Full undo/redo history
- ✅ **Zoom & Pan** - Navigate large canvases easily
- ✅ **Multi-language Support** - i18n with 50+ languages

### Export Features
- ✅ **PNG Export** - Export drawings as PNG images
- ✅ **SVG Export** - Export as scalable vector graphics
- ✅ **Clipboard Export** - Copy to clipboard
- ✅ **JSON Export** - Save as `.excalidraw` files for later editing
- ✅ **Open Format** - All exports use open, documented formats

### Collaboration Features (Key Fork Feature)
- ✅ **Real-time Collaboration** - Multi-user editing with WebSocket support
- ✅ **End-to-End Encryption** - All collaborative sessions are encrypted
- ✅ **Shareable Links** - Create readonly links to share with others
- ✅ **Live Cursors** - See collaborators' cursors in real-time
- ✅ **User Presence** - View who's currently in the session
- ✅ **Self-Hosted Backend** - Full control over your data
  - HTTP Storage Backend with PostgreSQL
  - WebSocket server for real-time updates
  - No dependency on Firebase or third-party services

### Storage & Persistence
- ✅ **Local-First** - Auto-saves to browser (IndexedDB)
- ✅ **PWA Support** - Works offline as Progressive Web App
- ✅ **Custom Backend** - Pluggable storage system
  - HTTP backend with PostgreSQL (default)
  - Firebase backend (optional, for compatibility)
- ✅ **File Storage** - Images and files stored separately for performance
- ✅ **Scene Versioning** - Track changes and updates

### Developer Features
- ✅ **Shape Libraries** - Create and use custom shape libraries
- ✅ **Customizable** - Extensive customization options
- ✅ **npm Package** - Use as React component (`@excalidraw/excalidraw`)
- ✅ **Self-Hostable** - Full Docker setup included
- ✅ **API Access** - Programmatic access to drawing functions

## ❌ Features Missing (Available in Excalidraw+ Only)

### AI Features
These AI-powered features require Excalidraw+ subscription:

- ❌ **Text-to-Diagram** - Generate diagrams from text descriptions
  - This feature uses AI to convert text prompts into Excalidraw drawings
  - Requires `VITE_APP_AI_BACKEND` endpoint (not provided in self-hosted)
  - Rate-limited in free version, unlimited in Excalidraw+

- ❌ **Diagram-to-Code** - Convert diagrams to HTML/React code
  - Converts visual diagrams to working code
  - Uses AI vision to analyze drawings
  - Requires `VITE_APP_AI_BACKEND` endpoint (not provided in self-hosted)
  - Rate-limited in free version, unlimited in Excalidraw+

- ❌ **Mermaid Integration** - Convert Mermaid diagrams to Excalidraw
  - While the UI component exists (`MermaidToExcalidraw`), full integration requires backend
  - Excalidraw+ has enhanced Mermaid support

### Workspace & Organization Features
- ❌ **Excalidraw+ Workspace** - Cloud workspace for saving and organizing drawings
  - Personal workspace with unlimited storage
  - Team workspaces for collaboration
  - Organized folders and collections
  - Cross-device sync

- ❌ **Version History** - Automatic version history and restore
  - Automatic snapshots of your work
  - Browse and restore previous versions
  - Compare versions side-by-side

- ❌ **Extended File Storage** - Higher storage limits
  - Self-hosted version: 3 MiB per file (configurable)
  - Excalidraw+: Higher limits with paid tiers

### Premium Features
- ❌ **Priority Support** - Direct support from Excalidraw team
- ❌ **Early Access** - Get new features before public release
- ❌ **Extended Rate Limits** - Higher API rate limits for AI features
- ❌ **Mobile Apps** - Native iOS/Android apps (Excalidraw+ exclusive)

### Authentication & User Management
- ❌ **User Accounts** - Persistent user accounts with profiles
  - Self-hosted version uses anonymous sessions
  - Excalidraw+ has full user authentication and profiles

- ❌ **Team Management** - Manage team members and permissions
- ❌ **Single Sign-On (SSO)** - Enterprise authentication options

## 🔧 Setting Up AI Features (Advanced)

While the AI features are designed for Excalidraw+, technically savvy users could potentially implement their own AI backend by:

1. Setting up an AI backend service that implements the required endpoints:
   - `/v1/ai/text-to-diagram/generate` - Text to diagram generation
   - `/v1/ai/diagram-to-code/generate` - Diagram to code conversion

2. Configuring the `VITE_APP_AI_BACKEND` environment variable to point to your backend

3. Implementing the API contract expected by the frontend (see `excalidraw-app/components/AI.tsx`)

**Note:** This requires significant development effort and access to AI models (e.g., GPT-4 Vision, Claude, etc.). It's not included in this repository by default.

## 🎯 Which Should You Choose?

### Choose This Self-Hosted Version If:
- ✅ You need full control over your data
- ✅ You have privacy/compliance requirements (GDPR, HIPAA, etc.)
- ✅ You want to avoid subscription costs
- ✅ You don't need AI features
- ✅ You have infrastructure to host applications
- ✅ You want to customize the codebase
- ✅ You're integrating Excalidraw into another product

### Choose Excalidraw+ If:
- ✅ You want AI-powered diagram generation
- ✅ You need automatic version history
- ✅ You prefer a managed service with zero infrastructure
- ✅ You want mobile apps
- ✅ You need team workspaces and organization features
- ✅ You want priority support
- ✅ You're looking for a simple, no-setup solution

## 📦 What This Fork Adds

Beyond the standard open-source Excalidraw, this fork specifically adds:

1. **HTTP Storage Backend** - REST API-based storage (alternative to Firebase)
2. **PostgreSQL Integration** - Persistent storage using PostgreSQL
3. **Docker Setup** - Complete containerized deployment
4. **Pluggable Storage System** - Easy to add new storage backends
5. **Self-Contained** - No external service dependencies required

## 🚀 Getting Started

To run this self-hosted version:

```bash
# Development
docker-compose up -d
docker-compose exec excalidraw yarn install
docker-compose exec excalidraw yarn start

# Production
docker-compose -f docker-compose-prod.yml up -d
```

See [README.md](./README.md) for detailed setup instructions.

## 📚 Additional Resources

- [Official Excalidraw Documentation](https://docs.excalidraw.com)
- [Excalidraw+ Pricing](https://plus.excalidraw.com)
- [Original Excalidraw Repository](https://github.com/excalidraw/excalidraw)
- [This Fork's Repository](https://github.com/arindm007/excalidraw)

## 🤝 Contributing

This is a fork focused on self-hosting capabilities. For core Excalidraw features, contribute to the [upstream project](https://github.com/excalidraw/excalidraw).

For issues specific to this fork's backend integration, please open issues in this repository.

---

**Last Updated:** January 2026

**Note:** Features and capabilities may change over time. Check the official Excalidraw+ website for the most current feature list.
