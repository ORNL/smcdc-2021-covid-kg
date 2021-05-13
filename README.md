# SMCDC 2021 -- Finding Novel Links in COVID-19 Knowledge Graph

A Shared Task at [SMC 2021](https://smc2021.ornl.gov/) that focuses on finding novel links in a knowledge graph generated from research literature on COVID-19. This is one of eight shared tasks conducted as part of [SMC Data Challenge 2021](https://smc-datachallenge.ornl.gov/).

## Shared task overview

The scientific literature is expanding at incredible rates, which were recently estimated to be in the millions of new articles per year. Extracting information from such vast stores of knowledge is an urgent need, as exemplified by the recent open release of materials relevant to the current SARS-CoV-2 pandemic. Given that the volume of information is easily beyond the capacity of any one person, analysts have been strongly motivated to develop automated knowledge-mining methods and extraction tools.

In this context, this challenge seeks to develop algorithms for the analysis and mining of *knowledge graphs*. More specifically, this challenge is based on the process of literature-based discovery. It has been shown that previously unknown relationships exist in the scientific literature that can be uncovered by finding concepts that link disconnected entities. This process, called *Swanson Linking*, is based on the discovery of hidden relations between concepts A and C via intermediate B-terms: if there is no known direct relation A-C, but there are published relations A-B and B-C one can hypothesize that there is a plausible, novel, yet unpublished indirect relation A-C. In this case the B-terms take the role of bridging concepts.  For instance, in 1986, Swanson applied this concept to propose a connection between dietary fish oil (A) and Raynaud's disease (C) through high blood viscosity (B), which fish oil reduces. This connection was validated in a clinical trial three years later.

## Task and data

**The main task in this challenge is to leverage a graph of biomedical concepts related to COVID-19 and the relations between them to try to discover novel, plausible relations between concepts.**

The data for this challenge can be downloaded from [https://doi.org/10.13139/OLCF/1782714](https://doi.org/10.13139/OLCF/1782714).

The following data is provided to participants:

* `edges_cc.csv`: Graph representing biomedical concepts and relations between them constructed from PubMed, Semantic MEDLINE, and CORD-19. This graph is provided as a CSV containing a list of edges. This part of the graph is undirected, i.e., A->B and B->A relations are considered identical.
* `edges_pc.csv`: Relations between concepts in the above graph and their source papers. These relations are again provided as a list of undirected edges.
* `edges_pp.csv`: Citation relations between papers in the graph. These relations are again provided as a list of edges. This part of the graph is directed, i.e., A->B represents a citation relation where A references B.
* `papers.csv`: Additional information about papers, mainly their date of publication.

A detailed description of this data is provided [here](https://zenodo.org/record/3980252).

The participants are asked to develop a model that will, given a historic snapshot of the data (e.g., all data in the graph up until March, 2020) predict which new links are likely to form in the future.

The participants are allowed to leverage external data, particularly data from PubMed and Semantic MEDLINE that are not included in the provided dataset.

### Challenge questions

* Analyze and visualize the provided graph and provide statistics such as, betweenness centrality, average path length and frequency of concept occurrence in different paths.
* Compare all pairs shortest path (APSP) statistics with the future connections -- are the length of a path between two concepts or other path statistics indicative of whether the concepts will form a connection in the future?
* Develop a classification or a model that uses APSP data or other relevant data as input and predicts which concepts will form a connection in the future.
* Develop ranking model/function for ranking the predicted links according to their importance.

## Timeline

* Registration opens: May 10
* Registration closes: June 22
* Submissions due: July 31
* Notification of acceptance: August 6
* SMC Conference: August 24-26

## Organizers and contact

* [Dasha Herrmannova](https://www.ornl.gov/staff-profile/drahomira-herrmannova)
* [Ramki Kannan](https://www.ornl.gov/staff-profile/ramakrishnan-kannan)
* [Seung-Hwan Lim](https://www.ornl.gov/staff-profile/seung-hwan-lim)
* [Tom Potok](https://www.ornl.gov/staff-profile/thomas-e-potok)

Please contact Dasha Herrmannova and CC Ramki Kannan and Seung-Hwan Lim with any questions about the challenge.
