Since NordVPN's Firefox extension is anything but stable, I needed a way of importing NordVPN servers to FoxyProxy.

```powershell
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$country = 'United States'
$servers = Invoke-WebRequest 'https://nordvpn.com/api/server' | ConvertFrom-Json
$servers | where country -eq $country | Sort-Object -Property load | Select-Object domain -First 10 | ForEach-Object { Write-Host (-join($_.domain, ":89:VPN_USERNAME:VPN_PASSWORD")) }
```
