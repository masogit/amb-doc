# AM Browser Viewer

Views created by Admin are displayed in the Viewer module. 
Power user can access views from the Viewer module, Guest user can access a view from URL.

User can access a view and then query data from AM REST service. Below are areas in Views:
- Header
- Menu
- Table
- Detail and links

### Header
- Title
- Search and filter box
    - Quick search
        - Input without pressing enter: Filter from front-end records
        - Input by pressing enter: Filter from back-end (**View must have defined searchable fields**)
    - Advanced search (Input AQL filters)
        - Enable or disable toggle from menu
        - Enable or disable toggle by input '/' as first character
        - Display added AQL filters below the input box

        Sample: `Name like '%ABC%' or AssetTag like'123ABC%'`

- Record number and return time
    - Records number
        - Number of current of front-end records
        - Total number of back-end records
        - **Click to get the data on the next page (30 records)**
    - REST return time

> For some reason you may click records numbers to get next page data instead of scroll to end 

### Menu
- Filter menu: Group by and filters
- Vertical / horizontal Graph toggle
- AQL enable toggle
- Full column toggle
- Export and download
    - Download in background
    - Default download manager of browsers (IE, FF, Chrome...)

> In viewer, you may easy to select a field as group by condition, then see the aggregation results.
Each result item can be clicked as a filter, after click, filter will display on top of record list.

### Table
- Header: Fields name and order by
    - Fields name will display alias name (that defined in view) instead of fields' original label.
    - Clicking fields name will display ascent or descend icon, and query records from back end.
- Column
    - By default, 5 columns are displayed.
    - Click a record to show detail.

If you scroll down to the bottom, it automatically gets the data of the next page.


![Viewer screen shot](img/viewer1.png)

### Detail
When a user clicks a record, there will be a popup window from the right side. In this window, all fields defined in view will be displayed vertically.
And all 1-M links defined in the view will be displayed as a Tab page.
- Display all fields
- Display sub links

![Viewer screen shot](img/detail1.png)

### Distribution
AM Browser Viewer provides a colorful and bright distribution graph to display group by statistics. It also provides a fast group by and filter functions. 

- Distribution Graph
    - Horizontal (default)
    - Vertical (enable from menu)
    - Allow to click each element as a filter
- Group by
    - Default group by field defined in view
    - Select a field from filter menu manually
- Filter
    - Display AQL filters that added by user
    - Allow to multiple filters, condition is 'AND'

Video:

[![Filter video](http://img.youtube.com/vi/2_Cn7692HHk/0.jpg)](http://www.youtube.com/watch?v=2_Cn7692HHk "Group and Filter")