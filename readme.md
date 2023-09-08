# Nuclear Power Plants
## An Analysis to Assess the Growth Opportunity for Nuclear Power Plants

### Problem Statement:

To identify countries and specific locations within the United States, where there is significant opportunity for growth in nuclear power generation. This will be done by evaluating the current operational capacities against energy needs, while also considering ecological and societal factors.

- **Availability of Cooling Water**: Existing and potential sites with abundant freshwater resources or access to the ocean.
  
- **Geological Stability**: Regions with low seismic activity and minimal risk of flooding are preferable for growth opportunities.
  
- **Proximity to Population Centers**: Current nuclear capacities in relation to major population centers to evaluate if they are serving the energy needs effectively.
  
- **Environmental Sensitivity**: Current ecological impact and public acceptance of existing nuclear power plants.

### Specific Objectives:

- Analyze the capacity of existing operational nuclear power plants per capita in each country.
  
- Evaluate how well the existing capacities meet the energy needs of the population.
  
- Assess the ecological and societal acceptance for potential growth.

### Expected Outcomes:

- A list of countries with significant growth opportunities for nuclear power, along with potential challenges.
  
- A methodology for evaluating the growth opportunities in nuclear power generation.

## Data Sources:

- Existing operational nuclear power plant locations: [https://www.kaggle.com/datasets/mexwell/geo-nuclear-data][https://github.com/cristianst85/GeoNuclearData/tree/master]
  
- Population Data: [https://data.worldbank.org/indicator/SP.POP.TOTL] [https://population.un.org/wup/Publications/Files/WUP2018-Report.pdf] [https://www.census.gov/quickfacts/fact/table/US/PST045219]
  
- Energy usage data: [https://www.iea.org/reports/world-energy-outlook-2022/key-findings]

## Data Cleaning and Preprocessing:

- The first step in the Data Wrangling process is to understand the data you are working with, so I took a look at the features to better grasp the information I am working with.
  
  - Data Columns Key
  
    - id - numeric id key
    - name - nuclear power plant name
    - latitude - latitude in decimal format
    - longitude - longitude in decimal format
    - country_code - ISO 3166-1 alpha-2 country code
    - status_id - nuclear power plant status id
    - reactor_type_id - nuclear reactor type id
    - reactor_model - nuclear reactor model
    - construction_start_at - date when nuclear power plant construction was started
    - operational_from - date when nuclear power plant became operational (also known as commercial operation date)
    - operational_to - date when nuclear power plant was shutdown (also known as permanent shutdown date)
    - capacity - nuclear power plant capacity (design net capacity in MWe) (see note)
    - source - source of the information
    - last_updated_at - date and time when information was last updated
    - iaea_id - IAEA PRIS reactor id (International Atomic Energy Agency Power Reactor Information System)

- Then I looked at the shape and the data types of each feature to see if there were any data type discrepancies, and to make sure that the data types would work  with the libraries that I planned to use

- Then I moved on to see if there were any missing data such as NAN's or NULL values, we ended up with 44 nuclear sites that did not list a lat or long coordinate, so they were omitted in this study due to not being to reliably get public lat long coordinates.

- There were also 79 nuclear sites that did not list production capacity, which I decided to use mean imputation for, as to not lose any more data fidelity.

- We started with 803 nuclear sites, but excluded the 44 with missing coordinates, which still gave us a healthy 759 sites to work with.

- I next took a look at the 'Status' feature to better understand what state each site was in. This yielded a few possibilities.

    - Shutdown
    - Operational
    - Under Construction
    - Planned
    - Cancelled Construction
    - Suspended Construction
    - Unknown
    - Decommissioning Completed
    - Suspended Operation
    - Never Commissioned

- Since the purpose of this study is to find sites and opportunites where we can grow Nuclear Power Production we are basically only concerned with 2 types of Nuclear sites, 'Operational' sites, and the rest were put into the second category as 'Shutdown'.

- This gave me a good understanding of the data I have to work with so at this point it was time to dive into analysis mode.


## Data Analysis Methods:

- Data Visualization
  - Horizontal Bar Charts
  - Bubble Plots
  - Maps (Heatmap and Map Markers)

- Capacity Aggregation/ Computation
- Comparative Analysis

## Tools Used:
- Python
- Jupyter Notebook
- Pandas
- Matplotlib
- Folium

## Results:

With a push from almost all developed countries and areas for cleaner energy creation, there are MAJOR opportunities for growth in this energy sector all over the world. Specifically in Africa, a continent of 1.4 billion people, and only 2 operational nuclear plants. Although the average African person uses 350kwh of electricty per year, a far cry from the average American, who uses about 11,000kwh per year, Africa is still woefully under energized.

Looking to more domestic areas, the average 'Western' person uses about 25kwh of electricty per day, and in America, nuclear makes up about 1/4 of that. Again, note that the current political climate is to push for 'greener' energy, so phasing out fossil fuels will come inevitably, but at what rate has yet to be determined. Regardless of what that time frame turns out to actually be, I believe that nuclear energy is the way to go. Especially given recent advancements in nuclear energy production and safety, such as small modular reactors, molten salt reactors, nuclear fusion (all beyond the scope of this study, but interesting topics unto themselves).

Given the CURRENT state of US energy production, it would be wise for us to invest in this technology as it provides clean and safe energy production. Using a heatmap of US Metro Areas overlayed with current operational nuclear power plants, it is easy to determine where the best locations for future sites may be, taking into account the following factors:

  - Size: The site should be able to accommodate the size of the nuclear power plant and its associated facilities.
  - Accessibility: The site should be accessible to transportation routes for the delivery of fuel and other supplies.
  - Water resources: The site should have adequate water resources for cooling and other purposes.
  - Seismic stability: The site should be in a seismically stable area.
  - Air quality: The site should be in an area with good air quality.
  - Population density: The site should be in an area with low population density.
  - Security: The site should be in an area with good security.

*See **Stake Holder Presentation** for maps of potential site locations*

Given these factors, a few sites were identified as potential sites for future nuclear power plants. One thing to note is that the sites in the California region, were picked based on the areas with the LEAST seismic activity given a historical range with the gian caveat that no area is truly immune from seismic activity.

Also, since we are focusing on the largest metro areas, in this study, I have included some areas where it may be more cost responsible to refurbish or retool, decommissioned or shutdown sites, as opposed to start from scratch.

## Conclusion:

In conclusion, the urgency for sustainable and efficient energy solutions has never been more palpable, underscored by the global push for greener technologies. While areas like Africa remain significantly under-energized, developed regions are also in a race against time to phase out fossil fuels. Nuclear energy, with its advancements in safety and efficiency, stands out as a highly viable solution to meet these escalating demands. This analysis, grounded in concrete data, suggests that strategic investments in nuclear technology in the U.S. would not only meet the daily energy consumption of its populous metro areas but also serve as a model for clean and sustainable energy globally. By applying meticulous site selection criteria—from size and accessibility to seismic stability and security—I have identified key locations for future nuclear installations. These range from entirely new sites to the refurbishment of existing, decommissioned facilities, each offering a unique set of advantages and challenges. As we look ahead, these findings arm us with the insights needed to make informed decisions, ensuring that we are not just reacting to the energy needs of today but are well-prepared for the demands of tomorrow.

## Limitations:

- The analysis is limited to the available data sources.
  
- The methodology for evaluating growth opportunities is based on several assumptions.
  
- A deeper dive into reactor types and building costs of each will be required to get estimations on ROI.

## Next Steps:

- Refine the methodology by incorporating additional factors, such as the cost of building and operating a nuclear power plant in potential growth countries.
  
- Conduct a more detailed analysis of the ecological and societal factors that could affect growth.
  
- Engage with stakeholders to get feedback on the methodology and results.

