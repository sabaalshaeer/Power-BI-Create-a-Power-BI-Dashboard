# Power-BI-Create-a-Power-BI-Dashboard
Exercise 1: Create a Dashboard
In this exercise you will create the Sales Monitoring dashboard. The completed dashboard will look like the following:

Image of the completed dashboard, comprising three tiles.

Task 1: Get started – Sign in
In this task you will setup the environment for the lab by signing in to Power BI.

Important: If you have already signed in to Power BI in a previous lab, continue from the next task.

To open Microsoft Edge, on the taskbar, click the Microsoft Edge program shortcut.

Picture 42

In the Microsoft Edge browser window, navigate to https://powerbi.microsoft.com.

Tip: You can also use the Power BI Service favorite on the Microsoft Edge favorites bar.

Click Sign In (located at the top-right corner).

Picture 41

Enter the account details provided to you.

If prompted to update the password, reenter the provided password, and then enter and confirm a new password.

Important: Be sure to record your new password.

Complete the sign in process.

If prompted by Microsoft Edge to stay signed in, click Yes.

In the Microsoft Edge browser window, in the Power BI service, in the Navigation pane, expand My Workspace.

Picture 40

Leave the Microsoft Edge browser window open.

Task 2: Get started – Open report
In this task you will setup the environment for the lab by opening the starter report.

Important: If you are continuing on from the previous lab (and you completed that lab successfully), do not complete this task; instead, continue from the next task.

To open the Power BI Desktop, on the taskbar, click the Microsoft Power BI Desktop shortcut.

Picture 39

To close the getting started window, at the top-left of the window, click X.

Picture 38

If Power BI Desktop is not signed in to the Power BI service, at the top-right, click Sign In.

Picture 37

Complete the sign in process using the same account used to sign in to the Power BI service.

To open the starter Power BI Desktop file, click the File ribbon tab to open the backstage view.

Select Open Report.

Picture 36

Click Browse Reports.

Picture 34

In the Open window, navigate to the D:\PL300\Labs\08-create-power-bi-dashboard\Starter folder.

Select the Sales Analysis file.

Click Open.

Picture 32

Close any informational windows that may open.

To create a copy of the file, click the File ribbon tab to open the backstage view.

Select Save As.

Picture 29

If prompted to apply changes, click Apply.

Picture 10

In the Save As window, navigate to the D:\PL300\MySolution folder.

Click Save.

Picture 9

Task 3: Get started – Publish the report
In this task you will setup the environment for the lab by creating a dataset.

Important: If you have already published the report in the Design a Report in Power BI Desktop, Part 2 lab, continue from the next task.

In the Microsoft Edge browser window, in the Power BI service, in the Navigation pane, at the bottom, click Get Data.

Picture 8

In the Files tile, click Get.

Picture 2

Click the Local File tile.

Picture 5

In the Open window, navigate to the D:\PL300\Labs\08-create-power-bi-dashboard\Solution folder.

Select the Sales Analysis.pbix file, and then click Open.

If prompted to replace the dataset, click Replace it.

Task 4: Create a dashboard
In this task you will create the Sales Monitoring dashboard. You will pin a visual from the report, and add a tile based on an image data URI, and use Q&A to create a tile.

In the Microsoft Edge browser window, in the Power BI service, open the Sales Analysis report.

In the Overview page, set the Year slicer to FY2020.

Picture 4

Set the Region slicer to Select All.

When pinning visuals to a dashboard, they will use the current filter context. Once pinned, the filter context cannot be changed. For time-based filters, it’s a better idea to use a relative date slicer (or, Q&A using a relative time-based question).

To create a dashboard and pin a visual, hover the cursor over the Sales and Profit Margin by Month (column/line) visual.

At the bottom-right corner, click the pushpin.

Picture 43

In the Pin to Dashboard window, in the Dashboard Name box, enter Sales Monitoring.

Picture 3

Click Pin.

Picture 1

Open the Navigation pane, select My Workspace and then open the Sales Monitoring dashboard.

Picture 44

Notice that the dashboard has a single tile.

Picture 45

To add a tile based on a question, at the top-left of the dashboard, click Ask a Question About Your Data.

Picture 7

You can use the Q&A feature to ask a question, and Power BI will respond will a visual.

Click any one of the suggested questions beneath the Q&A box, in blue boxes.

Review the response.

Remove all text from the Q&A box.

In the Q&A box, enter the following: Sales YTD

