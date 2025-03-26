# SaRACmd
SaRACmd: Remove all version of Office using CMD (M365, 2019, 2016)

Download: https://aka.ms/SaRA_EnterpriseVersionFiles

## **Available switches for the Office Uninstall scenario**

The following switches are available for this scenario. They aren't case-sensitive. Unless noted as optional, the switches are required to run the scenario. You can use more than one optional switch.

**Expand table**

| Switch \<parameter> | Details | Required/Optional |
| --- | --- | --- |
| `-S <scenarioname>` | Specify this switch and `OfficeScrubScenario` as the value for the `scenarioname` parameter to run this scenario. | Required |
| `-AcceptEula` | Specify this switch to accept the End User License Agreement (EULA) and to run this scenario. | Required |
| `-OfficeVersion` | Specify this switch to remove the Office version that's defined in the `<version>` parameter. The allowed values for the `<version>` parameter are All, M365, 2021, 2019, 2016, 2013, 2010, and 2007. | Optional |

## **Sample commands**

Here are some sample combinations of switches to run this scenario.

*   Sample 1
    
    To uninstall the detected installed version of Office, run the following command in an elevated Command Prompt window:
    
    ConsoleCopy
    
    ```plaintext
    SaRAcmd.exe -S OfficeScrubScenario -AcceptEula
    ```
    
*   Sample 2
    
    To uninstall a subscription version of Office, such as Microsoft 365 Apps for enterprise, run the following command in an elevated Command Prompt window:
    
    ConsoleCopy
    
    ```plaintext
    SaRAcmd.exe -S OfficeScrubScenario -AcceptEula -OfficeVersion M365
    ```
    
*   Sample 3
    
    To uninstall Office 2016 only, run the following command in an elevated Command Prompt window:
    
    ConsoleCopy
    
    ```plaintext
    SaRAcmd.exe -S OfficeScrubScenario -AcceptEula -OfficeVersion 2016
    ```
    
*   Sample 4
    
    To uninstall all versions of Office, run the following command in an elevated Command Prompt window:
    
    ConsoleCopy
    
    ```plaintext
    SaRAcmd.exe -S OfficeScrubScenario -AcceptEula -OfficeVersion All
    ```
    

## **Detected conditions and results**

When you run the Office Uninstall scenario by using the Enterprise version of the Assistant, you don't receive any prompts. This is a different experience from the full version of the Assistant. The following table describes the actions that the Enterprise version of the Assistant takes for each condition that's encountered by this scenario, and the corresponding output that's displayed.

**Expand table**

| Condition | Action taken by the Enterprise version | Output shown in the Command Prompt window |
| --- | --- | --- |
| Office is removed successfully | None | 00: Successfully completed this scenario.  
  
**Note:** We recommend you restart the computer to finish any remaining cleanup tasks. |
| Office program found .exe files running: `lync`, `winword`, `excel`, `msaccess`, `mstore`, `infopath`, `setlang`, `msouc`, `ois`, `onenote`, `outlook`, `powerpnt`, `mspub`, `groove`, `visio`, `winproj`, `graph`, `teams` | Exit the scenario | 06: Office programs are running. Please close all open Office programs and then rerun this scenario. |
| No Office products found, and the `-OfficeVersion` switch isn't used | Exit the scenario | 68: We could not find any Office version. Please rerun this scenario specifying the correct Office version that is installed on your machine. You can also run this scenario using the full UI version of SaRA. For additional information, please visit [https://aka.ms/SaRA_CommandLineVersion](https://aka.ms/SaRA_CommandLineVersion).  
  
**Note:** For SaRA command line users with version 17.00.8256.000 or earlier, the error displayed is:  
  
\-07: No installed Office versions were found. Please use the full SaRA version. |
| Multiple Office versions are detected as installed, and the `-OfficeVersion` switch isn't used | Exit the scenario | 08: Multiple Office versions were found. Please use the full SaRA version. |
| Failure to remove Office | Exit the scenario | 09: Failure to remove Office. Please use the full SaRA version. |
| The Assistant isn't running in elevated mode | Exit the scenario | 10: SaRA needs to run elevated for this scenario. Please use an elevated command-prompt. |
| Office version specified on the command line doesn't match the detected installed version | Exit the scenario | 66: We could not find the specified Office version. Please rerun this scenario specifying the correct Office version that is installed on your machine. You can also run this scenario using the full UI version of SaRA. For additional information, please visit [https://aka.ms/SaRA_CommandLineVersion](https://aka.ms/SaRA_CommandLineVersion). |
| Invalid Office version specified on the command line | Exit the scenario | 67: The Office version that you have specified is invalid. Please rerun this scenario specifying the correct Office version that is installed on your machine. You can also run this scenario using the full UI version of SaRA. For additional information, please visit [https://aka.ms/SaRA_CommandLineVersion](https://aka.ms/SaRA_CommandLineVersion). |
