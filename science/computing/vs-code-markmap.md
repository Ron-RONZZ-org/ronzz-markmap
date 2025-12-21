# VS Code

## Keyboard shortcuts

### Line operations

- `SHIFT+DELETE`
  - Delete entire line
- `CTRL+L`
  - Select line
  - Press repeatedly for multiple lines
- `ALT+↑/↓`
  - Move line up/down
- `ALT+SHIFT+↓`
  - Duplicate line

### Selection

- `ALT+SHIFT+→`
  - Smart selection
  - Expand selection
- `CTRL+SHIFT+↑/↓`
  - Multi-cursor
  - Same position above/below
- `CTRL+D`
  - Select next occurrence
- `SHIFT+Arrow keys`
  - Character/line selection
- Multi-line in indent-sensitive languages
  - Option 1: `HOME+SHIFT+END`, then `SHIFT+↓`
  - Option 2: `END`, then `SHIFT+↑/↓`

### Terminal

- `CTRL+`` (backtick)
  - Open/toggle terminal
- `CTRL+SHIFT+`` (backtick)
  - Create new terminal
- `ALT+←/→`
  - Switch between terminals (split)
- `CTRL+PageUp/PageDown`
  - Switch terminal groups (tabs)

## Settings

### Editor configuration

```json
{
  "editor.insertSpaces": true,
  "editor.tabSize": 2,
  "editor.formatOnSave": true
}
```

### Common settings

- Auto save
- Font size
- Theme
- Extensions
- Keybindings

## Navigation

### File operations

- Close tabs
  - Right-click tab
  - Close Others
  - Close All
  - Close to Right
- Split editor
  - Vertical/horizontal
- Switch between files
  - `CTRL+Tab`

### Code navigation

- Go to definition
  - `F12`
- Peek definition
  - `ALT+F12`
- Go to symbol
  - `CTRL+SHIFT+O`
- Command palette
  - `CTRL+SHIFT+P`

## Linting

- Language-specific
  - Pylance: `# type: ignore`
  - ESLint: `// eslint-disable-next-line`
- Turn off for file
  - Add comment at top
- Configure in settings
  - Per-language rules

## Extensions

### Popular extensions

- GitLens
  - Git supercharged
- Prettier
  - Code formatter
- ESLint
  - JavaScript linter
- Python
  - IntelliSense, linting
- Live Server
  - Local development server
- Remote SSH
  - Edit files on remote

### Extension management

- Install
  - Search in Extensions view
- Disable
  - Per workspace
  - Globally
- Uninstall
- Update

## Tips and tricks

### Multi-cursor

- `CTRL+ALT+↑/↓`
  - Add cursor above/below
- `ALT+Click`
  - Add cursor at position
- `CTRL+D`
  - Select next match

### Search and replace

- `CTRL+F`
  - Find
- `CTRL+H`
  - Find and replace
- `CTRL+SHIFT+F`
  - Search in files
- Regex support
- Case sensitive
- Whole word

### Snippets

- Built-in snippets
- Custom snippets
- Extension snippets
- Tab completion

## Workspace

- Multi-root workspace
- Settings hierarchy
  - User
  - Workspace
  - Folder
- Tasks
  - Build
  - Test
  - Run
- Launch configurations
  - Debug settings
