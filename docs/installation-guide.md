# 🔥 Installation Guide - Burner Expert Mode

## Prerequisites

- **Roo Code** installed and running
- Access to custom modes configuration

## Installation Methods

### Method 1: Global Installation (Recommended)

Global installation makes the mode available across all projects and workspaces.

#### Step 1: Locate Configuration File
Navigate to your global custom modes file:
```bash
~/Library/Application Support/Code/User/roo-code/settings/custom_modes.yaml
```

#### Step 2: Add Mode Configuration
1. Open the `custom_modes.yaml` file in a text editor
2. Add the content from [`modes/burner-expert.yaml`](../modes/burner-expert.yaml) to the `customModes:` array
3. Save the file

#### Step 3: Restart Roo Code
Close and reopen Roo Code to load the new configuration.

#### Step 4: Verify Installation
The mode should appear as "🔥 Burner Expert" in the mode selection menu.

### Method 2: Project-Specific Installation

This method installs the mode only for a specific project/workspace.

#### Step 1: Create Local Configuration
1. Navigate to your project root directory
2. Create or edit `.roomodes` file
3. Add the mode configuration from [`modes/burner-expert.yaml`](../modes/burner-expert.yaml)

#### Step 2: Restart Roo Code
The mode will be available only within this project workspace.

## Verification

Test the installation by:

1. **Mode Selection**: Look for "🔥 Burner Expert" in the mode menu
2. **Test Query**: Ask: "Create a basic packing list for Burning Man"
3. **Feature Check**: Verify it can access MCP tools for web scraping

## Troubleshooting

### Mode Not Appearing
- **Check YAML syntax**: Ensure proper indentation and formatting
- **Restart required**: Always restart Roo Code after configuration changes
- **File location**: Verify you're editing the correct configuration file

### Mode Loads But Doesn't Function
- **Tool permissions**: Ensure `groups: [read, edit, mcp]` is included
- **Configuration validation**: Check that all required fields are present

### YAML Syntax Errors
- **Indentation**: Use 2 spaces for each indentation level
- **Quotes**: Use quotes around values containing special characters
- **Arrays**: Ensure proper array formatting for `source_urls`

## Configuration Validation

Your `custom_modes.yaml` should include:

```yaml
customModes:
  # ... other modes ...
  - slug: burner-expert
    name: "🔥 Burner Expert"
    description: Burning Man preparation and participation guide
    # ... rest of configuration
```

## Advanced Configuration

### Adding Custom Source URLs
Modify the `source_urls` array to include additional resources:

```yaml
source_urls:
  - https://burningman.org/event/preparation/
  - https://your-custom-resource.com/guide
  # Add more URLs as needed
```

### Customizing Instructions
Modify `customInstructions` to emphasize specific aspects:

```yaml
customInstructions: >-
  Always prioritize safety and Leave No Trace principles.
  Add your specific emphasis here...
```

## Next Steps

After successful installation:

1. **Read Usage Examples**: Check [`docs/usage-examples.md`](./usage-examples.md)
2. **Enhance with Context**: See [`docs/context-enhancement-guide.md`](./context-enhancement-guide.md)
3. **Configure Source URLs**: Review [`docs/source-urls-guide.md`](./source-urls-guide.md)

## Getting Help

If you encounter issues:

1. **Check Documentation**: Review all files in the `docs/` directory
2. **Validate Configuration**: Use a YAML validator for syntax checking
3. **Community Support**: Visit [ePlaya forums](https://eplaya.burningman.org/) for Burning Man questions
4. **Technical Issues**: Create an issue in this repository

Welcome to the playa! 🏜️✨
