# AM Browser View Builder

AMB View is a lightweight AM data present layout, Admin users may create and manage view in AMB Builder. Power users may query all views in AMB Viewer. Guests access a view via a URL that shared by Admin users.

A view is created from AM schema (raw table),  and a view only have a root table. All fields or links are related from root table.  

### Fields and Links
Fields and links are selected from AMB Build Schema. When a root table is selected, it can not be changed. Fields and links are split into 3 groups:

- 1-M Links
- 1-1 Links
- Fields

All fields or 1-1 link's fields will be added in same link. When query data from this view. These fields will query and display together. For example:

```
Root table: 
        amComputer
Fields:
        CPUType
        Portfolio.seAssigment
        Portfolio.Model.Name
        Portfolio.Brand.Name
```

When fields in 1-M Links are selected, there is a new link be created. For example:

```
1-M link:
        PhysicalDrivers
Field:
        lTotalSizeMb
```
```
1-M link:
        Portfolio.Softs
Field:
        Folder
        Model.Name
        Model.Brand.Name
```

### Functions

Below functions are scoped in one link

- Searchable
    - Only 2 fields in a link can be set searchable
    - Prent enter in viewer search box, it will generate AQL filters to query data on this field
    - The searchable fields of root table will be search in Global Search
- Group by
    - Set default group by field, it will show group by graph when query in viewer
- Sum
    - If a field set group by, it allows select a number field to sum
- Order by
    - Set a field as order by field
- Set alias
    - Set Alias name replace label to display in viewer
- Filter
    - Specify AQL filter condition when query data
- Sort fileds
    - Adjust fields display order

### Others

- Click each link title, AM schema sidebar will address to table directly.
- Export view definition as json file.
- Share a view with guest users by send a URL in mail.
