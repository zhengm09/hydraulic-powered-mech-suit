# Contributing Guide | 贡献指南

## How to Participate

### 1. Submit Issues
- Bug reports: Design defects, calculation errors, selection issues
- Feature suggestions: New scenario adaptation, performance optimization directions
- Discussion: Technical implementation questions, replication experience sharing

### 2. Submit Pull Requests
- Documentation improvement: Assembly guide, debugging manual, troubleshooting
- Design optimization: Structural weight reduction, hydraulic hose optimization
- Hardware design: PCB project files, driver circuit improvement
- Control algorithms: ZMP balance algorithm optimization, gait planning improvement

### 3. Replication Reports
- After completing hardware assembly, welcome to submit replication reports (with photos, test data, improvement suggestions)
- Help subsequent replicators avoid pitfalls

## Code Standards

### Documentation Format
- Chinese documentation uses Markdown, space between Chinese and English/Latin text
- Technical parameters retain units, tables aligned

### Firmware Development
- STM32 HAL library, follows MISRA C subset
- Comment coverage >=80% (critical algorithms 100%)

## Safety Design Principles

All contributions must follow:
1. **Do not reduce existing safety level** - No modification shall remove or weaken existing safety measures
2. **New features include protection** - New features must include corresponding fault protection mechanisms
3. **Verified before merge** - Key safety changes require calculation verification or simulation validation

## Development Roadmap Reference

Currently in Phase 0 (Design Finalization), welcome to participate in:
- Hydraulic schematic drawing and review
- Kinematic modeling and simulation
- Structural strength verification
- BOM list improvement and cost optimization