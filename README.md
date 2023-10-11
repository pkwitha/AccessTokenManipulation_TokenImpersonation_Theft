# AccessTokenManipulation_TokenImpersonation_Theft
https://attack.mitre.org/techniques/T1134/001/
### This attack technique is used by APT28 and FIN8 groups in the wild.
Privilege Escalation trick (administratior -> SYSTEM)

## SeDebugPrivilege
The SeDebugPrivilege privilege is a user right that allows a process to bypass/skip the access check in the kernel for a given object. If a token has the SeDebugPrivilege privilege enabled, the calling process can retrieve a handle to any process in the system by calling the OpenProcess() Win32 API to obtain a handle with PROCESS_ALL_ACCESS, PROCESS_QUERY_INFORMATION, or PROCESS_QUERY_LIMITED_INFORMATION. This means that the calling process can obtain a handle to any process in the system, even if it does not own the process.


## technique :
Creating a new process using a “stolen” token from another process is one of the strategies of token manipulation. This occurs when a token of an existing access token present in one of the active processes on the target host is extracted, duplicated, and then used to create a new process, so granting the new process the privileges of the stolen token.

### for example : winlogon.exe
![Untitled](https://github.com/pkwitha/AccessTokenManipulation_TokenImpersonation_Theft/assets/91279108/2a56800a-5aaa-444e-b54b-4bc9b18396bb)


### after create process : cmd.exe

![Untitled2](https://github.com/pkwitha/AccessTokenManipulation_TokenImpersonation_Theft/assets/91279108/248c1e48-0bb1-4abf-81cc-13314b7e4bc8)
