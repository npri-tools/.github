The npri-tools project contextualizes publicly-available information relevant to addressing environmental racism in Canada.

## Motivation
Dr. Ingrid Waldron [defines](https://en.ccunesco.ca/-/media/Files/Unesco/Resources/2020/07/EnvironmentalRacismCanada.pdf) environmental racism as "environmental policies, practices, or directives that disproportionately
disadvantage individuals, groups, or communities (intentionally or unintentionally) based on race or colour definition." The outcomes of environmental racism include inequitable access to environmental goods such as clean drinking water, unfair distribution of environmental harms such as air pollution, and uneven access to legal and other mechanisms that would address these. As Waldron notes, environmental racism "compounds other existing inequalities and challenges that Indigenous and other racialized groups face, such as low-income and poverty, underemployment and unemployment, food insecurity, poor access to healthcare, among others." 

As of February 2024, Bill C-226 is under consideration in committee in Canada's Senate. Among other things, the Bill [proposes](https://www.parl.ca/DocumentViewer/en/44-1/bill/C-226/third-reading) addressing environmental racism through "a study that includes (i) an examination of the link between race, socio-economic status and environmental risk, and (ii) information and statistics relating to the location of environmental hazards." 

npri-tools contributes to this work by prototyping what the data infrastructure for it might look like.

## Data Sources and Interpretation
We copy the National Pollutant Release Inventory (NPRI)'s Microsoft Access [database](https://open.canada.ca/data/en/dataset/06022cc0-a31e-4b4c-850d-d4dccda5f3ac) of emissions reports, company ownership, and more covering the years 1993-2022.

In the future, we hope to compile provincial-level enforcement and compliance records in order to understand the extent to which industry meets legal requirements and ministries implement rules. Claire Ewing, a graduate of UBC's Master in Environment, Resources and Sustainability, brought together that information for her [thesis](https://open.library.ubc.ca/soa/cIRcle/collections/ubctheses/24/items/1.0402474?o=16). Unfortunately, there doesn't seem to be any straightforward way to link provincial and federal-level records. For instance, Ontario's violations records do not link facilities with their NPRI identifiers. It may be possible to connect Ontario facility records with NPRI facility records based on contextual information, such as addresses, rather than IDs, but even basic information such as facility location is inconsistenly reported.

It's crucial to keep in mind that NPRI records are self-reported from industry. As in the United States, these reports are often based on [modeled estimates](https://propublica.org/article/whats-polluting-the-air-not-even-the-epa-can-say) rather than direct measurements and do not reflect pollutant concentrations in the air, water, or land. Recent research, for instance, has found [staggering discrepancies](https://www.cbc.ca/news/science/alberta-oilsands-research-emissions-1.7093626) between what some oil and gas operations report to NPRI and the actual concentration of pollutants in the air around these operations. NPRI itself has some useful [notes](https://www.canada.ca/en/environment-climate-change/services/national-pollutant-release-inventory/using-interpreting-data.html) on how to interpret its data. 

One of the most glaring omissions from NPRI's records is any attempt to connect pollutants with health outcomes. Please visit the Indigenous-led Environmental Data Justice [lab](https://technoscienceunit.org/people/lab/) to learn about their work with communities in Ontario's Chemical Valley to "gather and translate diverse technical information into an accessible form so that people can more easily link health issues to facility activities." 

We have also made a complete copy of Statistics Canada's 2021 Census though, at the moment, we only provide complete access to a handful of variables at the dissemination area scale. Although in many respects the Census is a robust snapshot of socio-economic patterns, it is well-recognized that measures such as "Aboriginal identity" are undercounted (i.e. in First Nation [reserves](https://www.cbc.ca/news/canada/north/indigenous-gaps-census-1.6419156) and [urban areas](https://www.cbc.ca/news/canada/toronto/toronto-urban-indigenous-census-1.6192449)).

## Research
We are asking a variety of questions:
- What do researchers, policy-makers, and public and community groups need to know about the pollutants reported being released to the air, water, and land where they live?
- What can existing publicly-available information tell us and what can't it?
- How can we connect communities with similar "profiles" - emissions, industries, and socio-economics?

Concretely, the tools we've built are meant to answer questions such as:
- What NPRI-reporting facilities are near where I live?
- What are the socio-economic characteristics of this place, as measured by the Census?
- Which companies account for most of the releases of a given pollutant?
- What are the most common pollutants reported by an industrial sector?
- How often was a pollutant reported as released over some timeframe?
- Where are there data gaps and why do they exist?

## Tools
- `npri-db`: the scripts we use to access and copy NPRI, Stat Can, and other data
- `npri-vm`: configurations for the web server hosting our copy of NPRI and Stat Can data (TBD)
- `npri`: a Python package providing easy-to-use code that returns recently reported emissions from facilities, socio-economic information for places, emissions records for specific companies and industries, and emissions trends over time
- `npri-web-*`: a set of dashboards that use all of the above so that users can intuitively and interactively summarize NPRI information (TBD)

## Contributions
We're glad you're here - we welcome your help! One way to get started is by reviewing the Issues posted in each repository.

We follow the Environmental Data and Governance Initiative's [Code of Conduct](https://docs.google.com/document/d/1zqFPVjQ__x3tfcSlir-jeO7O-mcCh4oKyNNlJEpJMOU/edit#heading=h.2453p0hjle5m).
