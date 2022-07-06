Create a .ps1 file in the Scripts directory under win-acme install directory.

```
Stop-Service RemoteAccess
$certs = Get-ChildItem -Path Cert:\LocalMachine\My | Where-Object {$_.Subject -match "remoteaccess.contoso.com" -and $_.NotBefore -lt $(Get-Date) -and $_.NotAfter -gt $(Get-Date) }
Set-RemoteAccess -SslCertificate $certs[0]
Start-Service RemoteAccess
```

After creating a certificate, choose "Start external script or program" and specify the script file.
