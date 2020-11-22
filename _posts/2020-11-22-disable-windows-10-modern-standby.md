To disable Modern Standby (Connected Standby) on Windows 10 20H2, start **Command Prompt** and run the following:

    reg add HKLM\System\CurrentControlSet\Control\Power /v PlatformAoAcOverride /t REG_DWORD /d 0
