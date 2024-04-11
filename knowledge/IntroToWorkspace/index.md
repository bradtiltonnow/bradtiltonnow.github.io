# Intro to Workspace Lab

## Instance Setup

- PDI on Washington DC
- Plugins/Store Apps
  - Install: Agent Workspace for HR Case Management - sn_hr_agent_ws v3.0.1
  - Update: UI Builder – sn_ui_builder v25.1.26

## Lab: Duplicate the Variant for landing page and add a data viz for HR

As an Administrator working for a ServiceNow customer or partner, you might often be asked to perform several modifications to OOB ServiceNow Workspaces. We are going to walk through several changes you can easily perform to a workspace, using the HR Agent Workspace as our first example.

The default landing page greets the user at the top and provides the time, along with a heading describing what the user is seeing. There is an Overview section and a section showing Open items for my Team. We have received a few requests for modifications from the HR team:

- Move the Open Items section from the bottom to above the Overview section
- Remove the background image from the header
- Add a Data Visualization to the header to show “My Cases”

We will walk through the steps required to make these modifications.

1. Navigate to HR Agent workspace by going to the Unified Navigator menu, clicking on the “Workspaces” drop-down menu, and clicking on “HR Agent Workspace”.
2. Here you can see the default landing page. Take a quick moment to familiarize yourself with the different sections and the requirements we have been given above.
3. Navigate to the top left corner of the filter navigator and click on “All” to open the All menu. Type “UI Builder” and click on the “UI Builder” menu item under the “Now Experience Framework” application menu.
4. Once UI Builder loads in a new tab, sort the workspace experiences alphabetically and locate then click on “HR Agent Workspace”.
5. This is the Experience Editor view of UI Builder. If you are unfamiliar, take a moment to look at the different elements of UI Builder and familiarize yourself with them.
    1. In the top left corner, there is a blue and green icon. If you click on this, it will take you back to the all experiences view.
    2. Next to that is the title of the experience we are currently in, HR Agent Workspace. Clicking on this will bring you back to the current page, where you see the Pages and Variants for the HR Agent Workspace.
    3. Next to that you can switch between the Editor and Settings views.
    4. To the right, the first drop down is going to be the Application Scope selector. This is where we will select what Application Scope we are going to be working on in a few steps.
    5. The last two buttons are good for you to click on and navigate when you have a moment. What’s new will show you anything newly released within UI Builder, and the Help button contains links to useful documentation for when you get stuck.
    6. Below the HR Agent Workspace heading, you’ll find a menu detailing specific aspects of the experience we are currently in. You’ll see the URL Path, Application Scope, App shell, and what roles are required to view it.
    7. Under “Pages and variants” you’ll find a long list with grouped items. Each gray heading is a Page in the experience, and each item under the gray heading is a variant of that page. Typically, most pages will have a “Default” page, and any variants will be listed below. Note that the variants of each page share a URL path, but the order column is what determines which shows up by default. The lowest number is the variant that shows by default, and any others below don’t show up. The next two columns govern what shows up for different users and roles. At the end of the list, you have quick access to open variants in the editor or to view the settings for the variants. You can’t edit the order, audiences, or conditions from this list view, but you can from the settings pages which we will cover later.
6. At the top of the list under “Pages and Variants” you’ll see the Landing Page, which can also be identified by the yellow “Landing page” tag. Click on the “Landing page default” variant.
7. Before you start any work, it’s important that you always make sure you are in the correct application scope. In the top right corner, select the Application Scope drop-down menu and switch to the “Agent Workspace for HR Case Management” scope.
8. Let’s take a moment to familiarize ourselves with the UI Builder variant editor view.
    1. Below the menus we’ve already covered, you might see two blue bars telling you that this variant is Read Only, and that you can’t edit this variant. This is by design, as any OOB pages and variants will be Read Only by default. You must duplicate a variant to be able to make modifications to it. This is also where you would see a message telling you that you are in the wrong scope to edit a variant if that were the case.
    2. The next menu bar that you see will contain a hamburger menu (three horizontal lines) in the top left, providing you quick links to Duplicate a variant and other useful developer options/links. If you were on a page that had any URL parameters, you would be able to input test data for them next to this menu bar.
    3. There is also a setting to change the width of the variant preview below, as well as some handy options in the top right. We’ve got an undo and redo button, a preview button, and a save button. We will go over the preview button later, but for now, don’t forget where the save button is – it’s super useful!
    4. Below that menu bar, you have the three main sections of UI Builder.
        1. Component tree: The component tree is split into two sections. You’ve got the Overlays section at the top that contains any modals, modeless dialogs and popovers that are in the page. Then you’ve got the Body section, which encompasses everything you see on the page variant. There are containers and components within containers among many other things. If you notice any with a crossed-out eye, that means that they are currently not visible and are being hidden by a condition. You can tell that it gets a bit cluttered and confusing, so we always suggest you rename your containers and components to maintain ease of use and clarity. We’ll go over how to do this later.
        2. Data and scripts: This section has been changed as of Washington. It is now resizable and contains all your Data Resources, Client Scripts, and Client State Parameters. If you click on any of these, a new modeless dialog box will pop up and allow you to work on the item you selected while being much more flexible than it used to be. Now you can move it around, resize it as needed, and then close it when you are done working on it.
        3. Preview panel: The page variant itself is displayed here, reflecting what it might look like when browsed by an end user. If you have test data in your URL parameters setting, then the page preview might change accordingly. 
