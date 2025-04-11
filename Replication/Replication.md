# Check Active Directory Replication

### Summarize the replication status and view the overall health
```cmd 
repadmin /replsummary
```
### Show replication partner and status
```cmd 
repadmin /showrepl
```

### Show only Replication Errors
```cmd 
repadmin /showrepl /errorsonly
```
### Show replication Queue
```cmd 
repadmin /Queue
```

### Force Active Directory Replication
Use the following command if you want to force replication between domain controllers. You will want to run this on the DC that you wish to update. For example, if DC1 is out of sync I would run this on DC1.

This will do a pull replication, which means it will pull updates from DC2 to DC1.

```cmd 
repadmin /syncall dc1 /Aed
```
If you want to push replication you will use the /P switch. For example if you make changes on DC1 and want to replicate those to other DCs use this command.

```cmd 
repadmin /syncall dc1 /APed
```

### Inter Site Topology Generator Report
```cmd 
repadmin /istg * /verbose
```
