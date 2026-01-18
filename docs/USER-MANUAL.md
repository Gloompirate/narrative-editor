# Narrative Editor - User Manual

**Version:** 1.5 (Batch 14 Complete)  
**Date:** January 2025  
**For:** Bug Testing & User Documentation

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [Interface Overview](#interface-overview)
3. [Basic Operations](#basic-operations)
4. [Views & Modes](#views--modes)
5. [Advanced Features](#advanced-features)
6. [Data Management](#data-management)
7. [Keyboard Shortcuts](#keyboard-shortcuts)
8. [Testing Guide](#testing-guide)
9. [Known Limitations](#known-limitations)
10. [Troubleshooting](#troubleshooting)

---

## Getting Started

### Opening the Editor

1. Open `narrative-editor.html` in a modern web browser (Chrome, Edge, Firefox, Safari)
2. The editor loads with sample data automatically
3. No installation or server required - it's a single HTML file

### First Steps

1. **Explore the sample data** - Familiarize yourself with the structure
2. **Try different views** - Click the view buttons at top
3. **Edit something** - Click a category/thread/post in tree view
4. **Save your work** - Use "💾 Save Project" to export everything

---

## Interface Overview

### Main Components

```
┌─────────────────────────────────────────────────────────┐
│  Toolbar (Add/Delete/Import/Export/Undo/Redo/Utilities) │
├───────────────┬─────────────────────────────────────────┤
│               │                                         │
│   Tree View   │         Editor Panel                    │
│   (Left)      │         (Right)                         │
│               │                                         │
│  Categories   │    Edit selected item here              │
│  └─ Threads   │    - Title/Subtitle                     │
│     └─ Posts  │    - Content                            │
│               │    - Conditions                         │
│               │    - Options (choices)                  │
└───────────────┴─────────────────────────────────────────┘
```

### Toolbar Buttons

| Button | Function |
|--------|----------|
| **+ Category** | Add new category |
| **+ Thread** | Add thread to selected category |
| **+ Post** | Add post to selected thread |
| **Delete Selected** | Remove selected item |
| **↶ Undo** | Undo last change (Ctrl+Z) |
| **↷ Redo** | Redo last undone change (Ctrl+Y) |
| **Export JSON** | Export just the narrative data |
| **Import JSON** | Import narrative data |
| **💾 Save Project** | Save complete project (data + notes + tags + assets + users + snapshots) |
| **📂 Load Project** | Load complete project file (.neproj) |
| **⏮️ Load Auto-save** | Restore from auto-save (saved every 30 seconds) |
| **🧰 Utilities** | Open utilities panel |

### View Buttons

| View | Purpose |
|------|---------|
| **Tree View** | Hierarchical editing (default) |
| **Graph View** | Visual flow diagram |
| **📖 Screenplay** | Linear reading mode |
| **👁️ Preview** | Test the narrative as a player |
| **JSON View** | Raw data editing |

---

## Basic Operations

### Creating Content

#### Add a Category
1. Click **"+ Category"** in toolbar
2. Edit the title, subtitle, and icon in the editor panel
3. Category appears at bottom of tree

#### Add a Thread
1. Select a category in the tree view
2. Click **"+ Thread"** in toolbar
3. Edit thread details in the editor panel

#### Add a Post
1. Select a thread in the tree view
2. Click **"+ Post"** in toolbar
3. Edit post content, user, and body

### Editing Content

1. Click any item in tree view to select it
2. Edit fields in the right panel
3. Changes save automatically
4. Use **Undo** (Ctrl+Z) if you make a mistake

### Deleting Content

1. Select an item in tree view
2. Click **"Delete Selected"** button
3. Confirm the deletion
4. Item is removed (use Undo to restore)

### Moving Content

**Drag and Drop:**
- Drag threads between categories
- Drag posts within threads to reorder
- Visual indicators show drop targets

---

## Views & Modes

### 1. Tree View (Default)

**Purpose:** Main editing interface

**Features:**
- Hierarchical structure
- Expand/collapse items
- Drag and drop
- Color-coded items
- Validation badges

**Tips:**
- Click folder icons to expand/collapse
- Right panel updates when you select items
- Use search to find items quickly

---

### 2. Graph View

**Purpose:** Visual flow diagram of your narrative

**Layout Controls:**
- **➡️ Horizontal** - Categories on left, flows right
- **⬇️ Vertical** - Categories on top, flows down
- Layout preference is remembered

**Node Types:**
- 🟢 **Categories** - Green rectangles
- 🟡 **Threads** - Yellow rectangles  
- 🔵 **Posts (Original)** - Blue rounded
- 🟠 **Posts (Reply)** - Orange rounded
- 🟡 **Posts (Alert)** - Yellow rounded

**Interactions:**
- **Click** node - Select it
- **Double-click** node - Open detail modal
- **Right-click** node - Context menu:
  - ➕ Add Thread/Post
  - ✏️ Edit (switches to tree view)
  - 🗑️ Delete
- **Drag viewport** in minimap - Pan around
- **Mouse wheel** - Zoom in/out
- **Click flag badge** - Highlight flag dependencies

**Legend:** Top-right corner shows node types and edge meanings

**Minimap:** Bottom-right shows full graph, click/drag to navigate

**Flag Debugger:** 
- Toggle with "🐛 Flag Debugger" button
- Set active flags to test conditions
- See which posts would appear with current flags

---

### 3. Screenplay View

**Purpose:** Read your narrative like a script

**Features:**
- **Thread Selector** (left sidebar)
  - Browse all threads
  - Click to switch threads
  - Shows post count

- **Reading Area** (main)
  - Clean typography
  - Quote boxes for replies
  - Choice blocks highlighted
  - Flag indicators
  - User metadata (name, rank, day)

**Inline Editing:**
- **Click any post** to edit
- Edit form appears with:
  - User picker dropdown
  - User name field
  - User rank field
  - Post body textarea
- **Save** or **Cancel** buttons
- Changes save to main data

**Color Coding:**
- Blue - Original posts
- Orange - Reply posts (with left border)
- Yellow - Alert posts

---

### 4. Preview Mode

**Purpose:** Test your narrative as a player would experience it

**Features:**
- **Simulated Player View**
- **Forum-style display**
- **Interactive choices**
- **Flag system simulation**
- **Day progression**

**How to Use:**
1. Set starting conditions (day, flags)
2. Navigate through categories/threads
3. Click choice buttons to set flags
4. See how content changes based on flags

**Controls:**
- Day slider - Simulate progression
- Reset button - Start over
- Category/thread navigation

---

### 5. JSON View

**Purpose:** Direct data editing for advanced users

**Features:**
- Syntax-highlighted JSON
- Line numbers
- Real-time validation
- Apply/Discard buttons

**When to Use:**
- Bulk text changes
- Complex structural edits
- Copy/paste data
- Learn the data format

**Warning:** Invalid JSON will show error and won't apply

---

## Advanced Features

### Utilities Panel (🧰)

Access via toolbar button. Contains 8 tabs:

#### 1. 🏁 Flag Manager

**Purpose:** View and manage all flags in your narrative

**Features:**
- List of all flags used
- Shows where each flag is set
- Shows where each flag is required
- Click flag name to highlight in graph
- Search through flags

**Use Cases:**
- Find orphaned flags (set but never checked)
- Find unreachable content (requires flag never set)
- Audit flag usage

---

#### 2. 🔍 Search

**6 Search Types:**

1. **Text Search**
   - Find in titles, subtitles, bodies
   - Case-insensitive
   - Shows all matches with paths

2. **ID Search**
   - Find by exact ID
   - Useful for debugging

3. **Flag Search**
   - Find posts that use specific flag
   - Shows setters and checkers

4. **User Search**
   - Find all posts by a user
   - Shows post count

5. **Conditions Search**
   - Find posts with specific conditions
   - Day requirements
   - Flag requirements

6. **Choice Search**
   - Find posts with player choices
   - Shows option count

**Results:**
- Click any result to select that item
- Automatically switches to tree view
- Item is highlighted

---

#### 3. 🔄 Bulk Operations

**6 Operation Types:**

1. **Find & Replace**
   - Search text
   - Replace with new text
   - Scope: All, Categories, Threads, Posts
   - Shows replacement count

2. **Add Flag to Multiple**
   - Select posts
   - Add same flag to all
   - Useful for bulk requirements

3. **Update Day Requirements**
   - Select posts
   - Set min/max day
   - Bulk condition editing

4. **Bulk Tag Assignment**
   - Select posts
   - Assign same tag
   - Organize content

5. **Reset Timestamps**
   - Renumber all post timestamps
   - Maintains order
   - Fixes gaps

6. **Generate Reply Posts**
   - Select a post with choices
   - Auto-create reply posts for each option
   - Saves time on branching

**Selection:**
- Use checkboxes in tree view
- Or use search to select multiple

---

#### 4. ✅ Validation

**Purpose:** Find errors and potential issues

**Categories:**

1. **Errors** (Red) - Must fix
   - Missing required fields
   - Duplicate IDs
   - Circular dependencies
   - Invalid references

2. **Warnings** (Yellow) - Should check
   - Flag conflicts (same flag set multiple times)
   - Orphaned flags (set but never used)
   - Unreachable content (conditions never met)
   - Timestamp issues

3. **Info** (Blue) - Suggestions
   - Optimization tips
   - Best practices

**Actions:**
- Click issue to select that item
- Fix in tree view or editor panel
- Re-run validation to verify

---

#### 5. 🗒️ Notes & Tags

**Notes:**
- Add notes to any category/thread/post
- Markdown supported
- Private (not in JSON export)
- Searchable

**Tags:**
- Organize content with tags
- Multiple tags per item
- Color-coded
- Filter by tag

**Use Cases:**
- Mark "needs review" items
- Track completion status
- Group related content
- Development notes

---

#### 6. 🎨 Asset Browser

**Purpose:** View all sprites (avatars, icons) used

**Features:**
- Visual gallery
- Shows all unique sprites
- Click to copy sprite name
- Organized by type (avatars, icons)
- Shows usage count

**Upload Assets:**
- Drag and drop images
- PNG, JPG, GIF, WebP supported
- Stores as base64
- Reusable across project

---

#### 7. 👥 User Library

**Purpose:** Manage character profiles

**Features:**

**Create Users:**
- Name (required)
- Rank
- Avatar sprite
- Biography (for future AI use)
- Status (Active/Inactive)

**Import from Posts:**
- Scans all posts for unique users
- Auto-detects rank and avatar
- One-click import
- Prevents duplicates

**Edit Users:**
- Click "✏️ Edit" on any user card
- Inline editing
- Changes save immediately

**Quick-Select:**
- When creating posts, use dropdown
- Auto-fills name, rank, avatar
- Saves time
- Only shows active users

**Deactivate:**
- Mark users as inactive (for deaths)
- Hidden from picker
- Preserved in data

---

#### 8. 📸 Snapshots

**Purpose:** Save named versions of your narrative

**Features:**

**Create Snapshot:**
- Click "📸 Create Snapshot"
- Enter a name
- Saves complete state (data, notes, tags)
- Stores locally

**Restore Snapshot:**
- Click "↶ Restore" on any snapshot
- Confirms before restoring
- Current work saved to undo history

**Delete Snapshot:**
- Click "🗑️ Delete" to remove
- Confirms before deleting

**Use Cases:**
- Before major changes
- Milestone markers
- Experiment branches
- Backup points

**Info Panel:** Explains snapshot usage

---

### Undo/Redo System

**Features:**
- 50-step history
- Tracks all changes
- Persists in session (not across refreshes)

**Keyboard Shortcuts:**
- **Ctrl+Z** (Cmd+Z on Mac) - Undo
- **Ctrl+Y** (Cmd+Y on Mac) - Redo
- **Ctrl+Shift+Z** (Cmd+Shift+Z on Mac) - Redo (alternative)

**Toolbar Buttons:**
- **↶ Undo** - Disabled when at start of history
- **↷ Redo** - Disabled when at end of history

**What's Tracked:**
- Content creation/deletion
- Content editing
- Moving items
- Property changes
- Bulk operations

---

### User Library Workflow

**Setup:**
1. Go to Utilities → 👥 User Library
2. Click "📥 Import from Posts" to get existing users
3. Or click "Create New User" to add manually

**Usage:**
1. When creating a post, use "Select User from Library" dropdown
2. Choose a user
3. Name, rank, and avatar auto-fill
4. Edit post body as normal

**Management:**
- Edit users by clicking "✏️ Edit"
- Deactivate users when characters die
- Delete unused users
- Keep biographies for AI features (future)

---

### Timeline View

**Purpose:** See narrative flow organized by in-game days

**Features:**
- Posts grouped by day (based on min_day condition)
- Chapter markers
- Scroll through timeline
- Visual progress indicator

**Navigation:**
- Scroll vertically through days
- Click any post to select it
- See how story unfolds chronologically

---

### Smart ID Generation

**Purpose:** Automatic, readable IDs for all items

**Format:**
- Categories: `cat_categoryname`
- Threads: `th_threadname`
- Posts: `p_contentsnippet`

**Features:**
- Uses title/content words
- Removes common words (the, a, an, etc.)
- Ensures uniqueness
- Lowercase with underscores

**Example:** Thread titled "Report from the Field" → `th_report_field`

---

## Data Management

### Saving & Loading

**Three Save Methods:**

1. **Auto-save** (Every 30 seconds)
   - Saves data to browser localStorage
   - Automatic, no action needed
   - Recover with "⏮️ Load Auto-save"

2. **Export JSON** (Data only)
   - Exports narrative data as .json
   - No notes, tags, or assets
   - Smaller file size
   - For sharing just the narrative

3. **💾 Save Project** (Complete)
   - Exports everything to .neproj file
   - Includes: data, notes, tags, assets, users, snapshots
   - Recommended for backups
   - Portable between computers

**Loading:**

1. **Import JSON**
   - Loads .json narrative data
   - Replaces current data
   - Asks for confirmation

2. **📂 Load Project**
   - Loads .neproj complete project
   - Restores everything
   - Refreshes browser after load

3. **⏮️ Load Auto-save**
   - Restores last auto-saved version
   - Shows save time
   - Useful after mistakes

---

### Data Persistence

**What's Saved Automatically:**
- ✅ Data (auto-save every 30 seconds)
- ✅ Notes (on change)
- ✅ Tags (on change)
- ✅ Assets (on upload)
- ✅ User library (on change)
- ✅ Snapshots (on creation)
- ✅ Graph layout preference (on change)

**What's Saved in Session Only:**
- ⏳ Undo/redo history (lost on refresh)
- ⏳ Selected item
- ⏳ Expanded items in tree
- ⏳ Current view
- ⏳ Search results

---

### Browser Storage

**Location:** Browser localStorage

**Storage Keys:**
- `narrative-editor-data-autosave` - Main data
- `narrative-editor-data-autosave-time` - Save timestamp
- `narrative-editor-notes` - Notes
- `narrative-editor-tags` - Tags
- `narrative-editor-assets` - Uploaded images
- `narrative-editor-users` - User library
- `narrative-editor-snapshots` - Saved snapshots
- `narrative-editor-layout` - Graph layout preference

**Clearing Storage:**
- Browser refresh keeps data
- Browser cache clear removes data
- Use "Save Project" for permanent backup

---

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| **Ctrl+Z** / **Cmd+Z** | Undo |
| **Ctrl+Y** / **Cmd+Y** | Redo |
| **Ctrl+Shift+Z** / **Cmd+Shift+Z** | Redo (alternative) |

*Note: More shortcuts planned for future updates*

---

## Testing Guide

### Critical Paths to Test

#### 1. Basic Content Creation
- [ ] Create category
- [ ] Create thread in category
- [ ] Create post in thread
- [ ] Edit post content
- [ ] Delete post
- [ ] Undo delete
- [ ] Redo delete

#### 2. Content Organization
- [ ] Drag thread to different category
- [ ] Drag post within thread
- [ ] Expand/collapse categories
- [ ] Navigate with tree view
- [ ] Select items

#### 3. Views
- [ ] Switch to Graph view
- [ ] Toggle horizontal/vertical layout
- [ ] Right-click node in graph
- [ ] Create from context menu
- [ ] Switch to Screenplay view
- [ ] Click post to edit in screenplay
- [ ] Switch to Preview mode
- [ ] Test choices in preview
- [ ] Switch to JSON view
- [ ] Edit JSON directly

#### 4. Search & Find
- [ ] Text search
- [ ] ID search
- [ ] Flag search
- [ ] User search
- [ ] Conditions search
- [ ] Choice search

#### 5. Bulk Operations
- [ ] Find & replace
- [ ] Add flag to multiple posts
- [ ] Update day requirements
- [ ] Bulk tag assignment
- [ ] Reset timestamps
- [ ] Generate reply posts

#### 6. Validation
- [ ] Run validation
- [ ] Fix an error
- [ ] Re-run validation
- [ ] Check warnings

#### 7. Notes & Tags
- [ ] Add note to item
- [ ] Add tag to item
- [ ] View note in panel
- [ ] Remove tag

#### 8. Assets
- [ ] Upload image
- [ ] Use image as avatar
- [ ] View in asset browser
- [ ] Copy sprite name

#### 9. User Library
- [ ] Create user manually
- [ ] Import users from posts
- [ ] Edit user
- [ ] Deactivate user
- [ ] Use user picker in post editor
- [ ] Verify inactive users hidden

#### 10. Snapshots
- [ ] Create snapshot
- [ ] Restore snapshot
- [ ] Delete snapshot
- [ ] Create multiple snapshots

#### 11. Save & Load
- [ ] Export JSON
- [ ] Import JSON
- [ ] Save project (.neproj)
- [ ] Load project
- [ ] Verify all data restored

#### 12. Undo/Redo
- [ ] Make multiple changes
- [ ] Undo several times
- [ ] Redo several times
- [ ] Make change after undo (history fork)

---

### Edge Cases to Test

#### Data Integrity
- [ ] Create post with empty body
- [ ] Use special characters in titles
- [ ] Create very long content (10,000+ chars)
- [ ] Delete category with threads
- [ ] Delete thread with posts
- [ ] Undo after deleting category

#### Flags
- [ ] Create circular flag dependency
- [ ] Use flag that's never set
- [ ] Set flag that's never used
- [ ] Multiple choices setting same flag

#### Choices
- [ ] Post with 10+ options
- [ ] Choice with empty text
- [ ] Choice setting multiple flags
- [ ] Nested choices (choice → post with choices)

#### Performance
- [ ] 100+ posts in a thread
- [ ] 50+ threads in a category
- [ ] 10+ categories
- [ ] Large JSON import (1MB+)
- [ ] Rapid undo/redo (50 times)

#### Browser Compatibility
- [ ] Test in Chrome
- [ ] Test in Firefox
- [ ] Test in Safari
- [ ] Test in Edge
- [ ] Test on mobile (touch)

---

### Bug Reporting Template

When you find a bug, please report with:

```
**Bug Title:** [Short description]

**Severity:** [Critical / High / Medium / Low]

**Steps to Reproduce:**
1. 
2. 
3. 

**Expected Behavior:**
[What should happen]

**Actual Behavior:**
[What actually happens]

**Browser:** [Chrome 120, Firefox 121, etc.]

**Console Errors:** [Any errors in browser console]

**Screenshots:** [If applicable]

**Data File:** [Attach .neproj if needed to reproduce]
```

---

## Known Limitations

### Current Version

1. **Single File Only**
   - No multi-user editing
   - No cloud sync
   - Manual save/load required

2. **Browser Storage**
   - Limited to ~5-10MB
   - Can be cleared by browser
   - Must use "Save Project" for backup

3. **No Real-Time Collaboration**
   - One user at a time
   - Share via .neproj files

4. **Undo History**
   - Limited to 50 steps
   - Lost on browser refresh
   - Use snapshots for longer history

5. **Graph View**
   - Very large graphs (1000+ nodes) may be slow
   - No custom node positioning (auto-layout only)

6. **Preview Mode**
   - Simulates player view but doesn't run actual game engine
   - Some complex conditions may not preview accurately

---

## Troubleshooting

### Problem: Data disappeared after browser refresh

**Solution:**
- Click "⏮️ Load Auto-save" to restore
- Data is auto-saved every 30 seconds
- Always use "💾 Save Project" for important work

---

### Problem: Can't import JSON file

**Possible Causes:**
- Invalid JSON syntax
- Wrong file format

**Solution:**
- Check file is valid JSON
- Try opening in text editor to verify
- Look for missing commas, brackets

---

### Problem: Validation shows false errors

**Possible Causes:**
- Complex nested conditions
- Timing-based logic

**Solution:**
- Review the specific error message
- Check if it's an "Info" level (just suggestions)
- Test in Preview mode to verify behavior

---

### Problem: Graph view is slow or laggy

**Possible Causes:**
- Too many nodes (500+)
- Complex connections

**Solution:**
- Use Tree view for large projects
- Collapse unused categories
- Consider splitting into multiple files

---

### Problem: Can't undo changes

**Possible Causes:**
- Browser was refreshed (undo history cleared)
- More than 50 changes made

**Solution:**
- Use snapshots for important save points
- Restore from auto-save if needed
- Regular "Save Project" exports

---

### Problem: Image uploads not working

**Possible Causes:**
- File too large (>5MB)
- Unsupported format

**Solution:**
- Use PNG, JPG, GIF, or WebP
- Compress images before upload
- Keep under 1MB for best performance

---

### Problem: Right-click context menu doesn't appear (Graph)

**Possible Causes:**
- Browser blocking context menu
- Clicked outside of node

**Solution:**
- Right-click directly on a node (not empty space)
- Ensure you're in Graph view
- Try a different browser

---

## Quick Reference Card

### Must-Know Features

| Task | How To |
|------|--------|
| **Create content** | Use toolbar buttons or right-click in graph |
| **Edit content** | Click item in tree, edit in right panel |
| **Delete content** | Select item, click "Delete Selected" |
| **Save work** | Click "💾 Save Project" (saves everything) |
| **Load work** | Click "📂 Load Project", select .neproj file |
| **Undo mistake** | Ctrl+Z or click "↶ Undo" |
| **Find something** | Go to Utilities → 🔍 Search |
| **Check for errors** | Go to Utilities → ✅ Validation |
| **Create snapshot** | Go to Utilities → 📸 Snapshots |
| **Read narrative** | Click "📖 Screenplay" view |
| **Test as player** | Click "👁️ Preview" view |
| **See flow** | Click "Graph View" |

---

## Tips for Testers

1. **Save Often** - Use "💾 Save Project" regularly
2. **Create Snapshots** - Before major changes
3. **Use Validation** - Catches errors early
4. **Try All Views** - Each offers different perspective
5. **Test Edge Cases** - That's where bugs hide
6. **Check Console** - Browser console shows technical errors
7. **Be Thorough** - Test every feature, every view
8. **Document Everything** - Good bug reports help fixes
9. **Test Workflows** - Not just individual features
10. **Have Fun** - It's a powerful tool, explore it!

---

## Support & Feedback

For bugs, feature requests, or questions:
- GitHub: [Repository URL]
- Email: [Your email]
- Documentation: This manual

**Thank you for testing!** Your feedback helps make the Narrative Editor better for everyone.

---

*End of User Manual*
