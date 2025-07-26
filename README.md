# Aviation Risk Assessment Project

## Overview

This project dives deep into aviation incident data to help a company venturing into the airline industry identify the lowest-risk aircraft to invest in. Through structured data cleaning, analysis, and visualization, this notebook translates raw data into business intelligence tailored for high-stakes decision-making.

##  Business Understanding

**Scenario:**  
Your company is exploring new business verticals and is considering investing in aviation for commercial and private purposes. However, the risk factors associated with different aircraft types remain unknown. As a data analyst, your mission is to identify which aircraft categories and conditions result in the least severe outcomes in incidents.

**Stakeholder:**  
Head of the new aviation division, who will use this data-driven insight to inform strategic procurement decisions.

**Key Questions:**
- Which aircraft categories are linked to higher injury severity?
- Does weather condition impact the severity of incidents?
- Which flight purposes tend to be riskier?
- How have incidents trended over time?

## Data Understanding and Analysis

**Data Source:**  
U.S. National Transportation Safety Board (NTSB) aviation incident records (CSV/XLSX format).

**Key Columns:**
- `Event_Date`, `Location`, `Aircraft_Category`, `Injury_Severity`, `Weather_Condition`, `Purpose_of_flight`, etc.

**Cleaning Steps:**
- Filled missing numerical and categorical data.
- Dropped columns with over 80% missing data.
- Removed illegal characters that could corrupt Excel output.
- Added derived fields such as `Year` and `Injury_Severity_Categorized`.

## Key Visualizations

### 1. Events Per Year

{
  "config": {"view": {"continuousWidth": 300, "continuousHeight": 300}},
  "data": {"name": "data-7fdd64e6a90974456854043a276e0757"},
  "mark": {"type": "line", "point": true},
  "encoding": {
    "tooltip": [
      {"field": "Year", "type": "quantitative"},
      {"field": "Event_Count", "type": "quantitative"}
    ],
    "x": {"axis": {"title": "Year"}, "field": "Year", "type": "ordinal"},
    "y": {
      "axis": {"title": "Number of Events"},
      "field": "Event_Count",
      "type": "quantitative"
    }
  },
  "params": [
    {
      "name": "param_12",
      "select": {"type": "interval", "encodings": ["x", "y"]},
      "bind": "scales"
    }
  ],
  "title": "Number of Aviation Events per Year (Event Date)",
  "$schema": "https://vega.github.io/schema/vega-lite/v5.8.0.json",
  "datasets": {
    "data-7fdd64e6a90974456854043a276e0757": [
      {"Year": 1948, "Event_Count": 1},
      {"Year": 1962, "Event_Count": 1},
      {"Year": 1974, "Event_Count": 1},
      {"Year": 1977, "Event_Count": 1},
      {"Year": 1979, "Event_Count": 2},
      {"Year": 1981, "Event_Count": 1},
      {"Year": 1982, "Event_Count": 3593},
      {"Year": 1983, "Event_Count": 3556},
      {"Year": 1984, "Event_Count": 3457},
      {"Year": 1985, "Event_Count": 3096},
      {"Year": 1986, "Event_Count": 2880},
      {"Year": 1987, "Event_Count": 2828},
      {"Year": 1988, "Event_Count": 2730},
      {"Year": 1989, "Event_Count": 2544},
      {"Year": 1990, "Event_Count": 2518},
      {"Year": 1991, "Event_Count": 2462},
      {"Year": 1992, "Event_Count": 2355},
      {"Year": 1993, "Event_Count": 2313},
      {"Year": 1994, "Event_Count": 2257},
      {"Year": 1995, "Event_Count": 2309},
      {"Year": 1996, "Event_Count": 2187},
      {"Year": 1997, "Event_Count": 2148},
      {"Year": 1998, "Event_Count": 2226},
      {"Year": 1999, "Event_Count": 2209},
      {"Year": 2000, "Event_Count": 2220},
      {"Year": 2001, "Event_Count": 2063},
      {"Year": 2002, "Event_Count": 2020},
      {"Year": 2003, "Event_Count": 2085},
      {"Year": 2004, "Event_Count": 1952},
      {"Year": 2005, "Event_Count": 2031},
      {"Year": 2006, "Event_Count": 1851},
      {"Year": 2007, "Event_Count": 2016},
      {"Year": 2008, "Event_Count": 1912},
      {"Year": 2009, "Event_Count": 1783},
      {"Year": 2010, "Event_Count": 1793},
      {"Year": 2011, "Event_Count": 1871},
      {"Year": 2012, "Event_Count": 1894},
      {"Year": 2013, "Event_Count": 1651},
      {"Year": 2014, "Event_Count": 1646},
      {"Year": 2015, "Event_Count": 1651},
      {"Year": 2016, "Event_Count": 1738},
      {"Year": 2017, "Event_Count": 1753},
      {"Year": 2018, "Event_Count": 1860},
      {"Year": 2019, "Event_Count": 1766},
      {"Year": 2020, "Event_Count": 1539},
      {"Year": 2021, "Event_Count": 1655},
      {"Year": 2022, "Event_Count": 1800}
    ]
  }
}