9. In the top left corner, click the hamburger menu then click “Duplicate variant”. Let’s quickly explain what you are looking at:
    1. Audiences: These are representations of groups of users in your organizations. These let you define who has access to these pages, If you leave it blank anyone with access to the page will have access to the variant. [Learn more about audiences here.](https://docs.servicenow.com/bundle/washingtondc-application-development/page/administer/ui-builder/concept/add-audiences.html)
    2. Conditions: These can be used to determine when a page variant is shown. Conditions are based on adding a query string that sets the criteria that must be met for the page variant to display. [Learn more about conditions here](https://docs.servicenow.com/bundle/tokyo-application-development/page/administer/ui-builder/task/edit-page-conditions.html).
10. Rename the variant to “K24 Lab Landing Page” and click “Continue”.
11. With Washington, the page preview has gotten a lot more interactive. Hover your mouse above the “Open items for my team” section and click on the “Open items container”. Click and hold, then drag the container above the “Overview container”.
    1. Alternatively, you can also drag and drop items in the Component tree itself. Locate the “Open items container” in the list, collapse the “Overview container” above it by clicking on the arrow to the left, and then click, drag & drop the “Open items container” heading above the “Overview container”. You will see the preview to the right update in real time when you let go of the heading.
    2. The remaining steps will assume that you have chosen to navigate this page using the Content tree, but you can navigate using the preview pane if you wish to.
12. Scroll up to the top of the content tree and select the “Header Container”. The Component configuration panel will update to show this container’s properties. Scroll down to the bottom and under “Background” click on the three dots with a blue box containing the number “4” hovering above it. Here you will see the expanded background options, where you will remove the image information by selecting and erasing the entire text inside the “image” box. Alternatively, you can click on the trash can in the original “Background” section of the Component configuration panel.
13. In the top right corner, click on the “Save” button. You’ll want to get into the habit of doing this routinely to safeguard your progress.
14. Next to the “save” button is the “Preview” button with a dropdown arrow. The dropdown opens to show you the “Open URL path” option. If you click on Preview, a modal will pop up that shows you a rendered preview of the current variant you are editing. This allows you to preview the variant you are currently on without having to impersonate a user who has access to see it via audiences and conditions. Alternatively, if you click on the dropdown arrow and select “Open URL path” – this will display the variant that the user you are logged in as would see according to audiences, conditions, and the order of the variants.
    1. If you go to the settings menu in the top center of the page, you will see in the top left all the page variants for your page and what order they are in. The left menu reflects the order of variants, and according to any conditions or audiences that may be applied, they will generally be shown to you in top-to-bottom order. If your users can’t see a specific variant, make sure to verify all conditions and audiences are met, as well as that the variant in question is the one at the top of the list from the variants they have access to.
15. Right now, all of the variants are listed at order 0 since we just duplicated them. Go ahead and set your K24 Lab Variant to order 10 and set the “Landing page default” variant to be order 100. This will ensure that when you click “Open URL path”, the variant you see is the variant we are editing.
16. Click back to the “Editor” view of UI Builder, we are going to replace the Header container with a new Columns layout component to fulfill the rest of the requirements.
17. To add the Columns layout component, right-click the “Header container” and select “Add before”. A pop-up will appear listing out Layouts and Components. If you click on the “Layouts” tab at the top left of the pop-up, it displays several different layout configurations you can pick from. Select the “Three columns” configuration. You will now see that a “Column layout 1” component was added above the “Header container” in both the preview and the Component tree panel.
18. At the very top of the Component configuration panel, you will see the Name and ID of the component we’ve selected. Make sure you’ve got the “Column layout 1” selected, then click on the little (i) icon next to the component name. This will show the pop-up where you can set the Component’s Label and ID. It’s always a good idea to rename your components so they are easier to identify in the future, you don’t want to come back 3 months later to a mess of Column 1 2 and 3s, along with Stylized texts 3, 4, 7 and then wonder what anything is. Rename this column layout to “Header column layout” and set the id to “header_column_layout”.
19. Click and drag the “Sidebar 1” container from the old “Header Container” to our new column layout under “Column 1”.
20. Click and drag the “Main” container from the old “Header Container” to our new column layout under “Column 2”.
21. Now that the old Header Container is empty, right-click it from the component tree panel and click “Delete”.
22. **Now we will be making a few modifications to the column layout component and the columns inside.**
    1. Click on the “Header column layout”. Add 40px padding to column layout, make background white. Change width to 100%, remove padding.
    2. Adjust the “User Greetings” stylized text component. You’ll see it’s currently populated by a Client State Parameter, we’re going to change this using the Visual Data Binding formulas.
        1. Click on the input box below “Text” and it will show the “Bind data to Text” window.
        2. On the left side, click on “Formulas”.
        3. Click the X next to the data pill at the top of the modal box.
        4. Click the up arrow next to “CONCAT”.
        5. Inside the formula at the top, click on “values” and type: “Hello and Welcome “ (include the space at the end)
        6. Click on the second “values” box.
        7. Click “Data Types” on the left
        8. Go to “Page properties”, click on “Session”, click on “user”, click on “firstName” then click the up arrow that appears to add it to the formula builder.
        9. Click Apply
    3. Under the “Main” container in the content tree, move “Date and Time” component below “User greetings” component.
    4. Change width of “Main” container to 25%
23. In the last column, Add data visualization component.
    1. Semi donut
    2. Chart title: My items
    3. Add data source
        1. Source: table, HR case \[sn_hr_core_case\]
        2. Add custom condition
            1. Field: Assigned to
            2. Operator: is (dynamic)
            3. Value: Me
    4. Metric leave at hr case count
    5. Group by state (enable: show other, enable: hide elements w/0 values)
    6. Under “No data message”, Set custom message when no data. “No more work!”
    7. Change color palette to a fun color.
24. Good job you’re done!
