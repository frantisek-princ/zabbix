# Description
  This script monitors Windows Backup. It reads the job status with get-wbjob.
	It takes the first job, which has type backup. 
	It is then compared to how old the Job.
	The variable "$expired" is used to determine how old the backup may be.
  
	Returned values:
		wb.errorcode 0 ok
		wb.errorcode backup found, but error
		wb.errorcode backup found, no errors, but too old
  
  The Script read the Zabbix Hotname from the Zabbix Agent Conf.
  You can define with $hostname self a Hostname
  
# EXAMPLE
  c:\zabbix\bin\win64>powershell.exe c:\zabbix\scripts\backup01.ps1| c:\zabbix\bin\win64\zabbix_sender.exe -c c:\zabbix\conf\zabbix_agentd.conf -i - 
  
  This send the output with zabbix_sender to the Zabbix  Server / Proxy
  
  debug:
  c:\zabbix\bin\win64>powershell.exe c:\zabbix\scripts\backup01.ps1
  
  started only the Script and wirte the output to the console
