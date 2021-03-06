# Get-SQLDiagLatestCU

### SYNOPSIS
Gets The Latest Cumulative Updates and Date from the SQL Server Diagnostic API

### DESCRIPTION
Returns Product Name, Cumulative Update Name and Date created from the SQL Server Diagnostic API
Opens the Learn More webpage with the LearnMore switch
Downloads the CU with the Download Switch

### PARAMETER Recommendations
The recommendation object from the API - Use Get-SQLDiagRecommendations by default

### PARAMETER Product
The product or products that you want to filter by Get-SQLDiagProduct will show the options

### PARAMETER LearnMore
Opens the Information web-page for the Cumulative Update for the product specified in the default browser

### PARAMETER Download
Opens the Download page for the Cumulative Update for the product specified in the default browser

### EXAMPLE
Get-SQLDiagLatestCU

Returns Product Name, Cumulative Update Name and Date created for all products from the SQL Server Diagnostic API

### EXAMPLE
Get-SQLDiagRecommendations | Get-SQLDiagLatestCU

Returns Product Name, Cumulative Update Name and Date created for all products from the SQL Server Diagnostic API

### EXAMPLE
Get-SQLDiagLatestCU -Recommendations (Get-SQLDiagRecommendations)

Returns Product Name, Cumulative Update Name and Date created for all products from the SQL Server Diagnostic API

### EXAMPLE
Get-SQLDiagProduct 2012 | Get-SQLDiagLatestCU

Returns Product Name, Cumulative Update Name and Date created for products named 2012 from the SQL Server Diagnostic API

### EXAMPLE
Get-SQLDiagLatestCU -Product 'SQL Server 2012 SP3'

Returns Product Name, Cumulative Update Name and Date created for SQL Server 2012 SP3 from the SQL Server Diagnostic API

### EXAMPLE
Get-SQLDiagLatestCU -Product 'SQL Server 2012 SP3','SQL Server 2014 SP1'

Returns Product Name, Cumulative Update Name and Date created for SQL Server 2012 SP3 and SQL Server 2014 SP1 from the 
SQL Server Diagnostic API

### EXAMPLE
Get-SQLDiagLatestCU -Product 'SQL Server 2012 SP3' -LearnMore

Opens the Cumulative Update for SQL Server 2012 SP3 information webpage in the default browser

### EXAMPLE
Get-SQLDiagLatestCU -Product 'SQL Server 2012 SP3' -Download

Opens the Cumulative Update for SQL Server 2012 SP3 download webpage in the default browser

### EXAMPLE
Get-SQLDiagProduct 2012 | Get-SQLDiagLatestCU -LearnMore

Opens the Cumulative Update for SQL Server 2012 SP3 information webpage in the default browser

### EXAMPLE
Get-SQLDiagProduct 2012 | Get-SQLDiagLatestCU -Download

Opens the Cumulative Update for SQL Server 2012 SP3 download webpage in the default browser

### EXAMPLE
Get-SQLDiagLatestCU -Product 'SQL Server 2012 SP3','SQL Server 2014 SP1' | Out-GridView

Returns Product Name, Cumulative Update Name and Date created for SQL Server 2012 SP3 and SQL Server 2014 SP1 from the 
SQL Server Diagnostic API and outputs to Out-GridView

### EXAMPLE
Get-SQLDiagLatestCU -Product 'SQL Server 2012 SP3','SQL Server 2014 SP1' | Out-File C:\Temp\LatestCU.txt

Returns Product Name, Cumulative Update Name and Date created for SQL Server 2012 SP3 and SQL Server 2014 SP1 from the 
SQL Server Diagnostic API and outputs to a File C:\Temp\LatestCU.txt

### EXAMPLE
$LatestCu =  Get-SQLDiagLatestCU | Out-DbaDataTable
Write-DbaDataTable -SqlServer $Server -Database $DB -InputObject $LatestCu-Table $LatestCu -AutoCreateTable

Puts Product Name, Cumulative Update Name and Date created for all products from the 
SQL Server Diagnostic API into a database table and creates the table - Requires dbatools https://dbatools### io

### NOTES
    AUTHOR  Rob Sewell @SQLDBAWithBeard https://sqldbawithabeard.com
    DATE    30/06/2017