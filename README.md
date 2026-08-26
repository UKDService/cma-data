# cma-data
Public CMA Data
## Overview
This project is used to hold the messages read by the Centralised Message API

## Architecture
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
## Deployment
A **Pull Request** is created containing the updated **messages.yaml** (either the **staging** branch for the staging environment or **main** for live).

Before the PR can be merged the file undergoes a number of checks or quality gates

## Quality gates

| **Gate** | **Check** |
|----------|-------|
| YAML | Is it valid YAML? |
| Schema | Is the structure and are the types correct? |
| Semantic | Do the values make sense? |
