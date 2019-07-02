---
title: Multi-Level-Outcomes
permalink: /docs/Multi-Level-Outcomes/
---

# Reporting DB Table Schema
For the array fields and nested structs, their data are added to the database with in the table `<ItemType>_DATA`, which has the following schema

| Column     | Data Type | Description |
| ---------- | --------- | ----------- |
| DATA_UUID  | VARCHAR   | The UUID of the current item |
| DATA_XPATH | VARCHAR   | The xpath from the outcome referring to the  value |
| DATA_VALUE | VARCHAR   | The actual value of the field |

# Example Schema
Suppose we have the following schema
```
struct(name: 'Employee') { 
    field(name: 'UserName', type: 'string') 
    field(name: 'State', type: 'string', values: states) 
    field(name: 'Phone', type: 'string', multiplicity: '0..*') { 
      attribute(name: 'Type', type: 'string', values: phones) 
    }
    field(name: 'Email', type: 'string', multiplicity: '0..*') { 
      attribute(name: 'Type', type: 'string', values: emails) 
    }
    field(name: 'Department', type: 'string') 
    struct(name: 'Leave', multiplicity: '0..*') { 
      field(name: 'Type', type: 'string') 
      field(name: 'From', type: 'dateTime') 
      field(name: 'Thru', type: 'dateTime') 
      field(name: 'Notes', type: 'string') 
    }
  }
```

It could produce the following outcome
```
<Employee>
    <UserName>John Doe</UserName>
    <State>ACTIVE</State>
    <Phone Type="HOME">09123456789</Phone>
    <Phone Type="WORK">09987654321</Phone>
    <Email Type="HOME">john@doe.com</Email>
    <Email Type="WORK">johndoe@workemail.com</Email>
    <Department>Management</Department>
    <Leave>
      <Type>Vacation</Type>
      <From>2019-12-01</From>
      <Thru>2019-12-31</Thru>
      <Notes>This is a sample note</Notes>
    </Leave>
</Employee>
```

The fields `Phone`, `Email` and the all the fields in the struct `Leave` will be saved in the database like this


| DATA_UUID                            | DATA_XPATH                     | DATA_VALUE            |
| -------------------------------------| -------------------------------| --------------------- |
| b30070f4-cacb-40bf-a984-f345bf270168 | /Employee[1]/Phone[1]          | 09123456789           |
| b30070f4-cacb-40bf-a984-f345bf270168 | /Employee[1]/Phone[2]          | 09987654321           |
| b30070f4-cacb-40bf-a984-f345bf270168 | /Employee[1]/Email[1]          | john@doe.com          |
| b30070f4-cacb-40bf-a984-f345bf270168 | /Employee[1]/Email[2]          | johndoe@workemail.com | 
| b30070f4-cacb-40bf-a984-f345bf270168 | /Employee[1]/Leave[1]/Type[1]  | Vacation              |
| b30070f4-cacb-40bf-a984-f345bf270168 | /Employee[1]/Leave[1]/From[1]  | 2019-12-01            |
| b30070f4-cacb-40bf-a984-f345bf270168 | /Employee[1]/Leave[1]/Thru[1]  | 2019-12-31            |
| b30070f4-cacb-40bf-a984-f345bf270168 | /Employee[1]/Leave[1]/Notes[1] | This is a sample note |
