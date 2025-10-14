# Q-Vibes Memory Banking

![Q-Vibes Logo](logo_square.png)

A lightweight context preservation framework for AI-assisted rapid prototyping and vibe-coding sessions. Tested with Amazon Q Developer CLI (`q chat` command).

The Q-Vibes framework helps maintain context across AI assistant sessions through 5 lightweight files, enabling quick prototype development without losing momentum between sessions.

## Prerequisites

- Have an idea to explore
- Understanding of your collaboration style (git workflow, documentation preferences, etc.) and tech stack
- Access to the template files in `/templates/` folder

## File Templates Overview

The Q-Vibes framework uses 5 essential files, each with a specific purpose and ownership:

### [`q-vibes-memory-banking.md`](q-vibes-memory-banking.md) - The AI Contract
**👤 User copies** | **The most important file** - this contains the complete framework instructions that tell the AI **HOW TO WORK WITH MEMORY BANKING**. This file must be copied into every `.amazonq/vibes/` folder and serves as the AI's operating manual. It defines the file structure, update processes, and memory preservation workflow.

### [`idea.md`](templates/idea.md) - Project Concept  
**🤖 AI creates from user description** | Captures the core concept and success criteria for your prototype. This is your north star - created once and rarely changes. The AI creates this from your initial description, but may ask clarifying questions to complete all sections using the template structure.

### [`vibe.md`](templates/vibe.md) - Collaboration Style
**👤 User creates & maintains** | Defines how you want to collaborate with the AI assistant. Specifies your interaction style, tech stack preferences, decision-making approach, git workflow, security practices, documentation requirements, and speed vs quality trade-offs.

### [`state.md`](templates/state.md) - Technical Snapshot
**🤖 AI creates & maintains** | The living technical snapshot of your prototype. Updated frequently by the AI as you build. Contains current stack, architecture overview, file structure, what's working/broken, immediate next steps, and current focus.

### [`decisions.md`](templates/decisions.md) - Decision Log
**🤖 AI creates & maintains** | Log of key choices made during development. Prevents re-discussing the same decisions. The AI creates and maintains this file as architectural and technical decisions are made, following the template structure.

## How the System Works

This makes the framework complete and self-contained. The AI gets both:
- **How to work** (from the framework instructions in `q-vibes-memory-banking.md`)
- **What to work on** (from the 4 context files: `idea.md`, `vibe.md`, `state.md`, `decisions.md`)

## Optional Rule File (Bonus Tip)

The Q CLI has built-in support for rule files that can automatically activate behaviors without explicit prompts. The `fast-prototyping.rule.md` file in the `/rules/` folder is a **bonus feature** that leverages this Q CLI capability.

**Important**: The rule file is **not part of the core framework** - it's simply a convenience feature that:
- Uses Q CLI's native rule system to auto-detect the framework
- Eliminates the need for explicit prompts when starting/resuming sessions
- Provides a seamless experience for users who want the framework always active

**How it works**:
- Place `rules/fast-prototyping.rule.md` in your project's `.amazonq/rules/` folder
- Q CLI automatically reads and applies the rule when starting sessions
- The AI will automatically look for and use the Q-Vibes framework files

