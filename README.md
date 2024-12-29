# Introduction
these files are a companion to the "Structured Ambition Framework: How to Plan, Reflect, and Achieve with Obsidian" blog post.

the framework is designed to help the user in creating visions for their year and provide tools to give life to these visions.

more information can be found in the blog post here: 
# Components 

## Templates
the templates are designed to be used with the Templater plug-in as well as Tasks plug-in and without them they would not be functioning as intended to. 
# How To Use
## 1. Install Obsidian

1. **Download Obsidian**: Visit the [Obsidian website](https://obsidian.md/download) and download the installer compatible with your operating system.

2. **Install the Application**:
   - **Windows**: Run the downloaded `.exe` file and follow the installation prompts.
   - **macOS**: Open the `.dmg` file and drag Obsidian to your Applications folder.
   - **Linux**: Download the AppImage, make it executable, and run it.

3. **Create a Vault**: Launch Obsidian and create a new vault, which serves as the repository for your notes.

## 2. Install Plugins

Obsidian's functionality can be extended with both core and community plugins.

### General

1. **Enable Community Plugins**:
   - Open **Settings** > **Community Plugins**.
   - Toggle **Safe Mode** off to enable community plugins.

### Tasks

1. **Install the Tasks Plugin**:
   - In **Community Plugins**, search for "Tasks" and click **Install**.
   - After installation, click **Enable**.
   - The Tasks plugin allows you to create, query, and manage tasks within your notes.

### Templater

1. **Install the Templater Plugin**:
   - In **Community Plugins**, search for "Templater" and click **Install**.
   - After installation, click **Enable**.
   - Templater enhances Obsidian's templating capabilities, allowing for advanced scripting and dynamic content.

### Daily Notes

1. **Enable the Daily Notes Core Plugin**:
   - Open **Settings** > **Core Plugins**.
   - Find **Daily Notes** and toggle it on.

## 3. Settings

### Templates

For the **Daily Note Template**:

- **Periodic Notes Path**:  
  Set the `periodNotesBasePath` as the base folder for storing all periodic notes (e.g., daily, weekly, monthly).
  
- **Journal Notes Path**:  
  Set the `journalBasePath` as the folder where all journal entries will be saved.

- **Quick Capture Path**:  
  Define the path where quick capture notes will be stored for easy access.

For the **Quick Capture Template**:

- **Quick Caputre Notes Path**:  
  Set the `baseFolder` as the base folder for storing all quick capture notes
### Templater

1. After installing the **Templater** plugin, open the plugin settings.  
2. Under the **Template Folder Location**, configure each respective template for the following periodic notes:  
   - Daily Notes  
   - Weekly Notes  
   - Monthly Notes  
   - Quarterly Notes
   - Yearly Notes
   - Quick Capture Note

3. Ensure that each template is linked to its designated path set in the Templates section above.

### Daily Notes

1. Set the **Date Format** for the daily notes to the following structure:  
   `YYYY/[Q]Q/MM-MMMM/WW/YYYY-MM-DD-dddd`  
   - Example Output: `2024/Q1/01-January/01/2024-01-01-Monday`

2. Configure the **New File Location**:  
   - Match this location to the **Periodic Notes Path** specified in the **Daily Note Template**.

3. Enable the following option:  
   - **"Open daily note on startup"** to automatically open the daily note

