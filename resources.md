## For Intune Related

1. For all Intune/M365 related [https://www.prajwaldesai.com/](https://www.prajwaldesai.com/)
2. Intune debug toolkit <https://msendpointmgr.com/intune-debug-toolkit/>
3. 


## PowerShell Related

- Starting, Stopping Services

  ```powershell
  Stop-Service -Name Spooler
  Start-Service -Name Spooler
  ```

- Getting available Disk space

    ```powershell
    Get-CimInstance -ClassName Win32_LogicalDisk -Filter "DriveType=3"
    ```

- To check if a remote port is open

    ``` powershell
    tnc myserver.mydns.com -port 85
    ```

- To get a serial number of a computer

    ```powershell
    wmic bios get serialnumber
    ```

- Check when was the computer last booted

    ```powershell
    Systeminfo | find "System Boot Time"
    ```

- `netsh wlan show wlanreport`

- `powercfg /batteryreport`

- `Get-Service`

- `Get-EventLog`
