# 🔗 Source URLs Configuration Guide

## Overview

This guide explains how to add, manage, and optimize source URLs for the Burner Expert mode to provide comprehensive reference materials.

## 📝 **Current Source URLs Configuration**

The mode includes these essential Burning Man resources:

```yaml
source_urls:
  - https://burningman.org/event/preparation/         # Official preparation guide
  - https://burningman.org/event/survive/             # Survival guide  
  - https://burningman.org/culture/philosophical-center/10-principles/ # 10 Principles
  - https://survival.burningman.org/                  # Dedicated survival site
  - https://eplaya.burningman.org/                    # Community forums
  - https://burningman.org/event/art-performance/     # Art & performance
  - https://burningman.org/culture/leave-no-trace/    # Environmental guidelines
  - https://burningman.org/event/participate/volunteer/ # Volunteer info
```

## 🔧 **Adding Additional Source URLs**

### Method 1: Direct Configuration Editing

Edit the `modes/burner-expert.yaml` file:

```yaml
source_urls:
  # Current URLs...
  
  # Weather & Environment
  - https://weather.gov/rev/BurningMan          # Official weather forecasts
  - https://mesonet.agron.iastate.edu/sites/locate.php?station=KBLU # Historical data
  
  # Safety & Medical
  - https://burningman.org/event/health-safety/         # Health & safety
  - https://burningman.org/event/health-safety/medical-services/ # Medical services
  
  # Community Resources
  - https://regionals.burningman.org/                   # Regional events
  - https://journal.burningman.org/                     # Official journal
  
  # Art & Culture
  - https://burningman.org/event/art-performance/installations/ # Art installations
  - https://burningman.org/culture/history/             # Historical context
```

### Method 2: Category-Based Organization

```yaml
source_urls:
  # Official Core Resources
  - https://burningman.org/event/preparation/
  - https://burningman.org/event/survive/
  - https://survival.burningman.org/
  
  # 10 Principles & Culture
  - https://burningman.org/culture/philosophical-center/10-principles/
  - https://burningman.org/culture/leave-no-trace/
  - https://burningman.org/culture/history/
  
  # Community & Participation
  - https://eplaya.burningman.org/
  - https://burningman.org/event/participate/volunteer/
  - https://regionals.burningman.org/
  
  # Art & Performance
  - https://burningman.org/event/art-performance/
  - https://burningman.org/event/art-performance/installations/
  
  # Logistics & Infrastructure
  - https://burningman.org/event/black-rock-city-guide/infrastructure/
  - https://burningman.org/event/health-safety/
```

## 🎯 **Recommended URL Categories**

### Essential Categories:

#### **1. Official Preparation**
- Preparation guides and checklists
- Survival information and safety protocols
- Transportation and logistics
- Ticket and registration information

#### **2. Cultural Resources**
- 10 Principles detailed explanations
- Historical context and evolution
- Community values and participation
- Regional event connections

#### **3. Safety & Medical**
- Health and safety guidelines
- Medical services and emergency procedures
- Weather preparedness
- Risk management protocols

#### **4. Environmental Responsibility**
- Leave No Trace principles
- Environmental impact guidelines
- Restoration and conservation
- Sustainable practices

#### **5. Community & Participation**
- Forums and community discussions
- Volunteer opportunities
- Theme camp resources
- Regional burning communities

## 📋 **URL Selection Best Practices**

### Choose URLs that are:

#### **Authoritative**
- Official Burning Man Organization sources
- Trusted community resources with established reputations
- Government weather and safety agencies
- Recognized safety and medical organizations

#### **Current & Maintained**
- Regularly updated content
- Active community engagement
- Recent publication dates
- Responsive to current event changes

#### **Comprehensive**
- Cover different aspects of preparation and participation
- Address diverse participant needs
- Include both beginner and advanced resources
- Support multiple learning styles

#### **Accessible**
- Publicly available content
- No login or subscription requirements
- Mobile-friendly and responsive design
- Clear navigation and organization

## 🔄 **Managing URLs Over Time**

### Regular Maintenance Tasks:

#### **Monthly Review**
- Check all URLs for accessibility
- Verify content currency and relevance
- Remove broken or outdated links
- Add new resources as they become available