**Without the rule file**: You simply use the manual prompts provided in the [Example Prompts](#example-prompts) section - the framework works exactly the same way.

## Quick Project Setup

You have two options for setting up Q-Vibes Memory Banking:

### Option 1: Automatic Setup (Recommended)
Use the optional rule file for automatic framework activation:

```bash
# Create Q-Vibes memory banking structure
mkdir -p .amazonq/vibes
cd .amazonq/vibes

# Copy the AI instructions (tells AI how to use the framework)
cp ../../q-vibes-memory-banking.md .

# Copy ALL template files (AI uses these as references for consistent formatting)
cp ../../templates/*.md ./

# Copy the optional rule file for automatic activation
mkdir -p ../rules
cp ../../rules/fast-prototyping.rule.md ../rules/

# Customize your collaboration template
# Edit vibe.md to match your preferences

# Return to project root
cd ../..

# Start session - AI will automatically detect and use the framework
q chat 
```

### Option 2: Manual Setup (Prompt-Based)
Use explicit prompts without the rule file:

```bash
# Create Q-Vibes memory banking structure
mkdir -p .amazonq/vibes
cd .amazonq/vibes

# Copy the AI instructions (tells AI how to use the framework)
cp ../../q-vibes-memory-banking.md .

# Copy ALL template files (AI uses these as references for consistent formatting)
cp ../../templates/*.md ./

# Customize your collaboration template
# Edit vibe.md to match your preferences

# Return to project root
cd ../..

# Start a new prototype session using explicit prompts (see example prompts below)
q chat 
```

**That's it!** The AI agent will automatically handle:
- Using `idea.md` template when creating from your prototype description
- Using `state.md` template when creating and maintaining technical snapshot
- Using `decisions.md` template when logging decisions
- Following your `vibe.md` preferences for git workflow, security practices, and collaboration style

**With Option 1 (Automatic):** The AI detects the framework automatically via the rule file and starts using it immediately.

**With Option 2 (Manual):** You use the example prompts below to explicitly tell the AI to use the framework.

Just describe your prototype idea to the AI, and it will follow the template formats while using your `vibe.md` preferences.

## Real Example: Builder-Tracker

See the complete working example in [`/examples/builder-tracker/`](examples/builder-tracker/) which demonstrates:
- **Starting prompt** used to initialize the prototype (using the [example prompt below](#starting-a-new-prototype-session))
- **Resume prompt** used to continue work across sessions (using the [example prompt below](#resuming-an-existing-project))
- **Compiled templates** showing how the framework files look when filled out
- **Complete vibe.md** with git workflow, documentation requirements, and collaboration preferences

This example shows the Q-Vibes Memory Banking framework applied to a real prototype project using the exact prompts provided in this README.

## Step-by-Step Usage Guide

### 1. Starting a New Prototype Session

**Option 1 (Automatic with Rule File):**
1. **AI automatically detects the framework** via `fast-prototyping.rule.md` in `.amazonq/` folder
2. **AI reads framework instructions** and template files automatically
3. **Describe your prototype idea** to the AI assistant (can be brief - just the core concept)
4. **AI creates `idea.md`** using the template structure
5. **AI follows your `vibe.md` preferences** and starts coding

**Option 2 (Manual with Prompts):**
1. **Use the starting prompt** (see [Example Prompts](#example-prompts) below)
2. **AI reads the framework instructions** (`q-vibes-memory-banking.md`) to understand how to use the framework
3. **Describe your prototype idea** to the AI assistant (can be brief - just the core concept)
4. **AI creates `idea.md`** using the template structure:
   - If your description covers all template sections → AI creates complete `idea.md`
   - If information is missing → AI asks clarifying questions to fill gaps
   - You review and approve the final `idea.md` before proceeding
5. **AI follows your `vibe.md` preferences** for collaboration style, workflow, and project setup
6. **Start coding** - AI maintains `state.md` automatically

### 2. Collaboration Style Configuration
The Q-Vibes framework is **highly configurable** through your `vibe.md` file. You can specify:
- **Git workflow preferences** (branching, commits, merging)
- **Documentation requirements** (what docs to create, when)
- **Security practices** (how to handle secrets, environment variables)
- **Decision-making style** (what to ask about vs. assume)
- **Process management** (how to run long-running processes)

The template in `/templates/vibe.md` includes an example git workflow configuration. Customize it to match your preferred working style.

### 3. Resuming Work (Key Benefit!)

**Option 1 (Automatic with Rule File):**
1. **AI automatically detects the framework** via `fast-prototyping.rule.md` in `.amazonq/` folder
2. **AI reads all context files** (`q-vibes-memory-banking.md`, `idea.md`, `vibe.md`, `state.md`, `decisions.md`) automatically
3. **AI confirms context**: "I see we're building [X], currently working on [Y], next step is [Z]"
4. **AI continues work** following your vibe.md preferences
5. **No re-explaining needed** - context is preserved

**Option 2 (Manual with Prompts):**
1. **Use the resuming prompt** (see [Example Prompts](#example-prompts) below)
2. **AI reads the framework instructions** (`q-vibes-memory-banking.md`) to understand how to work
3. **AI reads all 4 context files** (`idea.md`, `vibe.md`, `state.md`, `decisions.md`) - takes ~30 seconds
4. **AI confirms context**: "I see we're building [X], currently working on [Y], next step is [Z]"
5. **AI continues work** following your vibe.md preferences
6. **No re-explaining needed** - context is preserved

### 4. Ending a Session
1. **AI updates `state.md`** with current progress
2. **AI logs any new decisions** made during the session
3. **AI follows end-of-session preferences** from your vibe.md (e.g., git commits, cleanup)
4. **Ready for next session** - no context loss

## Example Prompts

**Note:** These prompts are only needed if you're using Option 2 (Manual Setup). With Option 1 (Automatic Setup), the AI detects and uses the framework automatically via the rule file.

### Starting a New Prototype Session
```
Hi! I want to start a new prototype using Q-Vibes Memory Banking. 

Please read the framework instructions in .amazonq/vibes/q-vibes-memory-banking.md first to understand how to work with this system.

My prototype idea: [Describe your idea here - can be brief, just the core concept]

Example: "I want to build a simple web app that helps developers track their daily coding habits. Users can log what they worked on, how long they spent, and rate their productivity. The goal is to identify patterns and improve focus."
```

### Resuming an Existing Project
```
Hi! I'm resuming work on my prototype using Q-Vibes Memory Banking.

Please read the framework instructions in .amazonq/vibes/q-vibes-memory-banking.md first, then read all the context files in .amazonq/vibes/ folder to understand the current state.

Once you've reviewed everything, please confirm what we're building, where we left off, and what the next steps should be.
```

## Tips for Effective Q-Vibes Sessions

### Customizing Your `vibe.md`
- **Be comprehensive** - specify every aspect of collaboration (tech stack, git workflow, documentation requirements, etc.)
- **Be specific** about your preferences to avoid back-and-forth questions
- **Define your collaboration style** clearly for consistent AI behavior
- **Include all working preferences** - decision-making style, process management, security practices

### Managing File Sizes
- Keep files under the size limits (see main documentation)
- **Focus on actionable information** only
- **Use bullet points** instead of long paragraphs
- **Remove outdated information** regularly

### Git Workflow Tips
- **Feature branches** keep main clean and working
- **Regular commits** help track progress
- **Descriptive commit messages** aid in context rebuilding
- **Ask before merging** maintains code quality

## Troubleshooting

### "AI doesn't understand my context"
- Check if all 4 files exist in `.amazonq/vibes/` folder
- Ensure `idea.md` clearly describes the core concept
- Update `state.md` if current status is unclear

### "Setup commands don't work"
- Verify template files exist in `/templates/` folder
- Check file paths in copy commands
- Ensure you're in the correct directory

### "Git workflow is confusing"
- Stick to the feature branch pattern
- Let AI handle branch creation and management
- Always ask AI before merging to main

### "Files are getting too long"
- Review size limits in main documentation
- Focus on essential information only
- Archive old decisions that are no longer relevant

## Advanced Usage

### Multiple Prototypes
- Each prototype gets its own `.amazonq/vibes/` folder
- Reuse the same `vibe.md` template across projects
- Maintain separate git repositories for each prototype

### Collaboration with Others
- Share the entire project folder including `.amazonq/vibes/`
- Others can read the context files to understand the project

### Evolution to Production
- Use the prototype as a proof of concept
- Decision log helps avoid repeating the same architectural discussions
