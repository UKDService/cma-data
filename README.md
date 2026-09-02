# cma-data
Public CMA Data
## Overview
This project is used to hold the messages read by the Centralised Message API

## Message Format
The messages are held in **messages.yaml** in the following format:
```yaml
Messages:
  - message: "Example message"
    startDate: "2026-08-03T10:41:00Z"
    endDate: "2026-08-31T23:00:00Z"
    excludedDomains:
      - "ads.example.com"
      - "tracking.example.org"
    onlyOnDomain: "example.com"
    isEmergency: false
    
  - message: "Emergency example"
    startDate: "2026-08-31T07:00:00Z"
    endDate: "2026-08-31T23:00:00Z"
    excludedDomains: []
    onlyOnDomain: ""
    isEmergency: true

```

- message: text for the message
- startDate: start datetime of the message period
- endDate: end datetime of the message period
- excludedDomains: list of any domains to exclude
- onlyOnDomain: single domain for the message to appear on
- isEmergency: set this field to `true` if the message should be displayed **first** and with **more prominence**. If the field is `false`, the message will appear in normal order by end date 

## Deployment

Update **messages.yaml** and create a **Pull Request** targeting either the **staging** branch for the staging environment or **main** for live.

Before the PR can be merged the file undergoes a number of checks or quality gates

## Quality Gates

| **Gate** | **Check** |
|----------|-------|
| YAML | Is it valid YAML? |
| Schema | Is the structure and are the types correct? |
| Semantic | Do the values make sense? |
