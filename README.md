# sp_WhoIsActive
[![licence badge]][licence]
[![stars badge]][stars]
[![forks badge]][forks]
[![issues badge]][issues]

`sp_WhoIsActive` is a comprehensive activity monitoring stored procedure that works for all versions of SQL Server from 2005 through 2019 and Azure SQL DB.

`sp_WhoIsActive` is now officially versioned and maintained here on GitHub.

The license is now [GPLv3](/LICENSE).

Documentation is still available at http://whoisactive.com/docs

If you have enhancements, please consider a PR instead of a fork. I would like to continue to maintain this project for the community.

[licence badge]:https://img.shields.io/badge/license-GPLv3-blue.svg
[stars badge]:https://img.shields.io/github/stars/amachanic/sp_whoisactive.svg
[forks badge]:https://img.shields.io/github/forks/amachanic/sp_whoisactive.svg
[issues badge]:https://img.shields.io/github/issues/amachanic/sp_whoisactive.svg

[licence]:https://github.com/amachanic/sp_whoisactive/blob/master/LICENSE
[stars]:https://github.com/amachanic/sp_whoisactive/stargazers
[forks]:https://github.com/amachanic/sp_whoisactive/network
[issues]:https://github.com/amachanic/sp_whoisactive/issues

<br />
<br />
<br />
<br />

## Microsoft Dynamics AX 2012 - Database Performance
Sometimes it's hard do find what user are executing something that can hurt the SQL Server environment performance. This fork of `sp_WhoIsActive` enable the DBA to show the name of Microsoft Dynamics AX 2012's user that are quering something.

### Pre-requisites
* [Identifying a user session in SQL Server](https://docs.microsoft.com/en-us/dynamicsax-2012/appuser-itpro/troubleshooting-database-performance)

### Usage
| Parameter        | Type    | Description                                           |
|------------------|:-------:|------------------------------------------------------:|
| get_dax_user     | BIT     | When 1, enable the procedure to join the DAX database |
| get_dax_database | VARCHAR | The DAX database where UserInfo table is located      |

### Example
```SQL
    EXEC sp_WhoIsActive
        @get_dax_user = 1,
        @get_dax_database = 'CONTOSO';
```