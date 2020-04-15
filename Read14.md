# Read14
______________

 ## Database Normalization:
 
 
 - Introduction to Database Normalization:
 
   - Database normalization is a process used to organize a database into tables and columns.
   - The main idea with this is that a table should be about a specific topic and only supporting topics included.
   - There are three normal forms most databases adhere to using.  
   
   
 - Reasons for Database Normalization:
 
 
   - There are three main reasons to normalize a database:
     1. is to minimize duplicate data
     2. is to minimize or avoid data modification issues
     3. is to simplify queries.
     
     
  - Data Duplication and Modification Anomalies:
  
  
    - Duplicated information presents two problems:
      1. It increases storage and decrease performance.
      2. It becomes more difficult to maintain data changes.
      
 - There are three modification anomalies that can occur:
    1.  - Insert Anomaly: ![link](https://www.essentialsql.com/wp-content/uploads/2014/06/Intro-Insert-Anomaly.png)
        -There are facts we cannot record until we know information for the entire row. 
    2. - Update Anomaly: ![link](https://www.essentialsql.com/wp-content/uploads/2014/06/Intro-Update-Anomaly.png)
    3. - Deletion Anomaly: ![link](https://www.essentialsql.com/wp-content/uploads/2014/06/Intro-Deletion-Anomaly-e1425554658757.png?ezimgfmt=ng:webp/ngcb2)
    
 - Search and Sort Issues:
  - <code> SELECT SalesOffice   FROM SalesStaff   WHERE Customer1 = ‘Ford’ OR      Customer2 = ‘Ford’ OR      Customer3 = ‘Ford’      </code>.
   -The process to redesign the table is database normalization.
- Definition of Database Normalization:
  - There are three common forms of database normalization: 1st, 2nd, and 3rd normal form. They are also abbreviated as 1NF, 2NF, and 3NF respectively. 
  