#### **Seasonal Updates**
- Pre-event: Add current year specific information
- During event: Include real-time resources if applicable
- Post-event: Update with lessons learned and improvements
- Off-season: Focus on regional events and community building

#### **Community Feedback Integration**
- Monitor community discussions for new valuable resources
- Test user-recommended URLs for quality and relevance
- Incorporate feedback from mode users
- Maintain alignment with community values

### Version Control Strategy:

```yaml
# Document changes with comments
source_urls:
  - https://burningman.org/event/preparation/  # Added 2024-01-15
  - https://new-resource.com/guide             # Added 2024-03-20 - Community recommended
  # Removed https://outdated-site.com/        # Removed 2024-02-10 - Site deprecated
```

## 🚀 **Advanced URL Configuration**

### Conditional URL Loading
Consider different URL sets for different contexts:

```yaml
# Base configuration
source_urls:
  - https://burningman.org/event/preparation/

# Regional event variant might include:
# - https://regionals.burningman.org/events/regional-event-name/

# Theme camp variant might include:
# - https://burningman.org/event/participate/theme-camps/
```

### URL Categorization with Comments
```yaml
source_urls:
  # === CORE PREPARATION ===
  - https://burningman.org/event/preparation/
  - https://burningman.org/event/survive/
  
  # === COMMUNITY & CULTURE ===
  - https://eplaya.burningman.org/
  - https://burningman.org/culture/philosophical-center/10-principles/
  
  # === SAFETY & MEDICAL ===
  - https://burningman.org/event/health-safety/
  - https://survival.burningman.org/
```

## 🔍 **Quality Assurance**

### URL Validation Checklist:
- [ ] URL is accessible and loads quickly
- [ ] Content is relevant to Burning Man preparation/participation
- [ ] Information is current and accurate
- [ ] Source is authoritative and trusted
- [ ] Content aligns with 10 Principles and community values
- [ ] No commercial bias or inappropriate advertising
- [ ] Mobile-friendly and accessible design

### Testing New URLs:
```
"Check the latest updates from [new URL]"
"Compare information from [URL A] and [URL B]"
"Summarize the key points from [recently added URL]"
```

## 📊 **URL Performance Monitoring**

### Metrics to Track:
- **Accessibility**: Percentage of URLs consistently reachable
- **Currency**: Average age of content across sources
- **Relevance**: User feedback on URL usefulness
- **Coverage**: Comprehensiveness across preparation topics

### Community Feedback Collection:
- Regular surveys about resource quality
- Issue tracking for broken or outdated links
- Suggestions for new high-quality resources
- Usage analytics if available

## 🔧 **Implementation Steps**

1. **Current State Review**: Audit existing URLs for quality and coverage
2. **Gap Analysis**: Identify missing topic areas or resource types
3. **Research Phase**: Find high-quality resources for identified gaps
4. **Quality Assessment**: Evaluate new URLs against selection criteria
5. **Integration**: Add new URLs with appropriate documentation
6. **Testing**: Verify mode functionality with enhanced URL set
7. **Documentation**: Update guides and examples
8. **Community Feedback**: Gather input on improvements

## 🎯 **Specialized URL Collections**

### First-Time Burner Focus:
```yaml
source_urls:
  - https://burningman.org/event/preparation/
  - https://burningman.org/event/survive/
  - https://burningman.org/culture/philosophical-center/10-principles/
  - https://survival.burningman.org/
```

### Veteran Burner Enhancement:
```yaml
source_urls:
  # Include all basic URLs plus:
  - https://burningman.org/event/participate/volunteer/
  - https://burningman.org/event/art-performance/installations/
  - https://regionals.burningman.org/
  - https://journal.burningman.org/
```

### Theme Camp Leadership:
```yaml
source_urls:
  # Include core URLs plus:
  - https://burningman.org/event/participate/theme-camps/
  - https://burningman.org/event/black-rock-city-guide/infrastructure/
  - https://burningman.org/event/health-safety/
```

This comprehensive approach ensures the Burner Expert mode has access to current, authoritative, and community-aligned resources for all aspects of Burning Man preparation and participation.

Welcome home! 🏜️✨