This line chart shows the trend of aviation events over the years, highlighting spikes or dips in incident frequency.

---

### 2.  Injury Severity by Aircraft Category
This bar chart identifies which aircraft categories experience the most severe outcomes.


{
  "config": {"view": {"continuousWidth": 300, "continuousHeight": 300}},
  "data": {"name": "data-d7d651bdce611488ed6c2343a7ba091b"},
  "mark": {"type": "bar"},
  "encoding": {
    "color": {
      "field": "Injury_Severity_Categorized",
      "title": "Injury Severity",
      "type": "nominal"
    },
    "tooltip": [
      {"field": "Aircraft_Category", "type": "nominal"},
      {"field": "Injury_Severity_Categorized", "type": "nominal"},
      {"field": "Count", "type": "quantitative"}
    ],
    "x": {
      "field": "Aircraft_Category",
      "title": "Aircraft Category",
      "type": "nominal"
    },
    "y": {
      "field": "Count",
      "title": "Number of Incidents",
      "type": "quantitative"
    }
  },
  "height": 600,
  "params": [
    {
      "name": "param_1",
      "select": {"type": "interval", "encodings": ["x", "y"]},
      "bind": "scales"
    }
  ],
  "title": "Injury Severity by Aircraft Category",
  "width": 800,
  "$schema": "https://vega.github.io/schema/vega-lite/v5.8.0.json",
  "datasets": {
    "data-d7d651bdce611488ed6c2343a7ba091b": [
      {
        "Aircraft_Category": "Airplane",
        "Injury_Severity_Categorized": "Fatal",
        "Count": 82942
      },
      {
        "Aircraft_Category": "Airplane",
        "Injury_Severity_Categorized": "Incident",
        "Count": 2209
      },
      {
        "Aircraft_Category": "Airplane",
        "Injury_Severity_Categorized": "Minor",
        "Count": 176
      },
      {
        "Aircraft_Category": "Airplane",
        "Injury_Severity_Categorized": "Other/Unknown",
        "Count": 93
      },
      {
        "Aircraft_Category": "Airplane",
        "Injury_Severity_Categorized": "Serious",
        "Count": 135
      },
      {
        "Aircraft_Category": "Balloon",
        "Injury_Severity_Categorized": "Fatal",
        "Count": 225
      },
      {
        "Aircraft_Category": "Balloon",
        "Injury_Severity_Categorized": "Serious",
        "Count": 6
      },
      {
        "Aircraft_Category": "Blimp",
        "Injury_Severity_Categorized": "Fatal",
        "Count": 4
      },
      {
        "Aircraft_Category": "Glider",
        "Injury_Severity_Categorized": "Fatal",
        "Count": 502
      },
      {
        "Aircraft_Category": "Glider",
        "Injury_Severity_Categorized": "Minor",
        "Count": 4
      },
      {
        "Aircraft_Category": "Glider",
        "Injury_Severity_Categorized": "Serious",
        "Count": 2
      },
      {
        "Aircraft_Category": "Gyrocraft",
        "Injury_Severity_Categorized": "Fatal",
        "Count": 168
      },
      {
        "Aircraft_Category": "Gyrocraft",
        "Injury_Severity_Categorized": "Minor",
        "Count": 5
      },
      {
        "Aircraft_Category": "Helicopter",
        "Injury_Severity_Categorized": "Fatal",
        "Count": 3370
      },
      {
        "Aircraft_Category": "Helicopter",
        "Injury_Severity_Categorized": "Incident",
        "Count": 9
      },
      {
        "Aircraft_Category": "Helicopter",
        "Injury_Severity_Categorized": "Minor",
        "Count": 33
      },
      {
        "Aircraft_Category": "Helicopter",
        "Injury_Severity_Categorized": "Other/Unknown",
        "Count": 3
      },
      {
        "Aircraft_Category": "Helicopter",
        "Injury_Severity_Categorized": "Serious",
        "Count": 25
      },
      {
        "Aircraft_Category": "Powered Parachute",
        "Injury_Severity_Categorized": "Fatal",
        "Count": 89
      },
      {
        "Aircraft_Category": "Powered Parachute",
        "Injury_Severity_Categorized": "Serious",
        "Count": 2
      },
      {
        "Aircraft_Category": "Powered-Lift",
        "Injury_Severity_Categorized": "Fatal",
        "Count": 4
      },
      {
        "Aircraft_Category": "Powered-Lift",
        "Injury_Severity_Categorized": "Incident",
        "Count": 1
      },
      {
        "Aircraft_Category": "Rocket",
        "Injury_Severity_Categorized": "Fatal",
        "Count": 1
      },
      {
        "Aircraft_Category": "ULTR",
        "Injury_Severity_Categorized": "Serious",
        "Count": 1
      },
      {
        "Aircraft_Category": "UNK",
        "Injury_Severity_Categorized": "Fatal",
        "Count": 2
      },
      {
        "Aircraft_Category": "Ultralight",
        "Injury_Severity_Categorized": "Fatal",
        "Count": 30
      },
      {
        "Aircraft_Category": "Unknown",
        "Injury_Severity_Categorized": "Fatal",
        "Count": 14
      },
      {
        "Aircraft_Category": "WSFT",
        "Injury_Severity_Categorized": "Fatal",
        "Count": 7
      },
      {
        "Aircraft_Category": "WSFT",
        "Injury_Severity_Categorized": "Serious",
        "Count": 2
      },
      {
        "Aircraft_Category": "Weight-Shift",
        "Injury_Severity_Categorized": "Fatal",
        "Count": 161
      }
    ]
  }
}

