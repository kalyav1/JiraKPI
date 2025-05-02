# JiraKPI
In the dynamic world of software development, maintaining a clear line of sight across the delivery lifecycle is paramount. IT managers, Scrum masters, product owners, and Agile teams alike strive for predictable releases and transparent progress. Jira, a cornerstone tool for many agile teams, offers a wealth of data that, when strategically leveraged as Key Performance Indicators (KPIs), can provide invaluable insights into delivery governance. This article delves into essential Jira KPIs
<details>
  <summary>
Fix Version
    </summary>
Within the Jira ecosystem, the Fix Version acts as a designated release milestone. Think of it as a container that groups specific work items – typically User Stories and Defects – targeted for a particular deployment or release. While Features, which often span multiple releases, are intentionally excluded from direct Fix Version assignment, the Fix Version becomes the focal point for tracking the tangible deliverables within a defined timeframe. Jira's design inherently prevents associating a single work item with multiple Fix Versions. <br> <br>
Organizations commonly establish a yearly release calendar that aligns with their Planning Intervals (PI). A typical PI often spans 6 to 7 two-week sprints, with major releases occurring at the culmination of each PI, resulting in approximately four major releases annually. Minor releases are frequently scheduled every other week. Once this release calendar is in place, the corresponding Fix Versions should be created within Jira by navigating to the project's "Releases" section and selecting "Create Fix Version," where the release name and date are then entered. It's essential that every new work item created in Jira is consistently mapped to a relevant Fix Version. Upon the completion of a release, the corresponding Fix Version should be marked as "Released" only after confirming that all associated work items have been moved to a "Done" status. Any work items that remain incomplete at the release milestone must be promptly reassigned to the Fix Version of the next scheduled release. This review and reassignment of incomplete items should be a periodic practice <br> <br>

Dashboards centered around Fix Versions provide essential visibility into several key aspects of a release. They offer a clear view of the work items planned for a specific milestone, the team's progress towards achieving it, any impediments currently blocking the release, and the status of all open defects. Furthermore, metrics such as scope changes, the burndown rate of work, the overall count and types of defects, impediments and the cycle time of work items within the release are valuable data points that make them strong contenders for insightful release retrospection meetings. <br> <br>
<details>
  <summary>
   Release Status
  
  </summary>
To visualize the release status effectively within Jira, begin by creating a specific filter. <blockQuote>Navigate to the search field, click enter, and input the query fixVersion ="" and project = "", ensuring you replace the empty quotes with the relevant Fix Version, and Project name respectively </blockQuote>. Execute the search and save it as a filter, adopting a clear naming convention like "Project name _ Milestone name _ WorkItems." Next, to display this information on a dashboard, navigate to your Jira dashboard and click the "+" sign to create a new dashboard and add a gadget to an existing one. Search for and select the "Issue Statistics" gadget. Configure this gadget by choosing the saved filter you previously created. Set the "Stats Type" to "Status," and select "Yes" for "Show resolved issue stats." Finally, set the "Refresh Interval" to 15 minutes to ensure near real-time updates and click "Save" 

</details>
<details>
  <summary>
Release defect Status
  </summary>
To gain insight into the defect status for a specific release, the process mirrors the release status setup with a refined Jira filter. <blockQuote> Begin by navigating to the Jira search field, clicking enter, and entering the query: fixVersion ="" and project = "" and issuetype in (Bug).</blockQuote> Remember to replace the empty quotes with the specific Fix Version, and Project namen. Execute this search and save it as a new filter, using a descriptive name such as "Project name _ Milestone name _ Defects." Next, to visualize this defect data on your Jira dashboard, click the "Add gadget" button. Search for and select the "Issue Statistics" gadget. When configuring the gadget, choose the defect-specific filter you just saved. Set the "Stats Type" to "Status," and ensure "Show resolved issue stats" is set to "Yes." Finally, configure the "Refresh Interval" to your desired frequency, such as 15 minutes, and click "Save" 
</details>
<details>
<summary>  Release Impediments</summary>To effectively monitor blockers within a release, you can create a dedicated Jira filter and display it on a dashboard. Start by navigating to the Jira search field and entering one of the following queries, depending on how blockers are tracked in your instance:
<br> <blockQuote> Using "Is blocked by" or "Blocks" links: fixVersion ="" and project = "" and issueLinkType in ("Is blocked by",Blocks) </blockQuote>
<br> <blockQuote> Using a "Flagged" field: fixVersion ="" and project = "" and "Flagged[Checkboxes]" = Impediment </blockQuote>
<br> Remember to replace the empty quotes with the relevant Fix Version and Project name. Execute the chosen search and save it as a filter, using a clear and consistent naming convention like "Project name _ Milestone name _ Blockers."
Once the filter is saved, navigate to your Jira dashboard and click the "Add gadget" button. Search for and select the "Issue Statistics" gadget. Configure this gadget by selecting the blocker-specific filter you just created. Set the "Stats Type" to "Status," and ensure "Show resolved issue stats" is set to "Yes." Finally, set your desired "Refresh Interval," such as 15 minutes, and click "Save" 

