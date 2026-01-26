# Obsidian Template Vault 🔮

A personal Obsidian vault template with pre-configured plugins and reusable templates for note-taking, project management, and documentation.

## 📁 Vault Structure

```
obsidian-template/
├── .obsidian/           # Obsidian configuration and plugins
│   ├── plugins/         # 33 installed plugins
│   └── workspace.json   # User-specific workspace (not tracked)
│
└── topics/
    └── templates/       # Reusable note templates
```

## 🔌 Included Plugins (33)

### Productivity & Navigation
- **homepage** - Custom homepage for your vault
- **darlal-switcher-plus** - Enhanced quick switcher
- **pane-relief** - Better pane management
- **reveal-active-file-button** - Quick file reveal in explorer
- **obsidian-tagfolder** - Organize notes by tags

### Note Creation & Templates
- **templater-obsidian** - Advanced templating engine
- **notes-dater** - Date management for notes
- **obsidian-filename-heading-sync** - Sync filenames with headings

### Formatting & Styling
- **code-styler** - Enhanced code block styling
- **codeblock-customizer** - Customize code blocks
- **colored-text** - Color text in notes
- **obsidian-format-code** - Auto-format code
- **obsidian-plugin-prettier** - Prettier integration
- **markdown-to-slack-message** - Convert Markdown to Slack format

### Diagrams & Visual Tools
- **obsidian-excalidraw-plugin** - Hand-drawn diagrams
- **obsidian-diagrams-net** / **drawio-obsidian** - Draw.io integration
- **mermaid-themes** - Custom mermaid diagram themes

### Media & Gallery
- **obsidian-gallery** / **note-gallery** - Image galleries
- **obsidian-thumbnails** - Thumbnail previews
- **copy-image** - Better image handling

### File Management
- **obsidian-bulk-rename-plugin** - Batch rename files
- **obsidian-file-info-plugin** - File metadata display
- **obsidian-table-to-csv-exporter** - Export tables to CSV

### Utilities
- **dataview** - Query and display data from notes
- **obsidian-vault-statistics-plugin** - Vault statistics
- **obsidian-editor-shortcuts** - Enhanced editor shortcuts
- **emoji-shortcodes** - Easy emoji insertion
- **marker-api** - Marker functionality
- **mlir-syntax-highlight** - MLIR syntax highlighting
- **obsidian-prozen** - Zen mode for writing
- **confluence-to-obsidian** - Import from Confluence

## 📝 Available Templates

### Work & Projects
- **Note template** - Basic note structure
- **PROJECT-NUMBER Ticket template** - Project ticket documentation
- **Tasks** - Task management template

### Daily Standup & Meetings
- **MM-2025-Daily-Standup template** - Daily standup notes
- **Retro meeting DD-MM-YYYY template** - Retrospective meetings
- **Sprint planning DD-MM-YYYY template** - Sprint planning
- **Sprint review DD-MM-YYYY template** - Sprint review
- **Reflection talk DD-MM-YYYY template** - Reflection sessions

### Pull Requests & Code Review
- **Pull request template** - Standard PR description
- **Pull request medium template** - Medium-sized PRs
- **Pull request short template** - Quick PRs
- **Pull request remarks template** - PR review comments

### Other Templates
- **Absence note DD-MM-YYYY template** - Absence notifications
- **OPSESC-XXXX** - Operations/security template

## 🚀 Getting Started

1. **Clone the repository:**
   ```bash
   git clone git@github.com:velizartodorov/obsidian-template.git
   ```

2. **Open in Obsidian:**
   - Open Obsidian
   - Click "Open folder as vault"
   - Select the cloned `obsidian-template` directory

3. **Enable Community Plugins:**
   - Settings → Community plugins → Turn off Safe Mode
   - All plugins will be loaded automatically

4. **Start using templates:**
   - Access templates from `topics/templates/`
   - Use Templater plugin to insert templates into notes

## 📌 Git Configuration

This vault tracks:
- ✅ `.obsidian/` - All plugins and settings
- ✅ `topics/templates/` - All template files
- ❌ `workspace.json` - User-specific workspace state (ignored)

The `.gitignore` is configured to only track essential configuration and templates, while ignoring personal notes and workspace state.

## 📄 License

Personal template for individual use.
