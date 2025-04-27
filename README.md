# JiraKPI
> In the dynamic world of software development, maintaining a clear line of sight across the delivery lifecycle is paramount. Project managers, product owners, and development teams alike strive for predictable releases and transparent progress. Jira, a cornerstone tool for many agile teams, offers a wealth of data that, when strategically leveraged as Key Performance Indicators (KPIs), can provide invaluable insights into delivery governance. This article delves into essential Jira KPIs
<details>
  <summary>
Fix Version
    </summary>
Within the Jira ecosystem, the Fix Version acts as a designated release milestone. Think of it as a container that groups specific work items – typically User Stories and Defects – targeted for a particular deployment or release. While Features, which often span multiple releases, are intentionally excluded from direct Fix Version assignment, the Fix Version becomes the focal point for tracking the tangible deliverables within a defined timeframe. Jira's design inherently prevents associating a single work item with multiple Fix Versions. <br> <br>
Organizations commonly establish a yearly release calendar that aligns with their Planning Intervals (PI). A typical PI often spans 6 to 7 two-week sprints, with major releases occurring at the culmination of each PI, resulting in approximately four major releases annually. Minor releases are frequently scheduled every other week. Once this release calendar is in place, the corresponding Fix Versions should be created within Jira by navigating to the project's "Releases" section and selecting "Create Fix Version," where the release name and date are then entered. It's essential that every new work item created in Jira is consistently mapped to a relevant Fix Version. Upon the completion of a release, the corresponding Fix Version should be marked as "Released" only after confirming that all associated work items have been moved to a "Done" status. Any work items that remain incomplete at the release milestone must be promptly reassigned to the Fix Version of the next scheduled release. This review and reassignment of incomplete items should be a periodic practice <br> <br>

Dashboards centered around Fix Versions provide essential visibility into several key aspects of a release. They offer a clear view of the work items planned for a specific milestone, the team's progress towards achieving it, any impediments currently blocking the release, and the status of all open defects. Furthermore, metrics such as scope changes, the burndown rate of work, the overall count and types of defects, impediments and the cycle time of work items within the release are valuable data points that make them strong contenders for insightful release retrospection meetings. <br> <br>
<details>
<br> <br>
  <summary>
   Release Status
  
  </summary>
To visualize the release status effectively within Jira, begin by creating a specific filter. Navigate to the search field, click enter, and input the query fixVersion ="" and project = "", ensuring you replace the empty quotes with the relevant Fix Version, and Project name respectively. Execute the search and save it as a filter, adopting a clear naming convention like "Project name _ Milestone name _ WorkItems." Next, to display this information on a dashboard, navigate to your Jira dashboard and click the "+" sign to create a new dashboard and add a gadget to an existing one. Search for and select the "Issue Statistics" gadget. Configure this gadget by choosing the saved filter you previously created. Set the "Stats Type" to "Status," and select "Yes" for "Show resolved issue stats." Finally, set the "Refresh Interval" to 15 minutes to ensure near real-time updates and click "Save" 

</details>
<details>
  <summary>
Release defect Status
  </summary>
To gain insight into the defect status for a specific release, the process mirrors the release status setup with a refined Jira filter. Begin by navigating to the Jira search field, clicking enter, and entering the query: fixVersion ="" and project = "" and issuetype in (Bug). Remember to replace the empty quotes with the specific Fix Version, and Project namen. Execute this search and save it as a new filter, using a descriptive name such as "Project name _ Milestone name _ Defects." Next, to visualize this defect data on your Jira dashboard, click the "Add gadget" button. Search for and select the "Issue Statistics" gadget. When configuring the gadget, choose the defect-specific filter you just saved. Set the "Stats Type" to "Status," and ensure "Show resolved issue stats" is set to "Yes." Finally, configure the "Refresh Interval" to your desired frequency, such as 15 minutes, and click "Save" 
</details>
<details>
<summary>  Release Impediments</summary>To effectively monitor blockers within a release, you can create a dedicated Jira filter and display it on a dashboard. Start by navigating to the Jira search field and entering one of the following queries, depending on how blockers are tracked in your instance:
<br> <blockQuote> Using "Is blocked by" or "Blocks" links: fixVersion ="" and project = "" and issueLinkType in ("Is blocked by",Blocks) </blockQuote>
<br> Using a "Flagged" field: fixVersion ="" and project = "" and "Flagged[Checkboxes]" = Impediment
<br> Remember to replace the empty quotes with the relevant Fix Version and Project name. Execute the chosen search and save it as a filter, using a clear and consistent naming convention like "Project name _ Milestone name _ Blockers."
Once the filter is saved, navigate to your Jira dashboard and click the "Add gadget" button. Search for and select the "Issue Statistics" gadget. Configure this gadget by selecting the blocker-specific filter you just created. Set the "Stats Type" to "Status," and ensure "Show resolved issue stats" is set to "Yes." Finally, set your desired "Refresh Interval," such as 15 minutes, and click "Save" 

</details>
</details>

