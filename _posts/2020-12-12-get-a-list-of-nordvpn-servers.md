Since NordVPN's Firefox extension is anything but stable, I needed a way of importing NordVPN servers to FoxyProxy.

```powershell
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$country = 'United States'
$servers = Invoke-WebRequest 'https://nordvpn.com/api/server' | ConvertFrom-Json
$servers | Where-Object { $_.country -eq $country -and $_.features.proxy_ssl -eq $TRUE } | Sort-Object -Property load | Select-Object -First 10 | ForEach-Object { Write-Host (-join("https://VPN_USERNAME:VPN_PASSWORD@", $_.domain, ":89?title=", $_.domain.replace('.nordvpn.com', ''))) }
```
