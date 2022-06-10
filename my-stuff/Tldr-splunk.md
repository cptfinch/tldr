---
tags:
  - maturity-1
  - cheatsheet
---

## Examples

```
index="logs_ppi-rccn" Error | eval _raw=message |reverse 

index="logs_ppi-rccn" HPv3 

index="logs_ppi-*" HPv3 "Lost packet"   

index="logs_ppi-*" HPv3 "Lost packet" | eval _raw=message 

index="logs*" HPv3 "Lost packet" | stats count by host | fields count host 

index=first OR index=second | stats count by sourcetype | fields count sourcetype 

sourcetype="pridex_logs" host="SBF.110 - Bomarsund" | eval _raw=message  

sourcetype="pridex_logs" host="SBF.110 - Bomarsund" | eval _raw=message  

host="SBF.110 - Bomarsund" index="tags*" system!="PLC" | dedup name | table name process index=logs_pvcpt message=*"Warning, the system (seems to) encounter a problem, it is recommended to stop the treatment and to contact an IBA Technician!" AND "pts-treat-proc" AND tcr_operator_logger | eval correcthour=tonumber(substr(message, 12, 2)) | search correcthour>=8 AND correcthour<=17 
# gives the occurrance of popup messages in the logs of the treatment process during treatment hours. 
 
index="logs" process="poss-positioning-proc" forte_error_code>0 | lookup forte_err_msg_lookup error_code as forte_error_code OUTPUT error_msg as forte_error_msg | chart count(_raw) by forte_error_msg 
```

tags_ 
logs_ 
config_ 
host='SBF.110 - Bomarsund' 

## Treatment workflow report 
```
sourcetype="pridex_logs" "*UMI*" NOT room=MCR | sort fields.siteId room _time | table _time fields.siteId room *bms* *pms* *trcs* *time*pos* 
```
 
## What are the site names?
```
index="logs_ppi-*"  | stats count by fields.siteId 
```

index=logs_cyclhad "/srv/NagiosLogs/nagios.log" "*pridex*LOAD*" | rex field=message "load average: (?<average_1min>.+?)(?:(?:,\s)|$)(?<average_5min>.+?)(?:(?:,\s)|$)(?<average_15min>.+?)(?:(?:,\s)|$)" | bin span=0.2 average_1min as "load" | chart count as "count" by "load"

index=logs_cyclhad "/srv/NagiosLogs/nagios.log" "*pridex*LOAD*" | rex field=message "load average: (?<average_1min>.+?)(?:(?:,\s)|$)(?<average_5min>.+?)(?:(?:,\s)|$)(?<average_15min>.+?)(?:(?:,\s)|$)" | chart count by average_1min

index=logs_* "/srv/NagiosLogs/nagios.log" "*pridex*LOAD*" | rex field=message "load average: (?<average_1min>.+?)(?:(?:,\s)|$)(?<average_5min>.+?)(?:(?:,\s)|$)(?<average_15min>.+?)(?:(?:,\s)|$)" | table siteId average_1min average_5min average_15min | stats avg(average_1min) stdev(average_1min) max(average_1min) avg(average_5min) avg(average_15min) by siteId

index=logs_* "/srv/NagiosLogs/nagios.log" "*pridex*LOAD*" | rex field=message "load average: (?<average_1min>.+?)(?:(?:,\s)|$)(?<average_5min>.+?)(?:(?:,\s)|$)(?<average_15min>.+?)(?:(?:,\s)|$)" | table siteId average_1min average_5min average_15min | stats list(average_1min) as average_1min list(average_5min) as average_5min list(average_15min) as average_15min by siteId

index=logs_ppi-rccn "/srv/NagiosLogs/nagios.log" "*pridex*LOAD*" | regex message="load average: (?<blah>.+?)(?:(?:,\s)|$)(.+?)(?:(?:,\s)|$)(.+?)(?:(?:,\s)|$)"

load average: (.+?)(?:(?:,\s)|$)(.+?)(?:(?:,\s)|$)(.+?)(?:(?:,\s)|$)

index=logs_ppi-rccn "/srv/NagiosLogs/nagios.log" "*pridex*LOAD*" | regex  message="(average)" | table 5min_average_load

index=logs_* "/srv/NagiosLogs/nagios.log"

index=logs_* "/srv/NagiosLogs/nagios.log" "*pridex*LOAD*"  
| spath message | rex max_match=0 field=message "^(?<lines>.+)(\n+|$)" | mvexpand lines | fields lines, index, siteId 
| search lines = "*pridex*LOAD*" 

index="logs_ppi-rccn" Error | eval _raw=message |reverse 

index="logs_ppi-rccn" HPv3 

index="logs_ppi-*" HPv3 "Lost packet"   

index="logs_ppi-*" HPv3 "Lost packet" | eval _raw=message 

index="logs*" HPv3 "Lost packet" | stats count by host | fields count host 

index=first OR index=second | stats count by sourcetype | fields count sourcetype 

sourcetype="pridex_logs" host="SBF.110 - Bomarsund" | eval _raw=message  

host="SBF.110 - Bomarsund" index="tags*" system!="PLC" | dedup name | table name process index=logs_pvcpt message=*"Warning, the system (seems to) encounter a problem, it is recommended to stop the treatment and to contact an IBA Technician!" AND "pts-treat-proc" AND tcr_operator_logger | eval correcthour=tonumber(substr(message, 12, 2)) | search correcthour>=8 AND correcthour<=17 

# gives the occurrance of popup messages in the logs of the treatment process during treatment hours. 
 
index="logs" process="poss-positioning-proc" forte_error_code>0 | lookup forte_err_msg_lookup error_code as forte_error_code OUTPUT error_msg as forte_error_msg | chart count(_raw) by forte_error_msg 

tags_ 
logs_ 
config_ 
host='SBF.110 - Bomarsund' 

### Treatment workflow report 

sourcetype="pridex_logs" "*UMI*" NOT room=MCR | sort fields.siteId room _time | table _time fields.siteId room *bms* *pms* *trcs* *time*pos* 
 
### What are the site names?

index="logs_ppi-*"  | stats count by fields.siteId 

index="logs_*"  | stats count by siteId
