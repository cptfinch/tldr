---
tags:
  - tldr
---

select checks.host_id, versions.version_name
from versions_checks
inner join checks on versions_checks.checks_id = checks.ID

![](2021-11-18-12-47-35.png)
