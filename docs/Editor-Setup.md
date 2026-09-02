# Editor Setup Guide

Choosing the right code editor helps you get started quickly and catch mistakes early. While you are welcome to use any editor you prefer (such as [Cursor](https://www.cursor.com/), [Zed](https://zed.dev/), [Sublime Text](https://www.sublimetext.com/), or [Neovim](https://neovim.io/)), we officially recommend **Visual Studio Code** or **JetBrains WebStorm** for beginners.

---

## Editor Comparison: VS Code vs. WebStorm

| Feature / Aspect | Visual Studio Code (VS Code) | JetBrains WebStorm |
| :--- | :--- | :--- |
| **Pricing** | Completely free & open-source | Paid, but **100% free for students** via [JetBrains Education](https://www.jetbrains.com/community/education/#students) |
| **Setup** | Lightweight core; you customize it with extensions | Fully configured out of the box with robust tooling |
| **Performance** | Fast startup, low initial memory footprint | Feature-rich IDE; can use more memory/CPU |
| **Ecosystem** | Huge community and extension marketplace | Deeply integrated refactoring, Git tools, and debugging |

---

## 1. Visual Studio Code (Recommended)

[Visual Studio Code (VS Code)](https://code.visualstudio.com/) is the most popular editor for web development.

### Recommended Extensions
Install these extensions from the VS Code Extensions tab (`Ctrl+Shift+X` or `Cmd+Shift+X`):

1. **[ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)**: Highlights code quality issues and bugs directly in your editor as you type.
2. **[Prettier - Code Formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)**: Automatically formats code to keep consistent style across the codebase.
3. **[Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)**: Provides intelligent autocomplete, color previews, and hover documentation for Tailwind classes.
4. **[Pretty TypeScript Errors](https://marketplace.visualstudio.com/items?itemName=yoavbls.pretty-ts-errors)**: Makes TypeScript compiler errors readable and beginner-friendly.
5. **[ES7+ React/Redux/React-Native snippets](https://marketplace.visualstudio.com/items?itemName=rodrigovallades.es7-react-js-snippets)**: Fast snippets for generating React component boilerplates (e.g., `rafce`).
6. **[Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)**: Automatically renames matching HTML/JSX tags when you change either the opening or closing tag.

### Recommended Settings
Enable automatic formatting on save in `settings.json` (`Ctrl+,` / `Cmd+,` > Search "Format On Save"):
```json
{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": "explicit"
  }
}
```

---

## 2. JetBrains WebStorm

[WebStorm](https://www.jetbrains.com/webstorm/) is a dedicated JavaScript/TypeScript IDE with comprehensive built-in tools.

### Getting WebStorm for Free
- If you are a student with an `.edu` email address, apply for a free [JetBrains Student Pack](https://www.jetbrains.com/community/education/#students).

### WebStorm Configuration
WebStorm includes TypeScript, React, and Next.js support natively. To ensure optimal project formatting:
1. **Prettier on Save**: Go to `Settings` (or `Preferences` on macOS) > `Languages & Frameworks` > `JavaScript` > `Prettier`. Check **"Automatic Prettier configuration"** and check **"Run on save"**.
2. **ESLint**: Go to `Settings` > `Languages & Frameworks` > `JavaScript` > `Code Quality Tools` > `ESLint`. Select **"Automatic ESLint configuration"** and enable **"Run eslint --fix on save"**.
3. **Tailwind CSS**: WebStorm provides built-in Tailwind support under `Settings` > `Languages & Frameworks` > `Style Sheets` > `Tailwind CSS`.