</details>
<details>
<summary>Release Dependencies</summary>
To effectively track dependencies related to a specific release, you'll need to create a dedicated Jira filter and then display it using a different gadget type for a more detailed view. <blockQuote>First, navigate to the Jira search field and enter the following query: fixVersion ="" and project = "" and issueLinkType in (Dependency,Predecessors, Successors). </blockQuote>Make sure to replace the empty quotes with the relevant Fix Version and Project name. Execute this search and save it as a filter, using a clear name like "Project name _ Milestone name _ Dependencies."
Next, to visualize these dependencies on your Jira dashboard, click the "Add gadget" button. This time, search for and select the "Filter Results" gadget. When configuring this gadget, select the dependency-specific filter you just saved. In the configuration options, specify the "Fields to display" as: Issue Type, Key, Summary, and Linked Issues. Finally, set your desired "Refresh Interval," such as 15 minutes, and click "Save

  
</details>
<details>
  <summary>
    Version Report

  </summary>
  To gain a high-level overview of a release's progress and any scope changes, Jira's built-in Version Report gadget is invaluable. <blockQuote> To add this to your dashboard, click the "Add gadget" button and search for "Version Report." Once found, select it.</blockQuote> In the configuration settings, you'll need to specify the Board Name associated with your project and then select the specific Version Name (which corresponds to your Fix Version). Finally, set the Refresh Interval to your desired frequency, such as 15 minutes, to ensure the report stays up-to-date, and then click "Save." This gadget will provide a visual representation of the scope changes within the release and the progress being made towards the defined milestone date, offering a quick and easy way to track overall release health 

</details>
<details>
  <summary>
      Backlog Health
  </summary>
To visualize the distribution of work across future sprints and gain insights into backlog health, you can use the "Filter Results" gadget on your Jira dashboard. <blockQuote>Navigate to Jira Search and type query Project = "" and fixVersion =""  AND Sprint in futureSprints() and Sprint not in closedSprints() and issueType in (Bug, Story).</blockQuote> Sprint not in closedSprints(), excludes the stories that were carried over. Remember to replace the empty quotes with your project's name, fixversion. Save filter as "Projectname_Milestonename_BacklogHealth". Click the "Add gadget" button and search for "Filter Results." Once selected, in the configuration, choose the saved filter, select Sprint, Story Point/Estimate additional columns, select refresh interval as 15 mins and click save. Work items with sum estimates matching average velocity of the team for the next 2 or 3 Sprints is a sign of healthy backlog 

</details>

</details>
<details>
  <summary>
      Created vs Resolved chart
  </summary>
The Created vs. Resolved chart provides a visual representation of the team's delivery rate within the Kanban framework. This data can be utilized to forecast future capacity and inform workload management <blockQuote>Navigate to Jira Search and type query Project = "" and issueType in (Bug, Story).</blockQuote> Remember to replace the empty quotes with your project's name. Save filter as "Projectname_WorkItems". Click the "Add gadget" button and search for "Created vs resolved chart" Once selected, in the configuration, choose the saved filter,  select refresh interval as 15 mins and click save.  

</details>
<details>
  <summary>
    Retrospection
  </summary>
  KPI driven retrospection can help improve productivity. <li>Defect Gadget gives insight into Total defects & Defect priority. While finding defects early in the cycle helps deliver stable product, too many defects takes away time from productive development. Context switching & retesting efforts are often costly</li> <li>Version report gadget-Provides visibility in to scope changes, any deviation from milestone date, and rate of progression towards the milestone date</li> <li>Backlog Health gadget-Helps identify any challenges with the planning part of the delivery funnel. Some of the corrective actions would be relooking at the staffing for the planning team(US, POs, BAs, SAs) or it need for additional grooming ceremonies</li><li>Velocity Chart-Provides insights in to say to do commitment. Predictable velocity and near perfect say to do ratio is a sign of well formed Scrum team </li><li>Release dependencies & Impediments Gadgets-Provides visibility in to challenges faced by the scrum team. This provides the team Opportunity to find improvements in addition to Scrum of Scrum/ART Sync </li>
</details>

