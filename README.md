# MUSA 509 2021 — Final Project

The final project will be the culmination of all of the skills learned and practiced in this class. Students will build a data pipeline and a dashboard to help make some domain-specific operational decisions. The pipeline will extract data from various 3rd-party sources, load that data into a data warehouse, transform the data into an appropriate domain model, and render reports populated with maps, charts, and prose.

**Your code repository, Airflow server address, and generated report address should be slacked to me by December 10.**

Expectations:
* Pipelines will be built in Airflow (unless prior approval for a different platform is received).
* Multiple data sources will be used, at least one of which gets updated "frequently" (no less than monthly).
* Reports contain at least one chart, one map, and one dynamically generated paragraph.
* Queries to build reports are simple (no complex joins, limited sub-queries and CTEs); data should be pre-transformed for the domain.
* Reports will be hosted in the cloud at a URL that can be publicly accessed.

This project may be done individually or in a team of up to 3 students.

## Table of Contents

* [Proposal](#proposal)
* [Suggested Process](#suggested-process)
* [Final Project Requirements](#project-requirements)

## Proposal

A project proposal is due Wednesday, Nov 17th. Please create a GitHub repository on your account with a name of your choosing. Place your proposal in your project GitHub repo in a file called `proposal.md`. Write the proposal in markdown (how all class READMEs are written). If you need a markdown reference, check out [GitHub's](https://guides.github.com/features/mastering-markdown/). There are [many more online](https://www.google.com/search?q=markdown+reference).

The proposal consists of:

0. Authors — list the names of everyone part of producing the project.
1. Abstract — a paragraph description of the problem/situation/domain/etc. The Abstract should clearly state the types of decisions that your dashboard is going to help facilitate.
2. List of data sources you intend to use for this project. For each data source, please list:
   * Where you can get access to the dataset (e.g., a URL, government agency, third-party API, BigQuery public dataset, etc.)
   * Size of dataset (if applicable)
   * Whether you currently have access to this data

3. Wireframes of the webpage(s) for your project. This of a wireframe as an outline for an interactive project. It allows you to quickly communicate the general makeup and organization of the dashboard content. See [this page](https://careerfoundry.com/en/blog/ux-design/how-to-create-your-first-wireframe/) for guidance on creating wireframes. Hand-drawn or digital are both acceptable, but please scan or take pictures of the hand-drawn ones for inclusion in the repo. Link the images in the proposal markdown. Interactive wireframes are acceptable too. Many free and paid tools exist for creating wireframes (Adobe Wireframe XD, [MockFlow](https://mockflow.com/), [Figma](https://www.figma.com/wireframe-tool/), etc.)

## Suggested Process

Use the following as a rough task list of things that you'll need to do to complete your project:

0. Brainstorm for aspects of your proposal
1. Develop metrics that will help inform the domain decisions
1. Get familiar with the content of potential datasets; understand what might inform your metrics, and what holes there still are
1. Consider best way to communicate metrics; for example:
   - Should you use time-series graphs? Density/heat-maps? You're certainly not limited in the number of visualizations you can include.
   - Should your report only be at one level of detail, or should you include a break-down by sub-geography (neighborhood, district, etc)?
1. Write proposal and develop wireframes
   * Include boxes for metrics and sample prose on wireframes
1. Develop scripts to extract data from sources and load into PostgreSQL and/or BigQuery
1. Create the structure for your Airflow pipeline and add your extract/load scripts to it
1. Deploy your pipeline to a cloud server (and document your deployment steps for _when_ -- not _if_ -- you forget them)
1. Dive deeper into data
   * Experiment and develop queries for metrics, using tools such as PGAdmin, BigQuery, or Jupyter Notebooks
   * Note useful data transformations and queries
1. Convert explorations into SQL and Python scripts to transform ingested data
1. Experiment with visualizations of metrics
1. Create "live mockup(s)" in HTML of dashboard page(s)
1. Configure a GCS
1. Convert mockup(s) to template(s)
1. Create scripts to render template(s) for dashboard page(s)

You should be regularly (_constantly and habitually_, even) checking your code into git, and adding your scripts to your pipeline for testing along the way.

## Project Requirements

* **Documentation**
  - Your project should include a README file in Markdown format.
  - Discussion of any metrics (assumptions made, etc.)
  - Discussion of the data sources (shortcomings, etc.)
* **Data**
  * Your pipeline will ingest...
    * Data that is extracted from third-party sources (APIs, data portals, etc.).
    * Data that is extracted from at least one source that updates on a monthly or more frequent basis.
    * Data that is loaded into your own cloud-based BigQuery or PostgreSQL database. For data that does not change more frequently than annually, you _may_ skip having an extract step, but in this case you _must_ clearly document the process for loading the dataset into your database.
  * Your pipeline will transform ingested data into a data model appropriate for your domain.
  * Your pipeline should be hosted on a publicly accessible cloud server (with a strong password).
  * Your pipeline should be able to run without intervention.
  * Each extract, load, and transform should be in their own separate task
  * Each task should include appropriate documentation
* **Report**
  * Your project must include dynamically generated report available through Google Cloud Storage
  * Your report must include some combination of maps, chart, and dynamically-generated text (at least one example of each)
* **Presentation**
  * You will be presenting to your stakeholders. You will demonstrate to them that you have some understanding of their decision-making needs by explaining your understanding to them, and then you will tell and show them how the reports that you’re generating for them can assist them in making their decisions.
  * Presentations should be 10 minutes or less.
  * You should mention where your data comes from, and any relevant considerations, but you should omit most technical details that wouldn't be appropriate for non-technical stakeholders.
* **Code**
  * All of your deployed code should live in a GitHub repository, which should include:
    - HTML template(s)
    - DAGs
    - SQL transformations
  * Do not check any keys or credentials into your repository!
