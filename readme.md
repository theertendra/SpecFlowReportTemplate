# How to customize SpecFlow Report

This is a example how to create a specflow report and configure to use in the project

Refer to the documentation [here](http://www.specflow.org/plus/documentation/Tutorial:-Customising-Reports) for an explanation of how the screenshot's path is passed to the report.


## Configuration

1. Create a **Report** folder in the project
2. Copy the newly created .cshtml into the **Report** folder
3. Open default srprofile file from visual studio. And under report provide the path of new cshtml file. Please find the below example
   ```
    <Report>
       <Template name="Report\ReportTemplate.cshtml"/>
    </Report>
   ```

## Specflow Report file

Complete Specflow report has been segregated in to different tabs. Please find the below code snippet used in html file.

```
    <div class="tab">
        <button class="tablinks" onclick="openTab(event, 'Dashboard')" id="defaultOpen">Dashboard</button>
        <button class="tablinks" onclick="openTab(event, 'Summary')">Summary</button>
        <button class="tablinks" onclick="openTab(event, 'ErrDetails')">Error Details</button>
        <button class="tablinks" onclick="openTab(event, 'ScenSummary')">Scenario Summary</button>
        <button class="tablinks" onclick="openTab(event, 'ScenDetails')">Scenario Details</button>
        <button class="tablinks" onclick="openTab(event, 'TimeLine')">Time Line</button>
    </div>
```

Java Script to open a tab

```
<script>
                function openTab(evt, tabName) {
                    var i, tabcontent, tablinks;
                    tabcontent = document.getElementsByClassName("tabcontent");
                    for (i = 0; i < tabcontent.length; i++) {
                        tabcontent[i].style.display = "none";
                    }
                    tablinks = document.getElementsByClassName("tablinks");
                    for (i = 0; i < tablinks.length; i++) {
                        tablinks[i].className = tablinks[i].className.replace(" active", "");
                    }
                    document.getElementById(tabName).style.display = "block";
                    evt.currentTarget.className += " active";
                }

                // Get the element with id="defaultOpen" and click on it
                document.getElementById("defaultOpen").click();
            </script>
```

Details which need to be published under each tab is under div with **class="tabcontent"**

please find the below example
```
  <div id="Dashboard" class="tabcontent">
```

