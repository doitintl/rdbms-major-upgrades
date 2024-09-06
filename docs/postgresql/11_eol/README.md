# PostgreSQL 11 End of life

---

### TL;DR

### Supplemental documentation and content

DoiT has compiled some resources in order to help our customers plan and execute this major version upgrade successfully.
- [Mastering EOL Migrations: Lessons learned from MySQL 5.7 to 8.0 with Amazon RDS](https://www.youtube.com/watch?v=WTeOeumDfWw)
  - This is MySQL focused, but the general tips and talking points apply to all database engines
- [Major version upgrade checklist](../../checklist.md) 

### PostgreSQL upgrade specific documentation
- `#TODO`

---

## What is happening?

The PostgreSQL community has released the final minor version of major version 11 on [November 9, 2023](https://www.postgresql.org/support/versioning/).     
This means that there will be no security patches or bug fixes after this date from the community.   
In 2024, Database as a service providers, such as Amazon RDS and Google Cloud SQL will reach critical milestones with respect to the support of this version.   

## Amazon RDS PostgreSQL 11
If you haven't already upgraded your instance to  PostgreSQL 12 or higher, [you will be opted in to Extended Support on April 1, 2024](https://docs.aws.amazon.com/AmazonRDS/latest/PostgreSQLReleaseNotes/postgresql-release-calendar.html).    
Extended support will incur [additional costs](https://aws.amazon.com/rds/postgresql/pricing/#Amazon_RDS_Extended_Support_costs).    

## Amazon Aurora 3/PostgreSQL 11

If you haven't already upgraded your instance to Aurora 4/PostgreSQL 12, Aurora 13/PostgreSQL 13 or higher, [you will be opted in to Extended Support on April 1, 2024](https://aws.amazon.com/blogs/aws/your-mysql-5-7-and-postgresql-11-databases-will-be-automatically-enrolled-into-amazon-rds-extended-support/).    
Extended support will incur [additional costs](https://aws.amazon.com/rds/aurora/pricing/#Amazon_RDS_Extended_Support_costs).   

## Google Cloud SQL
>Starting on February 1, 2025, the following database major versions will enter extended support:
>
>PostgreSQL: 9.6, 10, 11, 12

Extended support will incur [addition costs](https://cloud.google.com/sql/pricing#extended-support-pricing).

For more information [please see Google blog post](https://cloud.google.com/blog/products/databases/extended-support-for-end-of-life-cloud-sql-mysql-and-postgresql).

[Database version policies](https://cloud.google.com/sql/docs/db-versions).

## When should we start planning/executing the upgrade?

We ***do not recommend*** waiting, start planning/executing your upgrade now***

---