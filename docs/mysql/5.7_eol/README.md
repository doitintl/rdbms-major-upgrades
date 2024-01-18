# MySQL 5.7 End of life

---

## TL;DR

### Supplemental documentation and content

DoiT has compiled some resources in order to help our customers plan and execute this major version upgrade successfully.
- [Mastering EOL Migrations: Lessons learned from MySQL 5.7 to 8.0 with Amazon RDS](https://www.youtube.com/watch?v=WTeOeumDfWw)
- [MySQL 5.7 End of life major version upgrade checklist](../../checklist.md) 

### MySQL 5.7 to 8 specific documentation
- [Review changes in MySQL 8.0](https://dev.mysql.com/doc/refman/8.0/en/upgrading-from-previous-series.html)
- [Review blog post](https://dev.mysql.com/blog-archive/upgrading-to-mysql-8-0-here-is-what-you-need-to-know/)
- Run the [Upgrade Checker Utility](https://dev.mysql.com/blog-archive/mysql-shell-8-0-4-introducing-upgrade-checker-utility/)
    - ***RDS***: This can be done manually, or you can clone and upgrade in-place which will automatically run the check
    - ***GCP***: Must run the upgrade checker manually
- [Capturing SQL statements](https://engineering.doit.com/how-to-capture-sql-statements-with-aws-rds-mysql-da12d95c5c4f))

---
## What is happening?

The MySQL community is planning to [deprecate MySQL 5.7 after October 31, 2023](https://www.oracle.com/us/support/library/lifetime-support-technology-069183.pdf).     
This means that there will be no security patches or bug fixes after this date from the community.   
In 2024, Database as a service providers, such as Amazon RDS and Google Cloud SQL will reach critical milestones with respect to the support of this version.   

## Amazon RDS MySQL 5.7
If you haven't already upgraded your instance to MySQL 8, [you will be opted in to Extended Support on February 29, 2024](https://repost.aws/articles/ARHdQg4IelQS2uyXkNrINw-A/announcement-amazon-rds-extended-support-opt-in-behavior-is-changing-upgrade-your-amazon-rds-for-mysql-5-7-database-instances-before-february-29-2024-to-avoid-potential-increase-in-charges).    
Extended support will incur [additional costs](https://aws.amazon.com/rds/mysql/pricing/#Amazon_RDS_Extended_Support_costs).    

## Amazon Aurora 2/MySQL 5.7

If you haven't already upgraded your instance to Aurora 3/MySQL 8, [you will be opted in to Extended Support on October 31, 2024](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/extended-support.html).    
Extended support will incur [additional costs](https://aws.amazon.com/rds/aurora/pricing/#Amazon_RDS_Extended_Support_costs).   

## Google Cloud SQL
There is no officially announced end of support date, which means that it will be at [least 12 months](https://cloud.google.com/sql/docs/mysql/db-versions#major_version_deprecation_plan) from the date of writing this.
> When Cloud SQL intends to end support for a specific major version, we will send a deprecation notice alerting project owners a minimum of 12 months ahead.    

[According to a GCP community thread](https://www.googlecloudcommunity.com/gc/Databases/Cloud-SQL-MySQL-5-7-EOL/m-p/646209/highlight/true#M1743), end of support will be December, 2024.     
***NOTE:*** This is not an official announcement, but including it here for completeness.    
Upgrading to MySQL 8 also gives you the ability to use [Cloud SQL Editions Enterprise Plus](https://cloud.google.com/blog/products/databases/announcing-the-cloud-sql-enterprise-plus-edition-for-mysql-and-postgresql).

## When should we start planning/executing the upgrade?

We ***do not recommend*** waiting, start planning/executing your upgrade now***

---