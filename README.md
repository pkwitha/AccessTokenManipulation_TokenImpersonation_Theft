# AccessTokenManipulation_TokenImpersonation_Theft
https://attack.mitre.org/techniques/T1134/001/
Privilege Escalation trick (administratior -> SYSTEM)

## SeDebugPrivilege
The SeDebugPrivilege privilege is a user right that allows a process to bypass/skip the access check in the kernel for a given object. If a token has the SeDebugPrivilege privilege enabled, the calling process can retrieve a handle to any process in the system by calling the OpenProcess() Win32 API to obtain a handle with PROCESS_ALL_ACCESS, PROCESS_QUERY_INFORMATION, or PROCESS_QUERY_LIMITED_INFORMATION. This means that the calling process can obtain a handle to any process in the system, even if it does not own the process.


## technique :
Creating a new process using a “stolen” token from another process is one of the strategies of token manipulation. This occurs when a token of an existing access token present in one of the active processes on the target host is extracted, duplicated, and then used to create a new process, so granting the new process the privileges of the stolen token.

### for example : winlogon.exe
![Untitled](https://github.com/pkwitha/AccessTokenManipulation_TokenImpersonation_Theft/assets/91279108/1524161a-0564-4847-8ed9-62ca3e52c665)

### after create process : cmd.exe
![Untitled2](https://github.com/pkwitha/AccessTokenManipulation_TokenImpersonation_Theft/assets/91279108/017298b8-2633-455b-b713-9cb7e72dcaee)
