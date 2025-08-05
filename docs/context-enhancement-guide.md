# 🔥 Context Enhancement Guide - Burner Expert Mode

## Overview

This guide explains how to enhance your Burner Expert mode with additional context, documents, and specialized knowledge sources.

## 🚀 **Immediate Enhancement Options (Available Now)**

### 1. **MCP Tool Integration** 
The mode has full `mcp` tool access for real-time information gathering:

#### Available Capabilities:
- **Web Scraping**: Fetch current content from burningman.org, weather sites, survival guides
- **Document Analysis**: Upload PDFs, Word docs, spreadsheets directly to conversations

#### Example Usage:
```
"Scrape the latest weather data for Black Rock Desert"
"Get current ticket information from the official site" 
"Search for updated Leave No Trace guidelines"
"Analyze this survival guide PDF I'm uploading"
```

### 2. **Dynamic Information Requests**
The mode can actively seek information during conversations:

```
"Let me fetch the latest weather forecast for August"
"I'll search for current art installation guidelines"
"Let me get the most recent safety protocols"
```

### 3. **Document Upload Integration**
Upload relevant documents directly to conversations:
- Official Burning Man survival guides (PDFs)
- Personal preparation checklists (Excel/Sheets)
- Weather reports and historical data
- Medical protocols and emergency procedures
- Community-shared resources and guides

## 📚 **Enhanced Configuration Options (Require Restart)**

### 4. **Document Knowledge Base Setup**

#### Create Organized Storage:
```bash
~/Documents/BurningManKnowledgeBase/
├── survival/
│   ├── weather-data.pdf
│   ├── desert-safety.pdf
│   └── medical-protocols.pdf
├── logistics/
│   ├── packing-lists.xlsx
│   ├── transportation-guide.pdf
│   └── arrival-timing.pdf
├── culture/
│   ├── 10-principles-guide.pdf
│   ├── gifting-ideas.pdf
│   └── participation-guide.pdf
└── resources/
    ├── official-guides/
    ├── community-wisdom/
    └── emergency-protocols/
```

#### Reference in Mode Configuration:
```yaml
customInstructions: >-
  Access the comprehensive knowledge base at ~/Documents/BurningManKnowledgeBase/ 
  for detailed survival guides, logistics planning, cultural resources, and 
  emergency protocols. Always prioritize safety and Leave No Trace principles...
```

### 5. **Enhanced System Prompt with Specific Sources**

Modify the `systemPrompt` section to include references:

```yaml
systemPrompt: >-
  You are a comprehensive Burning Man expert with access to:
  - Official Burning Man Survival Guide (burningman.org)
  - Historical weather data for Black Rock Desert (2010-2024)
  - Playa Safety Guidelines and Emergency Protocols
  - Black Rock City Infrastructure and Navigation Maps  
  - Community-curated preparation resources from ePlaya forums
  - Desert survival manuals and medical emergency procedures
  - Leave No Trace desert conservation principles and practices
  - Art installation safety guidelines and technical requirements
  - Theme camp organization and volunteer management resources
  
  You help people prepare for and participate meaningfully in Burning Man while 
  prioritizing safety, environmental responsibility, and community contribution.
```

### 6. **Additional Source URLs**

Expand the `source_urls` array with specialized resources:

```yaml
source_urls:
  # Core Official Resources
  - https://burningman.org/event/preparation/
  - https://burningman.org/event/survive/
  - https://survival.burningman.org/
  
  # Weather & Environment
  - https://weather.gov/rev/BurningMan
  - https://burningman.org/event/black-rock-city-guide/infrastructure/
  
  # Safety & Medical
  - https://burningman.org/event/health-safety/
  - https://burningman.org/event/health-safety/medical-services/
  
  # Community & Culture
  - https://eplaya.burningman.org/
  - https://regionals.burningman.org/
  - https://journal.burningman.org/
  
  # Art & Participation
  - https://burningman.org/event/art-performance/installations/
  - https://burningman.org/culture/history/
  
  # Environmental
  - https://burningman.org/culture/leave-no-trace/
  - https://lnt.org/learn/7-principles/
```