---

### 3.  Injury Severity by Weather Condition
Visualizing how weather conditions correlate with incident severity.

{
  "config": {"view": {"continuousWidth": 300, "continuousHeight": 300}},
  "data": {"name": "data-7326240dc68a53761be77323d182241d"},
  "mark": {"type": "bar"},
  "encoding": {
    "color": {
      "field": "Injury_Severity_Categorized",
      "title": "Injury Severity",
      "type": "nominal"
    },
    "tooltip": [
      {"field": "Weather_Condition", "type": "nominal"},
      {"field": "Injury_Severity_Categorized", "type": "nominal"},
      {"field": "Count", "type": "quantitative"}
    ],
    "x": {
      "field": "Weather_Condition",
      "title": "Weather Condition",
      "type": "nominal"
    },
    "y": {
      "field": "Count",
      "title": "Number of Incidents",
      "type": "quantitative"
    }
  },
  "height": 600,
  "params": [
    {
      "name": "param_7",
      "select": {"type": "interval", "encodings": ["x", "y"]},
      "bind": "scales"
    }
  ],
  "title": "Injury Severity by Weather Condition",
  "width": 500,
  "$schema": "https://vega.github.io/schema/vega-lite/v5.8.0.json",
  "datasets": {
    "data-7326240dc68a53761be77323d182241d": [
      {
        "Weather_Condition": "IMC",
        "Injury_Severity_Categorized": "Fatal",
        "Count": 5745
      },
      {
        "Weather_Condition": "IMC",
        "Injury_Severity_Categorized": "Incident",
        "Count": 218
      },
      {
        "Weather_Condition": "IMC",
        "Injury_Severity_Categorized": "Minor",
        "Count": 4
      },
      {
        "Weather_Condition": "IMC",
        "Injury_Severity_Categorized": "Other/Unknown",
        "Count": 6
      },
      {
        "Weather_Condition": "IMC",
        "Injury_Severity_Categorized": "Serious",
        "Count": 3
      },
      {
        "Weather_Condition": "UNK",
        "Injury_Severity_Categorized": "Fatal",
        "Count": 730
      },
      {
        "Weather_Condition": "UNK",
        "Injury_Severity_Categorized": "Incident",
        "Count": 100
      },
      {
        "Weather_Condition": "UNK",
        "Injury_Severity_Categorized": "Other/Unknown",
        "Count": 26
      },
      {
        "Weather_Condition": "Unk",
        "Injury_Severity_Categorized": "Fatal",
        "Count": 261
      },
      {
        "Weather_Condition": "Unk",
        "Injury_Severity_Categorized": "Serious",
        "Count": 1
      },
      {
        "Weather_Condition": "VMC",
        "Injury_Severity_Categorized": "Fatal",
        "Count": 80783
      },
      {
        "Weather_Condition": "VMC",
        "Injury_Severity_Categorized": "Incident",
        "Count": 1901
      },
      {
        "Weather_Condition": "VMC",
        "Injury_Severity_Categorized": "Minor",
        "Count": 214
      },
      {
        "Weather_Condition": "VMC",
        "Injury_Severity_Categorized": "Other/Unknown",
        "Count": 64
      },
      {
        "Weather_Condition": "VMC",
        "Injury_Severity_Categorized": "Serious",
        "Count": 169
      }
    ]
  }
}

---

## Conclusion

###  Summary of Findings:
- **Helicopters and Experimental Aircrafts** showed a higher proportion of fatal incidents.
- **Good weather** does not guarantee low risk — many severe incidents still occurred under clear conditions.
- **Personal and Instructional flights** experienced a disproportionately higher rate of severe incidents.

### Recommendation:
Start with investing in **Multi-engine Land** aircraft used for **Business or Commuter** purposes under **favorable weather**, as they showed lower incident severity in historical data.

---
