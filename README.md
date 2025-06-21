# Adroja Dhairya - Portfolio Website

A modern, interactive terminal-themed portfolio built with SvelteKit, TypeScript, and Tailwind CSS. This portfolio showcases my projects, skills, and experience as a Full Stack Developer.

## 🚀 Features

- **Terminal-Themed Design**: Interactive command-line interface experience
- **Responsive Design**: Optimized for all devices and screen sizes
- **Performance Optimized**: Fast loading with modern web technologies
- **SEO Friendly**: Comprehensive meta tags and structured data
- **Analytics Integration**: Built-in analytics for tracking user interactions
- **Interactive Commands**: Navigate using terminal commands
- **Easter Eggs**: Hidden retro gaming quotes and fun interactions

## 🛠️ Tech Stack

- **Framework**: SvelteKit 2.0
- **Language**: TypeScript
- **Styling**: Tailwind CSS 4.0
- **Package Manager**: pnpm
- **Analytics**: Vercel Analytics
- **Deployment**: Vercel (recommended)

## 📦 Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/Dhairya3391/portfolio.git
   cd portfolio
   ```

2. **Install dependencies**

   ```bash
   pnpm install
   ```

3. **Start development server**

   ```bash
   pnpm run dev
   ```

4. **Open your browser**
   Navigate to `http://localhost:5173`

## 🎮 Available Commands

The portfolio features an interactive terminal interface. Try these commands:

- `ls` or `ls -la` - View navigation menu
- `whoami` or `cat about.txt` - View about section
- `cat skills.txt` - View skills section
- `ls projects` - View projects section
- `cat contact.txt` - View contact information
- `clear` - Scroll to top
- `retro` - Show random retro gaming quote
- `help` - Show available commands

## 📁 Project Structure

```
src/
├── routes/
│   ├── lib/
│   │   └── components/
│   │       ├── Hero.svelte          # Landing section
│   │       ├── About.svelte         # About section
│   │       ├── Skills.svelte        # Skills showcase
│   │       ├── Projects.svelte      # Project portfolio
│   │       ├── Contact.svelte       # Contact information
│   │       ├── Navigation.svelte    # Command navigation
│   │       └── Terminal.svelte      # Global terminal
│   ├── App.svelte                   # Main application
│   ├── +layout.svelte              # Layout wrapper
│   └── +page.svelte                # Home page
├── app.css                         # Global styles
├── app.html                        # HTML template
└── app.d.ts                        # TypeScript declarations
```

## 🚀 Deployment

### Vercel (Recommended)

1. **Install Vercel CLI**

   ```bash
   npm i -g vercel
   ```

2. **Deploy**
   ```bash
   pnpm run deploy
   ```

### Manual Build

1. **Build for production**

   ```bash
   pnpm run build
   ```

2. **Preview build**
   ```bash
   pnpm run preview
   ```

## 🎨 Customization

### Colors

The terminal theme uses CSS custom properties defined in `src/app.css`:

```css
:root {
  --terminal-dark: #121212;
  --terminal-light: #e0e0e0;
  --terminal-pink: #ffb3ba;
  --terminal-purple: #6a0dad;
}
```

### Content

- Update project information in `src/routes/lib/components/Projects.svelte`
- Modify personal details in `src/routes/lib/components/About.svelte`
- Update contact information in `src/routes/lib/components/Contact.svelte`

## 📊 Analytics

The portfolio includes Vercel Analytics for tracking user interactions. Analytics are automatically initialized in the layout component.

## 🔧 Development Scripts

- `pnpm run dev` - Start development server
- `pnpm run build` - Build for production
- `pnpm run preview` - Preview production build
- `pnpm run check` - Type check
- `pnpm run format` - Format code with Prettier
- `pnpm run lint` - Lint code
- `pnpm run analyze` - Analyze bundle size

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📞 Contact

- **Email**: dhairyaadroja3391@gmail.com
- **LinkedIn**: [Adroja Dhairya](https://www.linkedin.com/in/adroja-dhairya-203b85348/)
- **GitHub**: [@Dhairya3391](https://github.com/Dhairya3391)
- **Twitter**: [@AdrojaDhairya1](https://twitter.com/AdrojaDhairya1)

---

Built with ❤️ using SvelteKit and TypeScript
