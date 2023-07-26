# Connection Issues Troubleshooting

Please check the following list before asking for help in <#953244641518551080>:

## Connection issues checklist:

### Are you getting error messages about missing mods or wrong versions?
- Make sure you’re running the same version of the pack as the server.
- Make sure you installed the server using the _server pack files_, see <#1059529187079237722>.

### Do the server logs register your connection attempt?
→ **YES**
- does it show any errors in between the connection attempt and the disconnect?
- does the _client_ log show any errors?

→ **NO**
- Is the server application/port whitelisted in your machine’s firewall?
- If server is running from a home network:
 - Is the port forwarded from the router?
 - To the correct local address?
 - Are you using the correct address to connect?
 - Is it sitting behind Carrier Grade NAT?

### If the client crashes while trying to connect please provide logs
- File named (exactly) `latest.log` in '**logs**' folder
- File named `crash-xxxxxx.txt` in '**crash-reports**' folder (folder may not exist).

### If you are getting timeouts, have you tried adding the “connectivity” mod on 
the server side? 
<https://legacy.curseforge.com/minecraft/mc-mods/connectivity>
