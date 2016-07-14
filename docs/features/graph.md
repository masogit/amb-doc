# AM Browser Graph

The Graph module provides data query, statistics and visual graph features. Admin users can input AQL (Asset Manager Query Language) to query data, for those aggregation data, it is easy to configure a Graph for presenting. There are 3 types of Graph currently (Build with orinial Grommet components):

- Chart
- Meter
- Distribution

Each Grommet component has several sub types:

##### Chart

- Bar
- Line
- Area

##### Meter

- Bar
- Arc
- Circle
- Spiral

##### Distribution

### AQL data and configuration

Admin user input AQL: 

- Preview
- Load from existing AM Widgets
- Configure Graph form
- Link to a view

##### Preview

Input AQL then preview, you will see a table as the result. It should have some columns:

> It is suggested to have the first column as the group by field and the second column as count(*) or sum(<field name>).

##### Load widgets


##### Configure Graph form

- Column (mandatory)
- label (mandatory if link to view)
    - X Axis lable in Chart
    - Column units in Meter
    - Lable in Distribution
- Other properties
    - Type
    - Size
    - ...

##### Link to a view

If you click an element, a page pops up and shows record list details. There is a simple rule when you provide AQL:

###### Rules