Picture 11

Notice the response of (Blank).

Picture 14

You may recall you added the Sales YTD measure in the Create DAX Calculations in Power BI Desktop, Part 2 lab. This measure is a Time Intelligence expression and it so requires a filter on the Date table to produce a result.

Extend the question with: in year FY2020.

Picture 12

Notice the response is now $33M.

Picture 13

To pin the response to the dashboard, at the top-right corner, click Pin Visual.

Picture 15

When prompted to pin the tile to the dashboard, click Pin.

Picture 17

To return to the dashboard, at the top-left corner, click Exit Q&A.

Picture 16

To add the company logo, on the menu bar, click Edit, and then select Add a Tile.

Picture 46

Using this technique to add a dashboard tile lets you embellish your dashboard with media, including web content, images, richly-formatted text boxes, and video (using YouTube or Vimeo links).

In the Add a Tile pane (located at the right), select the Image tile.

Picture 47

Click Next.

Picture 48

In the Add Image Tile pane, in the URL box, enter the complete URL found in the D:\PL300\Resources\AdventureWorksLogo_DataURL.txt file.

You can embed an image by using its URL, or you can use a data URL, which embeds content inline.

At the bottom of the pane, click Apply.

Picture 49

To resize the logo tile, drag the bottom-right corner, and resize the tile to become one unit wide, and two units high.

Tile sizes are constrained into a rectangular shape. It’s only possible to resize into multiples of the rectangular shape.

Organize the tiles so that the logo appears at the top-left, with the Sales YTD tile beneath it, and the Sales, Profit Margin tile at the right.

Picture 52

Task 5: Edit tile details
In this task you will edit the details of two tiles.

Hover the cursor over the Sales YTD tile, and then at the top-right of the tile, click the ellipsis, and then select Edit Details.

Picture 50

In the Tile Details pane (located at the right), in the Subtitle box, enter FY2020.

Picture 19

Click Apply.

Picture 20

Notice that the Sales YTD tile displays a subtitle.

Picture 21

Edit the tile details for the Sales, Profit Margin tile.

In the Tile Details pane, in the Functionality section, check Display Last Refresh Time.

Picture 22

Click Apply.

Picture 23

Notice that the tile describes the last refresh time (which done when loading the data model in Power BI Desktop).

You’ll refresh the dataset in the next exercise. Typically, this would be achieved by using scheduled refresh, in which case Power BI would use a gateway to connect to the SQL Server database. However, due to constraints in the classroom setup, there is no gateway. So, you’ll open Power BI Desktop, perform a manual data refresh, and then upload the file to your workspace.

Exercise 2: Refresh the Dataset
In this exercise you will first load sales order data for June 2020 into the AdventureWorksDW2020 database. You will then open your Power BI Desktop file, perform a data refresh, and then upload the file to your workspace.

Task 1: Update the lab database
In this task you will run a PowerShell script to update data in the AdventureWorksDW2020 database.

In File Explorer, inside the D:\PL300\Setup folder, right-click the UpdateDatabase-2-AddSales.ps1 file, and then select Run with PowerShell.

Picture 28

If prompted to change the execution policy, press A.

When prompted to press any key to close, press Enter again.

The AdventureWorksDW2020 database now includes sales orders made in June 2020.

Task 2: Refresh the Power BI Desktop file
In this task you will open the Sales Analysis Power BI Desktop file, perform a data refresh, and then upload the file to your Sales Analysis workspace.

In Power BI Desktop file, in the Fields pane, right-click the Sales table, and then select Refresh Data.

Picture 55

When the refresh completes, save the Power BI Desktop file.

To publish the file to your workspace, on the Home ribbon tab, from inside the Share group, click Publish and then click Select to publish.

Picture 59

When prompted to replace the dataset, click Replace.

Picture 31

The dataset in the Power BI service now has June 2020 sales data.

Close Power BI Desktop.

Exercise 3: Review the Dashboard
In this exercise you will review the dashboard to notice updated sales.

Task 1: Review the dashboard
In this task you will review the dashboard to notice updated sales.

In the Microsoft Edge browser window, in the Power BI service, review the Sales Monitoring dashboard.

In the Sales, Profit Margin tile, in the subtitle, notice that the data was refreshed NOW.

Notice also that there is now a column for 2020 Jun.

If you don’t see the June 2020 data, you might need to press F5 to reload the web browser.

Picture 33
