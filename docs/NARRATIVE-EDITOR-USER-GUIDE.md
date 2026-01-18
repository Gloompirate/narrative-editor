# Narrative Editor - User Guide

**Version 1.0**  
*A comprehensive tool for creating interactive forum-based narratives*

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [Interface Overview](#interface-overview)
3. [Creating Your Narrative](#creating-your-narrative)
4. [Views Explained](#views-explained)
5. [Advanced Features](#advanced-features)
6. [Managing Your Project](#managing-your-project)
7. [Tips & Best Practices](#tips--best-practices)

---

## Getting Started

### What is Narrative Editor?

Narrative Editor is a tool for creating interactive, choice-based narratives presented as forum discussions. You can create:
- **Characters** that post messages
- **Player choices** that affect the story
- **Branching narratives** based on flags and conditions
- **Timeline-based content** that unlocks on specific days

### Opening Your First Project

1. Open `narrative-editor.html` in a modern web browser (Chrome, Firefox, Edge)
2. You'll see an empty project with sample structure
3. Start creating by clicking **➕ Category** in the toolbar

### Basic Concepts

- **Categories**: Top-level groups (like forum sections)
- **Threads**: Discussion topics within categories
- **Posts**: Individual messages from characters
- **Flags**: Story variables that track choices
- **Days**: Timeline system for unlocking content

---

## Interface Overview

### Toolbar (Top)

**Content Creation:**
- **➕ Category** - Add a new forum category
- **➕ Thread** - Add a thread to selected category
- **➕ Post** - Add a post to selected thread
- **🗑️ Delete** - Remove selected item

**Editing:**
- **↶ Undo** - Undo last change (50 steps)
- **↷ Redo** - Redo undone change

**Project Management:**
- **📤 Export** - Export your project (JSON, Yarn, HTML, Markdown)
- **📥 Import JSON** - Import narrative data
- **💾 Save Project** - Save complete project file (.neproj)
- **📂 Load Project** - Restore from project file

**Tools:**
- **📊 Utilities** - Access validation, search, bulk operations
- **⌨️** - View keyboard shortcuts

**View Selector:**
- **🌲 Tree View** - Hierarchical editing
- **📊 Graph View** - Visual node connections
- **📖 Screenplay** - Linear reading format
- **👁️ Preview** - Test your narrative
- **📚 Lore** - Character and world reference
- **📄 JSON View** - Raw data editing

**Timeline:**
- **Current Day** - Set simulation day (affects preview)
- **Next TS** - Auto-incrementing timestamp value

---

## Creating Your Narrative

### Step 1: Create Structure

**Add a Category:**
1. Click **➕ Category**
2. Name it (e.g., "General Discussion")
3. Add subtitle (optional description)

**Add a Thread:**
1. Select your category in tree view
2. Click **➕ Thread**
3. Name your thread (e.g., "Welcome Thread")

**Add Posts:**
1. Select your thread
2. Click **➕ Post**
3. Fill in post details in right panel

### Step 2: Configure Posts

Each post has these fields:

**Basic Info:**
- **User Name** - Character posting this message
- **User Rank** - Character's title/role
- **Post Body** - The message content

**Post Types:**
- **Standard** - Regular post (blue)
- **Reply** - Response to another post (orange)
- **Alert** - System message (yellow)

**Advanced:**
- **Timestamp** - When post appears in timeline
- **Quote** - Reference another post
- **Set Flag** - Mark a story event when post appears

### Step 3: Add Player Choices

**Making Posts Interactive:**
1. Select a post in tree view
2. Scroll to **Player Response Options**
3. Click **Add Option**
4. Fill in:
   - **Option Text** - What the player chooses
   - **Set Flag** - Flag triggered by this choice
   - **Reply Body** - Response after choosing

**Example:**
```
Option Text: "I'll help you!"
Set Flag: agreed_to_help
Reply Body: "Thank you! Meet me tomorrow."
```

### Step 4: Add Conditions

**Locking Content:**

Posts and threads can be locked until:
- **Min Day** - Specific day number
- **Requires Flag** - Player made a choice

**Example Use Cases:**
- Day 5 content unlocks on Day 5
- "Secret Path" thread requires flag: found_key
- Post appears only after: talked_to_mayor

---

## Views Explained

### 🌲 Tree View (Default)

**Best for:** Organizing and editing content

**Features:**
- Hierarchical structure
- Right-click for quick actions
- Editor panel on right
- Drag to reorganize (manual)

**How to Use:**
1. Click any item to select
2. Edit in right panel
3. Use ➕ buttons to add content
4. Right-click for more options

### 📊 Graph View

**Best for:** Visualizing story flow

**Features:**
- Node-based visualization
- Auto-layout (horizontal/vertical)
- Click nodes to view details
- Shows connections between posts

**Controls:**
- **Zoom** - Mouse wheel
- **Pan** - Click and drag
- **Layout** - Toggle horizontal/vertical
- **Auto-center** - Focus on structure

**Right-click Actions:**
- Edit node
- Delete node
- View in tree

### 📖 Screenplay

**Best for:** Reading your narrative linearly

**Features:**
- Thread selector on left
- Posts displayed in order
- Inline editing (double-click posts)
- Search within threads

**How to Read:**
1. Select thread from list
2. Scroll through posts
3. View player choices inline

**Editing:**
- Double-click any post to edit
- Changes save automatically
- Search box filters posts

### 👁️ Preview

**Best for:** Testing your narrative

**Features:**
- Simulated forum interface
- Test player choices
- See conditional content
- Adjust day counter

**Controls:**
- **Day Counter** - Change simulated day
- **Flag Badges** - Shows active flags
- **Choose Options** - Test choices
- **✏️ Edit** - Jump to post in editor

**Testing Flow:**
1. Set Day to 0
2. Read through available content
3. Make choices (sets flags)
4. Advance days to unlock more
5. Click Edit to fix issues

### 📚 Lore

**Best for:** Tracking characters and world events

**Three Tabs:**

**📅 Timeline** (Default):
- Combined view of all characters and events
- Sorted by day
- Shows character introductions
- Shows world events
- Color-coded (blue=character, yellow=event)

**👥 Characters**:
- All characters from User Library
- Shows: name, rank, appearance day, biography
- Read-only (edit in Utilities)
- Sort by timeline or name

**🌍 World Events**:
- Create story events
- Set when they occur (day)
- Write descriptions (Markdown supported)
- Track plot points

**Creating World Events:**
1. Click **🌍 World Events** tab
2. Click **➕ Add Event**
3. Set title and day
4. Write description in Markdown
5. Event auto-saves

### 📄 JSON View

**Best for:** Advanced users, bulk editing

**Features:**
- Raw JSON data
- Direct editing
- Copy/paste structure
- Import external data

**Warning:** Malformed JSON will break your project

---

## Advanced Features

### Character Management (User Library)

**Access:** 📊 Utilities → 👥 User Library

**Features:**
- Create character profiles
- Set appearance day
- Add biography
- Mark active/inactive
- Quick-insert into posts

**Creating a Character:**
1. Go to Utilities → User Library
2. Click **Add User**
3. Fill in details:
   - Name
   - Rank/Title
   - Biography (Markdown)
   - Appearance Day
4. Save

**Using Characters:**
- When creating posts, select from dropdown
- Auto-fills name and rank
- Biography appears in Lore view

### Flags & Validation

**Flags** track player choices and story state.

**View All Flags:**
1. Go to 📊 Utilities
2. Click **Flags** tab
3. See all flags used in project

**Validation:**
1. Click **🔍 Run Validation**
2. Review issues:
   - Missing IDs
   - Invalid references
   - Unreachable content
   - Orphaned posts
3. Click item to jump to it

### Search & Replace

**Access:** 📊 Utilities → 🔎 Search & Replace

**Features:**
- Find text across entire project
- Replace text in bulk
- Scope filters (categories/threads/posts)
- Preview before applying

**Example Use:**
- Find: "King John"
- Replace: "Queen Jane"
- Scope: All posts
- Preview → Apply

### Bulk Operations

**Access:** 📊 Utilities → ✏️ Bulk Edit

**Operations:**
- Change avatars
- Update ranks
- Modify post types
- Set conditions

**How to Use:**
1. Select operation
2. Set "Find" criteria
3. Set "Replace" value
4. Preview changes
5. Apply

### Notes & Tags

**Per-Item Notes:**
1. Select any item
2. Open Notes tab
3. Write notes (supports Markdown)
4. Use for planning, reminders, etc.

**Tags:**
1. Select item
2. Add tags (e.g., "important", "review")
3. Filter/search by tags later

### Asset Management

**Upload Images:**
1. Go to Utilities → 🎨 Asset Browser
2. Click **Upload Asset**
3. Select image
4. Asset stored in project

**Using Assets:**
- Reference in post bodies
- Use in character profiles
- Include in world events

### Snapshots

**Version Control:**

**Create Snapshot:**
1. Go to Utilities → 📸 Snapshots
2. Click **Create Snapshot**
3. Name it (e.g., "Chapter 1 Complete")

**Restore Snapshot:**
1. Find snapshot in list
2. Click **Restore**
3. Project reverts to that version

**Use Cases:**
- Before major changes
- Chapter milestones
- Safe experimentation

---

## Managing Your Project

### Saving Your Work

**Auto-Save:**
- Project auto-saves to browser storage
- Happens every 30 seconds
- Persists between sessions

**Manual Save:**
- **💾 Save Project** - Downloads .neproj file
- Contains: data, notes, tags, characters, events
- Recommended before major changes

**Export Options:**
- **JSON** - Data only, for import/backup
- **Yarn Script** - For game engines (Unity, Godot)
- **HTML** - Standalone readable webpage
- **Markdown** - Plain text format

### Loading Projects

**From Project File:**
1. Click **📂 Load Project**
2. Select .neproj file
3. Confirms overwrite
4. Page reloads with project

**From JSON:**
1. Click **📥 Import JSON**
2. Select .json file
3. Merges or replaces data

**From Auto-Save:**
1. Click **⏮️ Load Auto-save**
2. Restores last auto-save
3. Use if browser crashed

### Organizing Content

**Best Practices:**

**Categories** - Broad sections:
- General Discussion
- Story Events
- Side Quests
- Character Interactions

**Threads** - Specific topics:
- "Welcome to Town"
- "The Mystery Begins"
- "Character: John's Story"

**Posts** - Individual messages:
- Keep focused on one idea
- Use types (standard/reply/alert)
- Add timestamps

**Smart IDs:**
- Enable in editor panel
- Auto-generates: p_category_thread_post
- Makes references easier

### Collaboration

**Sharing Projects:**
1. Save Project (💾)
2. Send .neproj file
3. Collaborator loads file

**Working Together:**
- One person edits at a time
- Use notes to communicate
- Save before passing file
- Use snapshots for versions

---

## Tips & Best Practices

### Writing Tips

**Character Consistency:**
- Create character in User Library first
- Set appearance day
- Write biography
- Use consistently throughout

**Pacing:**
- Spread content across days
- Don't overwhelm Day 0
- Use conditions to gate content
- Balance linear and branching paths

**Player Agency:**
- Give meaningful choices
- Choices should have consequences
- Use flags to track decisions
- Reference past choices in later posts

### Organization Tips

**Naming Conventions:**
- Categories: Clear, broad names
- Threads: Descriptive, specific
- Flags: verb_noun format (e.g., "met_mayor")
- IDs: Use smart IDs feature

**Timeline Planning:**
- Map out day-by-day unlocks
- Use Lore timeline to visualize
- Don't lock too much content
- Playtest different paths

**Quality Control:**
- Run validation regularly
- Check for typos (search feature)
- Test in Preview mode
- Create snapshots at milestones

### Performance Tips

**Large Projects:**
- Use categories to organize
- Split into multiple threads
- Archive old content
- Clean up unused flags

**Browser Storage:**
- Auto-save uses localStorage (limited)
- Save project file regularly
- Clear old snapshots
- Export backup copies

---

## Keyboard Shortcuts

**Editing:**
- `Ctrl+Z` / `Cmd+Z` - Undo
- `Ctrl+Y` / `Cmd+Y` - Redo
- `Ctrl+Shift+Z` / `Cmd+Shift+Z` - Redo (alternative)

**More shortcuts:** Click ⌨️ button in toolbar

---

## Common Workflows

### Starting a New Project

1. Create categories for your main sections
2. Add characters to User Library
3. Create first thread and welcome posts
4. Add player choices to first post
5. Create branching threads based on flags
6. Test in Preview mode
7. Save project file

### Adding a New Chapter

1. Create snapshot of current state
2. Add new category or thread
3. Set day conditions for new content
4. Create posts with references to flags
5. Test with different flag combinations
6. Run validation
7. Save

### Testing Your Narrative

1. Switch to 👁️ Preview
2. Start at Day 0
3. Read through content
4. Make choices (watch flags)
5. Advance days
6. Check conditional content appears
7. Use Edit buttons to fix issues
8. Return to start and test different paths

### Preparing for Release

1. Run validation - fix all issues
2. Test all player paths in Preview
3. Check Lore for completeness
4. Spell-check using Search
5. Create final snapshot
6. Save project file
7. Export to desired format(s)

---

## Troubleshooting

**Project won't load:**
- Check browser console for errors
- Try Load Auto-save
- Restore from snapshot
- Import backup JSON

**Content not appearing:**
- Check day conditions
- Check flag requirements
- Run validation
- Test in Preview mode

**Performance issues:**
- Reduce project size
- Clear old snapshots
- Use fewer undo steps
- Split into multiple files

**Lost changes:**
- Use Load Auto-save
- Restore from snapshot
- Check browser storage
- Always save project files

---

## Getting Help

**Resources:**
- This user guide
- Testing manual (for QA)
- Validation tool (built-in)
- Example projects

**Support:**
- Report bugs to development team
- Suggest features
- Share your projects
- Help improve documentation

---

## Glossary

**Category** - Top-level forum section grouping related threads

**Thread** - Discussion topic containing multiple posts

**Post** - Individual message from a character

**Flag** - Story variable tracking player choices/events

**Condition** - Requirement for content to be visible (day/flag)

**Smart ID** - Auto-generated unique identifier for posts

**Timestamp** - Sequential number for post ordering

**User Library** - Collection of reusable character profiles

**Lore** - Reference system for characters and world events

**Snapshot** - Saved version of your entire project

**Validation** - Tool that checks for errors in your project

**Preview Mode** - Simulated forum for testing your narrative

---

## Version History

**Version 1.0** - Initial Release
- Complete narrative editing suite
- Multiple view modes
- Character and world event tracking
- Export to multiple formats
- Comprehensive testing tools

---

*End of User Guide*
