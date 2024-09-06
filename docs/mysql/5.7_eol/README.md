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

>Starting on February 1, 2025, the following database major versions will enter extended support:
>
>MySQL: 5.6, 5.7

Extended support will incur [addition costs](https://cloud.google.com/sql/pricing#extended-support-pricing).

For more information [please see Google blog post](https://cloud.google.com/blog/products/databases/extended-support-for-end-of-life-cloud-sql-mysql-and-postgresql).

[Database version policies](https://cloud.google.com/sql/docs/db-versions).

### Post Upgrade Tasks
* For Cloud SQL for MySQL, after the upgrade “root” user may not have desired permissions. In that case create a temporary user from the console (this user will automatically have cloudsqlsuperuser role) and use it to grant root necessary privileges. Step 2 in this document: https://cloud.google.com/sql/docs/mysql/upgrade-major-db-version-inplace#complete_the_major_version_upgrade

    #### Steps to solve:
    Create a user from the console. This user will have cloudsqlsuperuser role by default.
Default permissions for a user created from the console:

```sql

mysql> SHOW GRANTS FOR 'fromconsole';
+----------------------------------------------------+
| Grants for fromconsole@%                           |
+----------------------------------------------------+
| GRANT USAGE ON *.* TO `fromconsole`@`%`            |
| GRANT `cloudsqlsuperuser`@`%` TO `fromconsole`@`%` |
+----------------------------------------------------+
2 rows in set (0.03 sec)

 ``` 
 
Log in as fromconsole user and run the following grants:

```sql
mysql> grant cloudsqlsuperuser to root;
mysql> GRANT ROLE_ADMIN ON *.* TO root;
```

NOTE: If you create Cloud SQL for MySQL 8.0, the root user will have the following permissions:

```sql
mysql> show grants for root;
+---------------------------------------------+
| Grants for root@%                           |
+---------------------------------------------+
| GRANT USAGE ON *.* TO `root`@`%`            |
| GRANT `cloudsqlsuperuser`@`%` TO `root`@`%` |
+---------------------------------------------+
2 rows in set (0.04 sec)
```

## When should we start planning/executing the upgrade?

We ***do not recommend*** waiting, start planning/executing your upgrade now***

---