# AI Coding Standards

A personal collection of AI prompts, operating modes, and rules designed to streamline development and ensure high-quality code through AI collaboration.

## 📁 Project Structure

- `commands/`: Markdown-based command definitions (e.g., `spec-assistant.md`) for use with slash commands.
- `skills/`: Agent Skills that can be installed in Cursor, VS Code (GitHub Copilot), or Claude Desktop for automatic activation.
  - `spec-assistant/`: A collaborative spec-building assistant that guides spec-driven development.

## 🚀 Installation

### For Cursor IDE

**Option 1: Install from GitHub (Recommended - UI Method)**

The easiest way to install this skill is through Cursor's built-in GitHub integration:

1. Open **Cursor Settings** (`Cmd+Shift+J` on Mac, `Ctrl+Shift+J` on Windows/Linux)
2. Navigate to **Rules**
3. In the **Project Rules** section, click **Add Rule**
4. Select **Remote Rule (Github)**
5. Enter the repository URL: `https://github.com/harshilparmar/ai-coding-standards`
6. Cursor will automatically discover and load the skill from the `skills/spec-assistant/` directory

**Note:** Agent Skills are currently only available in the **Nightly** release channel. To switch:
- Open Cursor Settings (`Cmd+Shift+J` / `Ctrl+Shift+J`)
- Select **Beta**
- Set your update channel to **Nightly**
- Restart Cursor after the update

For more details, see the [official Cursor documentation on installing skills from GitHub](https://cursor.com/docs/context/skills#installing-skills-from-github).

**Option 2: Clone the entire repository**
```bash
# Clone the repository
git clone https://github.com/harshilparmar/ai-coding-standards.git

# Copy the skill to Cursor's skills directory
cp -r ai-coding-standards/skills/spec-assistant ~/.cursor/skills/
```

**Option 3: Clone just the skill directory**
```bash
# Navigate to Cursor skills directory
mkdir -p ~/.cursor/skills
cd ~/.cursor/skills

# Clone just the skill
git clone https://github.com/harshilparmar/ai-coding-standards.git temp-repo
cp -r temp-repo/skills/spec-assistant .
rm -rf temp-repo
```

**Option 4: Download and extract manually**
1. Download this repository as a ZIP file
2. Extract the `skills/spec-assistant` folder
3. Copy it to `~/.cursor/skills/spec-assistant`

After installation (Options 2-4), restart Cursor. The skill will be automatically discovered and available.

**Viewing installed skills:**
- Open **Cursor Settings** → **Rules**
- Skills appear in the **Agent Decides** section

### For VS Code (GitHub Copilot)

**Note:** Agent Skills support in VS Code is currently in preview. Enable the `chat.useAgentSkills` setting to use Agent Skills.

**Option 1: Install as a project skill (Recommended)**

Install the skill in your workspace so it's available for all team members:

```bash
# Clone the repository
git clone https://github.com/harshilparmar/ai-coding-standards.git

# Copy the skill to your project's .github/skills directory
mkdir -p .github/skills
cp -r ai-coding-standards/skills/spec-assistant .github/skills/
```

**Option 2: Install as a personal skill**

Install the skill in your user profile for use across all projects:

```bash
# Clone the repository
git clone https://github.com/harshilparmar/ai-coding-standards.git

# Copy the skill to your personal skills directory
mkdir -p ~/.copilot/skills
cp -r ai-coding-standards/skills/spec-assistant ~/.copilot/skills/
```

**Option 3: Clone directly to skills directory**

```bash
# For project-level installation
mkdir -p .github/skills
cd .github/skills
git clone https://github.com/harshilparmar/ai-coding-standards.git temp-repo
cp -r temp-repo/skills/spec-assistant .
rm -rf temp-repo

# Or for user-level installation
mkdir -p ~/.copilot/skills
cd ~/.copilot/skills
git clone https://github.com/harshilparmar/ai-coding-standards.git temp-repo
cp -r temp-repo/skills/spec-assistant .
rm -rf temp-repo
```

**Enable Agent Skills in VS Code:**

1. Open VS Code Settings (`Cmd+,` on Mac, `Ctrl+,` on Windows/Linux)
2. Search for `chat.useAgentSkills`
3. Enable the setting: **"Chat: Use Agent Skills"**
4. Restart VS Code

**Legacy compatibility:** VS Code also supports skills in `.claude/skills/` (project-level) or `~/.claude/skills/` (user-level) for backward compatibility.

For more details, see the [official VS Code documentation on Agent Skills](https://code.visualstudio.com/docs/copilot/customization/agent-skills#_create-a-skill).

### For Claude Desktop

1. **Download the skill as a ZIP file:**
   ```bash
   # Clone the repository
   git clone https://github.com/harshilparmar/ai-coding-standards.git
   cd ai-coding-standards/skills
   
   # Create a ZIP file of the skill
   zip -r spec-assistant.zip spec-assistant/
   ```

2. **Upload to Claude Desktop:**
   - Open Claude Desktop
   - Go to **Settings** → **Capabilities**
   - In the **Skills** section, click **"Upload skill"**
   - Select the `spec-assistant.zip` file you created

### For Claude Code (CLI)

```bash
# Clone the repository
git clone https://github.com/harshilparmar/ai-coding-standards.git

# Install the skill
/plugin add /path/to/ai-coding-standards/skills/spec-assistant
```

Or install from a directory:
```bash
cd ~/.claude/skills
git clone https://github.com/harshilparmar/ai-coding-standards.git temp-repo
cp -r temp-repo/skills/spec-assistant .
rm -rf temp-repo
```

### Using Commands (Alternative)

If you prefer using slash commands instead of skills:

```bash
# For Cursor
cp commands/spec-assistant.md ~/.cursor/commands/

# For Claude Code
cp commands/spec-assistant.md ~/.claude/commands/
```

Then use: `/spec-assistant` in your IDE.

## 📖 Usage

Once installed, the `spec-assistant` skill activates automatically when you mention spec-related keywords like:
- "Help me spec out a new feature"
- "I need to build a specification"
- "Let's gather requirements"

See [`skills/spec-assistant/QUICK_START.md`](skills/spec-assistant/QUICK_START.md) for detailed usage instructions.

