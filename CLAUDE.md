# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

- **Development server**: `npm run dev` - Runs Next.js development server on port 3000
- **Build**: `npm run build` - Creates production build
- **Production server**: `npm start` - Serves production build
- **Linting**: `npm run lint` - Runs ESLint with Next.js config

## Project Architecture

This is a **Next.js 13+ startup/SaaS template** using the App Router architecture with the following key structure:

### Core Architecture
- **App Router**: Uses Next.js 13+ app directory structure (`/app`)
- **Component-based**: Modular React components in `/components` organized by feature
- **TypeScript**: Full TypeScript support with strict type definitions in `/types`
- **Styling**: Tailwind CSS with custom design system and dark/light theme support
- **Theme System**: `next-themes` for dark/light mode switching via `app/providers.tsx`

### Key Directories
- `/app` - Next.js app router pages and layouts
  - `layout.tsx` - Root layout with Header, Footer, and theme providers
  - `page.tsx` - Homepage composing all landing page sections
  - Route-based pages: `/about`, `/blog`, `/contact`, `/signin`, `/signup`
- `/components` - Reusable React components organized by feature
  - Each major section (Hero, About, Blog, etc.) has its own directory
  - Data files (like `blogData.tsx`, `menuData.tsx`) co-located with components
- `/types` - TypeScript type definitions for data structures
- `/public/images` - Static assets organized by feature/component
- `/styles` - Global CSS (imports Tailwind and component styles)

### Design System
- **Colors**: Custom color palette defined in `tailwind.config.js` with dark/light variants
- **Typography**: Inter font from Google Fonts
- **Responsive**: Custom breakpoints (xs: 450px, sm: 575px, md: 768px, lg: 992px, xl: 1200px, 2xl: 1400px)
- **Theme**: Class-based dark mode with custom shadows and color schemes

### Component Patterns
- Components use consistent patterns for props, styling, and data handling
- Navigation uses `usePathname()` for active state management
- Theme toggling via `ThemeToggler` component in header
- Sticky header behavior with scroll detection
- Mobile-responsive navigation with hamburger menu

### Data Management
- Static data defined in co-located files (e.g., `menuData.tsx`, `blogData.tsx`)
- Type-safe data structures defined in `/types`
- No external API calls or database connections in base template

## Image Configuration
Next.js image optimization is configured for:
- Local images from `/public`
- Remote images from `cdn.sanity.io` (for potential CMS integration)