# Homework 6
## 1: Project Set-up
### 1.1 Using Existing Database
The documentation on the class website was giving me some problems, but I eventually got connected to the database using [this page](https://msdn.microsoft.com/en-us/library/mt710790.aspx) from the MSDN.

Following the instructions, I make two scripts.
```sql
RESTORE FILELISTONLY  
FROM DISK = 'C:\Users\user\Documents\School\2017FALL\CS460\AdventureWorks2014.bak' 
GO  
```
...to import the database through the back up files from Microsofts Github. It gives me an AdventureWorks2014_Data file and an AdventureWorks2014_Log file.
Now I can continue the back up with the following:
```sql
RESTORE DATABASE AdventureWorks
FROM DISK = 'C:\Users\user\Documents\School\2017FALL\CS460\AdventureWorks2014.bak'  
WITH MOVE 'AdventureWorks_Data' TO 'C:\Users\user\Documents\School\2017FALL\CS460\homeworks\homework6\AdventureWorks.mdf',  
MOVE 'AdventureWorks_Log' TO 'C:\Users\user\Documents\School\2017FALL\CS460\homeworks\homework6\AdventureWorks.ldf' 
```

### 1.2 Installing Scaffold Tools
[Use Microsofts tutorial for Existing Database set up,](https://docs.microsoft.com/en-us/ef/core/get-started/aspnetcore/existing-db) (but not for connecting to an existing database... that didn't go smoothly with this tutorial page), I installed all the packages I needed to use the scaffolds from the reverse engineering section.

I have to run...  
```
Install-Package Microsoft.EntityFrameworkCore.SqlServer
```
```
Install-Package Microsoft.EntityFrameworkCore.Tools
```
```
Install-Package Microsoft.VisualStudio.Web.CodeGeneration.Design
```
...to install the tools needed to use the following to set up the scaffolding.
```
Scaffold-DbContext "Server=(localdb)\mssqllocaldb;Database=AdventureWorks;Trusted_Connection=True;" Microsoft.EntityFrameworkCore.SqlServer -OutputDir Models
```
I use -Schemas Production to only take the Production tables. The microsoft document alludes to this by a 'tip' that says you can use -Tables, but I had to dig a little deeper in Enity Frameworks' documents to figure out you could also apply it to Schemas.

After this, I modify the HomeController that was made with the Project to handle all the classes.