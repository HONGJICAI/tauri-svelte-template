# Tauri v2 + Svelte 5 Template

A modern desktop application template built with:
- **Tauri v2** - Build smaller, faster, and more secure desktop applications
- **Svelte 5** - Cybernetically enhanced web apps with runes
- **Vite** - Next generation frontend tooling
- **TypeScript** - Type-safe development
- **Tailwind CSS 4** - Utility-first CSS framework
- **Biome** - Fast formatter and linter
- **pnpm** - Fast, disk space efficient package manager
- **Husky + lint-staged** - Git hooks for quality control

## Features

✨ **Modern Stack**
- Tauri v2 for native desktop capabilities
- Svelte 5 with the latest runes API
- Tailwind CSS 4 with native CSS variables support
- Full TypeScript support

🛠️ **Developer Experience**
- Fast builds with Vite
- Code formatting and linting with Biome
- Pre-commit hooks with Husky
- Staged file linting with lint-staged

🚀 **CI/CD Ready**
- GitHub Actions workflows included
- Multi-platform builds (Windows, macOS, Linux)
- Automated releases

## Prerequisites

- [Node.js](https://nodejs.org/) (v20 or higher)
- [pnpm](https://pnpm.io/) (v10 or higher)
- [Rust](https://www.rust-lang.org/) (latest stable)

### Platform-specific requirements

**Linux:**
```bash
sudo apt update
sudo apt install libwebkit2gtk-4.1-dev \
  build-essential \
  curl \
  wget \
  file \
  libxdo-dev \
  libssl-dev \
  libayatana-appindicator3-dev \
  librsvg2-dev
```

**macOS:**
- Xcode Command Line Tools

**Windows:**
- Microsoft Visual Studio C++ Build Tools

## Getting Started

1. **Clone the repository:**
   ```bash
   git clone https://github.com/HONGJICAI/tauri-svelte-template.git
   cd tauri-svelte-template
   ```

2. **Install dependencies:**
   ```bash
   pnpm install
   ```

3. **Run the development server:**
   ```bash
   pnpm tauri:dev
   ```

## Available Scripts

- `pnpm dev` - Start Vite dev server
- `pnpm build` - Build the frontend
- `pnpm preview` - Preview the built frontend
- `pnpm tauri:dev` - Run Tauri in development mode
- `pnpm tauri:build` - Build the Tauri application
- `pnpm check` - Run Svelte type checking
- `pnpm lint` - Run Biome linter
- `pnpm lint:fix` - Run Biome linter and fix issues
- `pnpm format` - Format code with Biome

## Project Structure

```
tauri-svelte-template/
├── .github/
│   └── workflows/       # GitHub Actions workflows
├── .husky/              # Husky git hooks
├── src/                 # Svelte source files
│   ├── App.svelte       # Main Svelte component
│   ├── app.css          # Global styles with Tailwind
│   ├── main.ts          # Application entry point
│   └── vite-env.d.ts    # Vite type declarations
├── src-tauri/           # Tauri (Rust) source files
│   ├── src/
│   │   ├── main.rs      # Tauri entry point
│   │   └── lib.rs       # Library code
│   ├── icons/           # Application icons
│   ├── Cargo.toml       # Rust dependencies
│   └── tauri.conf.json  # Tauri configuration
├── public/              # Static assets
├── index.html           # HTML entry point
├── package.json         # Node dependencies and scripts
├── pnpm-workspace.yaml  # pnpm workspace configuration
├── biome.json           # Biome configuration
├── postcss.config.js    # PostCSS configuration
├── svelte.config.js     # Svelte configuration
├── tsconfig.json        # TypeScript configuration
└── vite.config.ts       # Vite configuration
```

## Building for Production

Build the application for your current platform:

```bash
pnpm tauri:build
```

The built application will be in `src-tauri/target/release/bundle/`.

## Customization

### Tailwind CSS

Customize Tailwind in `src/app.css`. Tailwind CSS 4 uses CSS variables and the new `@import "tailwindcss"` syntax.

### Biome

Modify linting and formatting rules in `biome.json`.

### Tauri

Configure the application in `src-tauri/tauri.conf.json`:
- Window properties
- Application identifier
- Bundle settings
- Security policies

## CI/CD

Two GitHub Actions workflows are included:

1. **CI** (`.github/workflows/ci.yml`):
   - Runs on push and pull requests
   - Lints and formats code
   - Type checks
   - Builds the application on all platforms

2. **Release** (`.github/workflows/release.yml`):
   - Triggers on version tags (e.g., `v1.0.0`)
   - Builds and publishes releases for all platforms

## License

This template is open source and available under the MIT License.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.