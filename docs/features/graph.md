# AM Browser Graph

Graph module provide data query, statistics and visual graph features. Admin user input AQL (Asset Manager Query Language) to query data, for those aggregation data, it's easy to configure a kind of Graph to present. There are 3 types of Graph currently (Build with orinial Grommet components):

- Chart
- Meter
- Distribution

Each Grommet component have several sub types:

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

Admin user input AQL 

- Preview
- Load from existing AM In Tool Reports (Widgets)
- Configure Graph form
- Link to a view

##### Preview

Input AQL then preview, you will see a table as result. It should have some columns:

> Prefer first column is group by field, second column is count(*) or sum(<field name>)

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

Graph supports click each element, then popup a page to get record list details. There is a simple rule when you provide AQL:

###### Rules