## 🔧 **Workspace-Specific Resources**

### Project-Level Enhancement
Create `.roomodes` files in specific projects:

```yaml
# In your project's .roomodes file
customModes:
  - slug: burner-expert
    extends: global  # Inherit from global mode
    additionalResources:
      - path: "./burning-man-docs/"
      - url: "https://eplaya.burningman.org"
      - documents: ["survival-guide.pdf", "packing-list.xlsx"]
    customInstructions: >-
      In addition to global knowledge, reference the project-specific 
      documents in ./burning-man-docs/ for this preparation cycle.
```

### Theme Camp Specific Configuration
For theme camp planning projects:

```yaml
customInstructions: >-
  Focus on theme camp logistics, volunteer coordination, and interactive 
  experience design. Reference camp-specific planning documents and 
  collaborate with camp leadership on safety protocols and resource allocation.
```

## 📊 **Resource Categories**

### Essential Documents to Add:
1. **Survival & Safety**
   - Official Burning Man Survival Guide
   - Desert first aid protocols
   - Weather emergency procedures
   - Evacuation and emergency contact plans

2. **Logistics & Planning**
   - Comprehensive packing checklists
   - Transportation and arrival guides
   - Power system planning resources
   - Food and water calculation tools

3. **Cultural Resources**
   - 10 Principles detailed explanations
   - Gifting culture participation guides
   - Art installation guidelines
   - Community participation frameworks

4. **Technical Resources**
   - Shade structure engineering guides
   - Power system specifications
   - Bike modification instructions
   - Camp infrastructure blueprints

## 🎯 **Enhancement Strategies**

### Progressive Enhancement:
1. **Week 1**: Start with basic MCP tool usage and document uploads
2. **Week 2**: Organize knowledge base folder structure
3. **Week 3**: Add specialized source URLs and references
4. **Week 4**: Create project-specific configurations for camps/groups

### Collaboration Enhancement:
- **Shared Resources**: Create shared Google Drive/Dropbox with camp members
- **Community Integration**: Connect with ePlaya forum threads and discussions
- **Expert Networks**: Engage with veteran burner communities and regional groups

## 🔍 **Testing Your Enhancements**

### Verification Questions:
```
"Access my personal packing checklist and suggest improvements"
"Compare official weather data with community reports"
"Analyze my camp's safety protocols against best practices"
"Search recent ePlaya discussions about [specific topic]"
```

### Enhancement Quality Checks:
- **Accuracy**: Information matches official sources
- **Currency**: Data is current and relevant
- **Safety Focus**: All advice prioritizes participant safety
- **Cultural Alignment**: Recommendations support 10 Principles

## 🚀 **Next Steps**

### Immediate Actions:
1. **Upload Key Documents**: Add 3-5 essential PDFs to current conversations
2. **Test MCP Tools**: Try web scraping current weather and ticket information
3. **Create Knowledge Folder**: Establish organized document storage

### Future Enhancements:
1. **Expand Source URLs**: Add weather, medical, and community resources
2. **Create Specialized Modes**: Consider camp-specific or role-specific variants
3. **Community Integration**: Connect with regional burning communities

## 📞 **Getting Help**

### Troubleshooting Enhancement Issues:
- **MCP Tools Not Working**: Check tool permissions in mode configuration
- **Documents Not Accessible**: Verify file paths and permissions
- **Source URLs Not Loading**: Test URL accessibility and update as needed

### Community Resources:
- **ePlaya Forums**: Community wisdom and real-time advice
- **Regional Groups**: Local burning communities and preparation groups
- **Official Resources**: Burning Man organization support and guidelines

The goal is to create a comprehensive, current, and culturally aligned knowledge system that supports safe, responsible, and meaningful participation in Burning Man.

Welcome home! 🏜️✨
