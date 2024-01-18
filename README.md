# RDBMS Major version upgrades

Major version upgrades can be a significant amount of work, depending on various factors. Such as:
- Incompatible changes between major versions 
- Performance regressions due to changes in the engine's Query/Cost-based optimizer
- Choosing the right upgrade process that meets the requirements of your business, documenting and testing it
- Database/Application complexity and the amount of work required to perform proper testing (smoke, integration, regression and performance)
- In-flight application changes and new feature development

This project aims to help guide the world through these upgrades, particularly those on a managed service, such as Amazon RDS and Google Cloud SQL.    
We are not looking to reproduce technical documentation, but rather:
- Provide supplemental documentation 
- Aggregate existing documentation 
- Summarize important dates/deadlines, particularly  

In order to help create an actionable and successful plan.    

---
[![CC BY-NC-SA 4.0][cc-by-nc-sa-shield]][cc-by-nc-sa]

This work is licensed under a
[Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License][cc-by-nc-sa].

[![CC BY-NC-SA 4.0][cc-by-nc-sa-image]][cc-by-nc-sa]

[cc-by-nc-sa]: http://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-by-nc-sa-image]: https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png
[cc-by-nc-sa-shield]: https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg    

---

## General resources

Regardless of the RDBMS, we've created this [RDBMS major version upgrade checklist](docs/checklist.md).     
There will always be specifics related to the particular engine, but the goal of the checklist is to help create an actionable plan regardless of the engine.

## When should we start planning/executing a major version upgrade?

Ideally, major version upgrades should be completed before the [EOL](docs/glossary.md#end-of-life) of the engine.   
Managed services, such as Amazon RDS or Google Cloud SQL will offer grace periods to perform these upgrades, and in some situations offer extended support.   
***Start planning and executing your upgrades as soon as possible, based on EOL dates.***    
***Depending on the Cloud Service Provider (CSP), there will be particular deadlines, see below.***

## MySQL 5.7 EOL

- [MySQL 5.7 End of life summary and important dates/deadlines](docs/mysql/5.7_eol/README.md)

## PostgreSQL 11 EOL

- [PostgreSQL 11 End of life summary and important dates/deadlines](docs/postgresql/11_eol/README.md)

## Checklist

Here is [a checklist](docs/checklist.md) that you can use as a starting point to ensure a successful upgrade

