# Narrative Editor

A comprehensive visual editor for JSON-based narrative games with forum-style dialogue, branching choices, and conditional content.

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![React](https://img.shields.io/badge/React-18-61dafb)

## 🎮 Overview

Narrative Editor is a single-file HTML application for creating interactive narrative games. Built with React and ReactFlow, it provides visual tools for designing branching storylines with conditional content and flag systems.

**Perfect for:** Visual novels, RPG dialogues, interactive fiction, choice-based games

## ✨ Key Features

- 🌳 **Tree View** - Hierarchical editing
- 🗺️ **Graph View** - Visual node representation with minimap
- 🔍 **Advanced Search** - 6 search types (keyword, flag, avatar, user)
- ✏️ **Bulk Edit** - Mass operations on multiple items
- ✅ **Validation** - 10+ validation checks
- 🎮 **Flag Debugger** - Test accessibility
- 👁️ **Preview Mode** - Interactive simulation
- 📊 **Asset Lists** - Track avatars, users, ranks

## 🚀 Quick Start

1. Download `narrative-editor.html`
2. Open in browser (Chrome/Firefox/Edge/Safari)
3. Start editing!

**No build process required!**

## 📖 Usage

### Basic Workflow
```
Load JSON → Edit Content → Set Conditions → Test Flags → Validate → Export
```

### Example Structure
```json
[
  {
    "id": "category_id",
    "title": "Category",
    "threads": [
      {
        "id": "thread_id",
        "title": "Thread",
        "posts": [
          {
            "id": "post_id",
            "type": "original",
            "user_name": "Character",
            "body": "Dialogue text",
            "options": [
              {
                "text": "Choice",
                "reply_body": "Response",
                "set_flag": "FLAG_NAME"
              }
            ]
          }
        ]
      }
    ]
  }
]
```

## 📁 Project Structure

```
narrative-editor/
├── narrative-editor.html          # Main application
├── test-validation-issues.json    # Test file
├── FEATURE-SUMMARY.md             # Full documentation
├── README.md                      # This file
└── LICENSE                        # MIT License
```

## 🛠️ Technical Details

- **Built With:** React 18, ReactFlow 11, Babel
- **File Size:** ~4,100 lines
- **Dependencies:** None (CDN-loaded)
- **Storage:** Browser localStorage for notes/tags

## 🎯 Features

### Editing Tools
- Smart ID generation
- Auto-populate quote text
- Day counter management
- Copy/paste/delete operations

### Search & Replace
- Keyword search
- Text replace
- Flag search (sets/requires)
- Avatar/user search

### Bulk Operations
- Replace avatars
- Replace ranks
- Replace icons  
- Rename flags
- Preview before applying

### Validation
- Duplicate IDs
- Dead ends
- Unreachable content
- Missing fields
- Circular dependencies
- Flag conflicts

### Visual Features
- Color-coded nodes
- Flag badges
- Validation indicators
- Notes/tags icons
- Collapsible branches
- Enhanced minimap

## 💡 Tips

- Use validation frequently
- Test with flag debugger
- Keep threads focused (10-20 posts)
- Export clean JSON (no metadata)
- Back up your files

## 🐛 Known Issues

- File too large for Claude.ai preview (works fine locally)
- Large graphs (500+ nodes) may be slow
- MiniMap: drag viewport, click-to-jump not available

## 🤝 Contributing

Contributions welcome! This is a single-file app:

1. Fork the repository
2. Edit `narrative-editor.html`
3. Test in multiple browsers
4. Submit pull request

## 📝 License

MIT License - see [LICENSE](LICENSE)

## 📊 Stats

- **Features**: 65+
- **Lines of Code**: ~4,100
- **View Modes**: 4
- **Search Types**: 6
- **Bulk Operations**: 6

---

⭐ Star if you find this useful!