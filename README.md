# Data Engineering Diagrams - PlantUML Claude Code Skill

A comprehensive Claude Code skill for creating professional, educational data engineering architecture diagrams using PlantUML.

## Overview

This skill enables Claude Code to generate sophisticated PlantUML diagrams for data engineering and end-to-end data architecture. The diagrams are designed to be:

- **Educational**: Clearly show data flow and architecture patterns
- **Professional**: Use icons, proper styling, and high contrast
- **Consistent**: Follow tested templates that produce landscape layouts
- **Comprehensive**: Support medallion architecture, ML pipelines, streaming, and more

## Example Diagrams

### Apex National Bank - ML Churn Prediction Pipeline

A 3-part diagram series showing a complete data engineering solution:

#### Part 1: Data Ingestion
![Part 1 - Data Ingestion](renders/part%201.png)

Source systems (ERPNext, Salesforce, Supabase, Google Sheets) are ingested via Python API clients into the Bronze layer in Databricks.

#### Part 2: dbt Transformation
![Part 2 - Transformation](renders/part%202.png)

Bronze data flows through dbt staging, matching, and testing to create Silver (star schema) and Gold (business aggregates) layers.

#### Part 3: ML & Consumption
![Part 3 - ML & Consumption](renders/part%203.png)

Gold layer feeds ML training (Gradient Boosting + MLflow), producing churn predictions that power Power BI dashboards and Slack alerts.

## Key Features

### Tested tupadr3 Icons
```plantuml
!include <tupadr3/devicons/database>
!include <tupadr3/devicons/python>
!include <tupadr3/font-awesome/cogs>
!include <tupadr3/font-awesome/line_chart>
!include <tupadr3/font-awesome/bell>
!include <tupadr3/font-awesome/users>
```

### Landscape Layout (Critical)
```plantuml
left to right direction
skinparam nodesep 50
skinparam ranksep 80
```

### High Contrast Styling
```plantuml
skinparam backgroundColor #FFFFFF
skinparam defaultFontColor #212121
skinparam defaultFontName "Segoe UI"
```

## File Structure

```
.
├── .claude/
│   └── skills/
│       └── data-architecture-diagram.md    # Main skill file
├── examples/
│   ├── apex-bank-part1-final.puml          # Ingestion diagram
│   ├── apex-bank-part2-final.puml          # Transformation diagram
│   └── apex-bank-part3-final.puml          # ML & Consumption diagram
├── renders/
│   ├── part 1.png                          # Rendered Part 1
│   ├── part 2.png                          # Rendered Part 2
│   └── part 3.png                          # Rendered Part 3
└── README.md
```

## Usage with Claude Code

1. Copy the `.claude/skills/data-architecture-diagram.md` file to your project
2. Ask Claude Code to create data architecture diagrams
3. Use the skill invocation `/data-arch` or ask naturally

### Example Prompts

- "Create a data lakehouse architecture diagram for AWS"
- "Design a streaming pipeline with Kafka and Flink"
- "Generate a medallion architecture diagram with dbt"
- "Create an ML feature engineering pipeline diagram"

## Architecture Patterns Supported

- **Medallion Architecture**: Bronze/Silver/Gold layers
- **Data Lakehouse**: S3/ADLS + Delta Lake + Spark
- **Real-Time Streaming**: Kafka, Flink, Event-driven
- **ETL/ELT Pipelines**: Batch and incremental processing
- **Data Mesh**: Domain-oriented, federated governance
- **ML Pipelines**: Feature stores, training, serving

## Rendering PlantUML

### VS Code Extension
Install the "PlantUML" extension by jebbs, then use `Alt+D` to preview.

### Online
Use [PlantUML Server](https://www.plantuml.com/plantuml/uml) to paste and render.

### Command Line
```bash
java -jar plantuml.jar diagram.puml
```

## Key Success Factors

1. **Always use `left to right direction`** - Forces landscape layout
2. **Use `rectangle` to group related elements** - Clean visual groupings
3. **Use `nodesep 50` and `ranksep 80`** - Proper spacing
4. **Use tupadr3 icons with `<$icon>` syntax** - Professional appearance
5. **Dark text on light backgrounds** - High contrast readability
6. **Legend at bottom** - Consistent placement

## License

MIT License - Feel free to use and modify for your projects.

## Author

Sulaiman Ahmed
