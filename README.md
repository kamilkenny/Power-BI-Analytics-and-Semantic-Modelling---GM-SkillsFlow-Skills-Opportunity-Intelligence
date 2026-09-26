# Power-BI-Analytics-and-Semantic-Modelling---GM-SkillsFlow-Skills-Opportunity-Intelligence
The page should explain the journey from source data → ingestion → Bronze → Silver → Gold → dimensional modelling → semantic model → DAX/reporting → Power BI, then use your dashboard image as the visible outcome of that engineering work.

# Power BI Analytics and Semantic Modelling

## GM SkillsFlow | Skills & Opportunity Intelligence

<img width="1386" height="787" alt="Screenshot 2026-09-26 103610" src="https://github.com/user-attachments/assets/02e7bf85-4b00-430b-9fb1-6df3d3906448" />


**GM SkillsFlow** is an end to end data intelligence platform designed to connect education, apprenticeships, skills supply, youth participation and labour market opportunity across the ten boroughs of Greater Manchester.

The Power BI component is the analytical and decision support layer of the wider platform. It does not operate directly on raw source files. Instead, it consumes governed and modelled data produced through the project's Microsoft Fabric data engineering architecture.

The objective is to provide a consistent analytical view of questions such as:

1. How do employment and economic inactivity differ across Greater Manchester?
2. Which boroughs have stronger or weaker apprenticeship participation?
3. How are apprenticeship starts translating into achievements?
4. Where are NEET and Not Known rates highest?
5. How have labour market conditions changed over time?
6. How can education and skills supply be related to local economic opportunity?
7. How can MBacc pathways and subject areas be connected to skills demand and labour market outcomes?

The Power BI report therefore represents the final business intelligence layer of a much larger data engineering and analytical workflow.

---

## Power BI Report Preview

![GM SkillsFlow Power BI Dashboard](../assets/powerbi/gm-skillsflow-overview.png)

> Replace the image path above with the final location of the Power BI screenshot in the repository.

The current executive overview brings together employment, economic inactivity, apprenticeships and NEET indicators into a single Greater Manchester intelligence view.

The report is designed so that headline regional indicators can be viewed alongside borough level variation and longer term labour market trends.

---

# 1. From Public Data to Decision Intelligence

The Power BI report is not built directly from individual CSV, Excel or API responses.

Before information becomes available to Power BI, it passes through a controlled data engineering architecture that preserves the raw source, validates and standardises the data, creates analytical entities, applies business rules and exposes governed Gold layer data for reporting.

The main source domains used by GM SkillsFlow include:

| Source domain | Purpose |
|---|---|
| Department for Education | Apprenticeship starts, achievements, participation and youth education indicators |
| ONS Nomis Annual Population Survey | Employment, unemployment and economic inactivity indicators |
| NEET and participation datasets | Young people who are Not in Education, Employment or Training, including Not Known classifications |
| Greater Manchester MBacc reference data | Mapping education and subject pathways to the Greater Manchester Baccalaureate framework |
| Greater Manchester geography | Consistent borough level analytical structure |

The platform therefore combines information that would otherwise sit in separate datasets and reporting systems.

---

# 2. End to End Data Architecture

```mermaid
flowchart LR

    A[Department for Education] --> E[Microsoft Fabric Data Factory]
    B[ONS Nomis APS] --> E
    C[NEET and Participation Data] --> E
    D[GMCA MBacc Reference Data] --> E

    E --> F[Bronze Lakehouse]

    F --> G[PySpark Validation and Transformation]

    G --> H[Silver Lakehouse]

    H --> I[Dimensional and Business Modelling]

    I --> J[Gold Warehouse]

    J --> K[Power BI Semantic Model]

    K --> L[DAX Measures and KPIs]

    L --> M[Interactive Power BI Reports]

    M --> N[Greater Manchester Skills and Opportunity Intelligence]
