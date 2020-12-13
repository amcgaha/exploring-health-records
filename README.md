# Exploring Cold & Flu Symptoms at Summer Camp
My summer camp is revising our communicable disease plan for summer 2021. In addition to public health research and expert advice, we hope to study our own health center records to see what we can learn from possible respiratory infections at camp in the past. This project explores a tidy dataset created in [this previous project](https://github.com/amcgaha/coding-health-records), focusing on cold and flu symptoms reported to the health center.

A summary analysis is produced for decision-makers, along with recommendations for policy changes to address issues revealed by the data.

The primary conclusion is that increased monitoring, especially early on in the summer, can facilitate prompt and early interventions. These two actions may help control the spread of disease and improve the wellbeing of people at camp.

## Contents
1.	[Introduction](https://github.com/amcgaha/exploring-health-records#introduction)
2.	[Data Source](https://github.com/amcgaha/exploring-health-records#data-source)
3.	[Methods & Tools](https://github.com/amcgaha/exploring-health-records#methods--tools)
4.	[Procedure](https://github.com/amcgaha/exploring-health-records#procedure)
5.	[Products](https://github.com/amcgaha/exploring-health-records#products)
6.	[Next Steps](https://github.com/amcgaha/exploring-health-records#next-steps)

## Introduction
The COVID-19 pandemic has caused many organizations to reevaluate their communicable disease protocols. My organization, a summer camp that did not open in 2020, is working on a safety plan to open this summer, which requires a careful study of best practices and risk management techniques.

We always followed basic measures, like washing hands and sanitizing surfaces. However, our knowledge of best practices has advanced significantly in the past year. In particular, we have learned the importance of social distancing, wearing masks, and isolating patients who are suspected to have a communicable disease.

While they are now solidifying as social norms, these public health protocols seemed over-serious, even foreign, in the years before COVID-19. We certainly took any illness seriously, especially those accompanied by fever. However, a cold or cough was not a trigger for immediate isolation, mask wearing, or distancing, as would likely now be the case. As a result, we suspect our communicable disease protocol may not have been as robust as it needs to be during this and following summers.

Consider this plot. It shows the percent of all visits to the health center that show cold and flu symptoms. They are presented in chronological order, with the first day of camp on the left. The labels note camp sessions, which is the label most useful to the audience of camp leadership.

![Image](https://github.com/amcgaha/exploring-health-records/blob/main/images/daily_plot_both.png)


This plot matches the staff experience particularly well. Anecdotally, staff members -- including me -- can recall that getting a cold or other respiratory infection in the past has seemed normal. We have gotten sick, took some medication to relieve symptoms, and often kept working. The COVID-19 pandemic has shown us that these norms ignored some basic ways we can help reduce the spread of communicable diseases at camp.

As part of our broader planning strategy, we would like to explore how respiratory infections may have manifested and spread at camp in the past. Knowing differences between staff and campers, for example, could help us generate smarter policies for each group. Watching how diseases manifest and change over time may also yield useful insights.

This project analyzes health center records, which are described in more detail below. It produces a summary of findings for decision-makers and recommendations for policy changes.

## Data Source
The dataset explored here was produced in a [a previous project](https://github.com/amcgaha/coding-health-records), which transformed messy, text-centered reports into a tidy dataset.

The process to create the dataset was laborious, but it involved programmatically scanning text reports for a number of keywords representing categories. Then, records were tagged as True or False for each category. For example, if a text report mentioned "congestion" or "stuffy nose", the record was labeled True for the larger category "congestion." Records were then uploaded to an existing database containing camp information and linked to other tables with information about summer dates and people.

For this project, an expanded dataset was retrieved from the database to include information about summer dates. The dataset contains more than 3,700 records from the years 2013 to 2019. It includes health center visits from both campers and staff across all camp sessions.

To learn more about the data source and the resulting dataset, [visit this project repository.](https://github.com/amcgaha/coding-health-records)

__Data Privacy Note__: Health records are extremely sensitive and regulated by law. The full dataset will not be posted publicly. Only the documentation of my process is posted here.

## Methods & Tools
The data is maintained in a __Postgres__ database. To maintain flexibility and anonymity, as well as connect useful information about specific summer dates, the dataset was downloaded from the database in csv format using __SQL__ queries.

The data is processed and explored in __Python__, using the standard data science libraries __pandas__, __seaborn__, and __matplotlib__.

## Procedure
The data exploration and analysis is shown step by step in the following __Jupyter Notebook__.

[View Notebook](https://github.com/amcgaha/exploring-health-records/blob/main/exploring_health_notebook.ipynb)

## Products
A summary of analysis and recommendations has been provided to decision-makers. That document is available here as a PDF.

[View Summary for Decision-Makers](https://github.com/amcgaha/exploring-health-records/blob/main/cold_flu_summary_decision_makers.pdf)

The headline recommendations are to:
* Hire medical staff during the staff training week and screen staff for symptoms
* Ensure all medical staff are trained in standards for record-keeping
* Inspect records weekly and ensure data is being recorded properly
* In the first weeks of camp, focus on monitoring, prevention, and early interventions
* As the summer moves on, continue to maintain high standards for hygiene, cleaning, and monitoring
* Provide specific advice on reducing spread to anyone who shows symptoms. This should happen not only at the onset of symptoms, but also at the end of each session and the end of summer, to help keep other staff healthy and campers' families healthy.

## Next Steps
### 1. Provide Addendum for COVID-19
This project made some recommendations for decision-makers based on past data. Some of those recommendations should be adjusted for this summer in particular due to the COVID-19 pandemic. Most policy changes will need to be more robust, strict, and serious this year.

For example, anyone who reports to the health center with a cough may need to be isolated completely and even sent home. In future years, we may not need to be that strict. A camper with a cough may simply need to wear a mask and take meals at the health center.

An important next step will be to develop an addendum for decision-makers that outlines some possible differences in the recommendations. It may be useful to develop this document with the help of longtime camp medical staff.

### 2. Revise Health Center Training
To ensure strong data collection in the future, we must revise how we onboard and train medical staff. Thanks to discoveries made in this project, we now know that visits to the health hut have been significantly underreported in two circumstances.

First, since medical staff are often not present during Staff Training, few years show any visits at all. Years that did report visits, however, often showed cold and flu symptoms. If illnesses are to be controlled, medical staff will need to be present, trained, and vigilant starting the first day of camp.

The second circumstance was the entire year of 2016. That year, medical staff failed to record a huge number of visits, resulting in a year with much less useful data.

These discoveries highlight the importance of careful training for medical staff. These professionals know how to make reports. They may simply need clear guidance to our expectations, how our system works, and support to ensure their reports are being entered correctly.

### 3. Develop Data Model
Consider this statistical plot of camper visits to the health center showing cold and flu symptoms.

![Image](https://github.com/amcgaha/exploring-health-records/blob/main/images/session_plot_campers.png)


Camper visits to the health center seem fairly predictable across the summer. A useful next step would be to develop a data model. With a model, we would be able to show how normal or abnormal the number of health hut visits seems.

This will be useful in the summer. While individual cases will need to be tracked carefully, we would also be able to look at the number of visits for any category -- including injuries, bug bites, or even anxiety -- and assess if our numbers fit within what we expect based on the past.

We would hope to see lower numbers than is typical of the past. That might provide evidence suggesting our policy changes have been effective.

### 4. Update High-Level Communication Tools
During the summer, camp directors communicate important information among each other using a daily report form. That form does not yet include a specific spot for reporting health concerns. Especially considering the high stakes of COVID-19, that form should be revised to include health concerns or other information that could aid prevention strategies. With this adjustment, the form could also be an important source of data going forward.
