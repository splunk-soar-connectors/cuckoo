[comment]: # "Auto-generated SOAR connector documentation"
# Cuckoo

Publisher: Splunk Community  
Connector Version: 2\.2\.1  
Product Vendor: Cuckoo  
Product Name: Cuckoo  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 5\.0\.0  

This app supports executing various investigative and generic actions on the Cuckoo sandbox

[comment]: # " File: readme.md"
[comment]: # "  Copyright (c) 2014-2022 Splunk Inc."
[comment]: # ""
[comment]: # "  Licensed under Apache 2.0 (https://www.apache.org/licenses/LICENSE-2.0.txt)"
[comment]: # ""
## SDK and SDK Licensing details for the app

#### pexpect

This app uses the pexpect module, which is licensed under the ISC License (ISCL), Copyright (c) Noah
Spurrier, Thomas Kluyver, Jeff Quast.

#### ptyprocess

This app uses the ptyprocess module, which is licensed under the ISC License (ISCL), Copyright (c)
Thomas Kluyver.

### Getting Web Reports

If you add the base URL to the Cuckoo instance's Web Interface, a link will be generated and added
to the action result which will point to analysis summary for each action.

## Playbook Backward Compatibility

-   The existing action parameter has been modified in the action given below. Hence, it is
    requested to the end-user to please update their existing playbooks by re-inserting \| modifying
    \| deleting the corresponding action blocks or by providing appropriate values to these action
    parameters to ensure the correct functioning of the playbooks created on the earlier versions of
    the app.

      

    -   Detonate File - The new \[zip_and_encrypt\] parameter has been added providing an option to
        zip and encrypt the file.

-   New action 'submit strings' has been added. Hence, it is requested to the end-user to please
    update their existing playbooks by inserting the corresponding action blocks for this action on
    the earlier versions of the app.


### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a Cuckoo asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**server** |  required  | string | Server IP/Hostname
**port** |  required  | string | REST API Port
**use\_https** |  optional  | boolean | Connect with HTTPS
**verify\_server\_cert** |  optional  | boolean | Verify server certificate
**timeout** |  required  | numeric | Timeout \(seconds\)
**username** |  optional  | string | HTTP Basic Auth Username
**password** |  optional  | password | HTTP Basic Auth Password
**append\_uri** |  optional  | string | Additional URI Path to Add to the Server
**web\_ui\_base\_url** |  optional  | string | Base URL to the Web Interface \(e\.g\. https\://10\.16\.6\.42\:8000/\)

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[detonate file](#action-detonate-file) - Run the file in the sandbox and retrieve the analysis results  
[get report](#action-get-report) - Query for results of an already completed detonation  
[detonate url](#action-detonate-url) - Load a URL in the Cuckoo sandbox and retrieve the analysis results  
[submit strings](#action-submit-strings) - Add VirusTotal compatible URL/Domain to the list of pending tasks  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'detonate file'
Run the file in the sandbox and retrieve the analysis results

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**vault\_id** |  required  | Vault ID of file to detonate | string |  `vault id`  `sha1` 
**file\_name** |  optional  | Filename to use | string |  `file name` 
**zip\_and\_encrypt** |  optional  | Option to zip and encrypt file, WARNING\: password visible as zip command line argument | boolean | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.file\_name | string |  `file name` 
action\_result\.parameter\.vault\_id | string |  `vault id`  `sha1` 
action\_result\.parameter\.zip\_and\_encrypt | string | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.CopyFileA | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.CreateServiceA | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.FindResourceExW | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.GetFileAttributesW | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.GetFileSize | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.GetFileType | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.GetSystemInfo | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.GetSystemMetrics | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.GetSystemTimeAsFileTime | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.GetSystemWindowsDirectoryW | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.GetTempPathW | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.GetTimeZoneInformation | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.LdrGetDllHandle | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.LdrGetProcedureAddress | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.LdrLoadDll | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.LoadResource | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.LoadStringA | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtAllocateVirtualMemory | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtClose | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtCreateFile | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtCreateMutant | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtCreateSection | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtCreateThreadEx | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtDelayExecution | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtDuplicateObject | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtFreeVirtualMemory | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtMapViewOfSection | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtOpenKey | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtOpenMutant | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtProtectVirtualMemory | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtQueryAttributesFile | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtQueryInformationFile | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtQueryValueKey | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtReadFile | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtResumeThread | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtWriteFile | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.OpenSCManagerA | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.OutputDebugStringA | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.RegCloseKey | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.RegOpenKeyExA | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.RegOpenKeyExW | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.RegQueryValueExA | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.RegQueryValueExW | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.RegSetValueExA | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.SetEndOfFile | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.SetFileAttributesW | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.SetFilePointer | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.SetFileTime | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.SetUnhandledExceptionFilter | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.SetWindowsHookExA | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.StartServiceA | numeric | 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.first\_seen | numeric | 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.pid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.ppid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.process\_name | string |  `file name` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.process\_path | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.dll\_loaded | string | 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.file\_copied\.\* | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.file\_created | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.file\_exists | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.file\_opened | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.file\_read | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.file\_recreated | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.file\_written | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.mutex | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.regkey\_opened | string | 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.regkey\_read | string | 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.regkey\_written | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.api | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.access | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.allocation\_type | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.base\_address | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.base\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.basename | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.buffer | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.callback\_function | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.commit\_size | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.create\_disposition | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.create\_options | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.database\_name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.desired\_access | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.dirpath | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.display\_name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.error\_control | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.fail\_if\_exists | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.file\_attributes | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.file\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.file\_size\_low | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.filepath | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.filepath\_r | string |  `file name`  `file path` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.flags | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.free\_type | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.function\_address | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.function\_name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.handle\_attributes | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.hook\_identifier | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.id | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.index | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.information\_class | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.initial\_owner | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.key\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.key\_name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.language\_identifier | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.length | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.machine\_name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.milliseconds | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.module | string |  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.module\_address | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.module\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.module\_name | string |  `file name`  `file path` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.move\_method | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.mutant\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.mutant\_name | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.newfilepath | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.newfilepath\_r | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.object\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.offset | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.oldfilepath | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.oldfilepath\_r | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.options | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.ordinal | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.parameter | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.password | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.pointer | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.process\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.process\_identifier | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.processor\_count | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.protection | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.reg\_type | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.region\_size | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.regkey | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.regkey\_r | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.resource\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.section\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.section\_name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.section\_offset | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.service\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.service\_manager\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.service\_name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.service\_start\_name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.service\_type | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.share\_access | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.size | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.skipped | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.source\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.source\_process\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.source\_process\_identifier | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.stack\_zero\_bits | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.start\_type | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.status\_info | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.string | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.suspend\_count | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.suspended | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.target\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.target\_process\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.target\_process\_identifier | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.thread\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.thread\_identifier | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.thread\_name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.type | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.value | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.view\_size | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.win32\_protect | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.category | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.allocation\_type | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.create\_disposition | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.create\_options | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.desired\_access | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.file\_attributes | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.hook\_identifier | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.index | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.information\_class | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.protection | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.reg\_type | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.share\_access | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.status\_info | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.win32\_protect | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.last\_error | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.nt\_status | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.return\_value | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.status | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.tid | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.time | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.command\_line | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.first\_seen | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.modules\.\*\.baseaddr | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.modules\.\*\.basename | string |  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.modules\.\*\.filepath | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.modules\.\*\.imgsize | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.pid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.ppid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.process\_name | string |  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.process\_path | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.tid | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.time | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.track | boolean | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.type | string | 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.command\_line | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.first\_seen | numeric | 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.pid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.ppid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.process\_name | string |  `file name` 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.track | boolean | 
action\_result\.data\.\*\.report\.behavior\.summary\.dll\_loaded | string | 
action\_result\.data\.\*\.report\.behavior\.summary\.file\_copied\.\* | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.summary\.file\_created | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.summary\.file\_exists | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.summary\.file\_opened | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.summary\.file\_read | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.summary\.file\_recreated | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.summary\.file\_written | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.summary\.mutex | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.summary\.regkey\_opened | string | 
action\_result\.data\.\*\.report\.behavior\.summary\.regkey\_read | string | 
action\_result\.data\.\*\.report\.behavior\.summary\.regkey\_written | string | 
action\_result\.data\.\*\.report\.debug\.cuckoo | string | 
action\_result\.data\.\*\.report\.debug\.log | string | 
action\_result\.data\.\*\.report\.dropped\.\*\.crc32 | string | 
action\_result\.data\.\*\.report\.dropped\.\*\.filepath | string |  `file path` 
action\_result\.data\.\*\.report\.dropped\.\*\.md5 | string |  `md5` 
action\_result\.data\.\*\.report\.dropped\.\*\.name | string | 
action\_result\.data\.\*\.report\.dropped\.\*\.path | string | 
action\_result\.data\.\*\.report\.dropped\.\*\.pids | numeric | 
action\_result\.data\.\*\.report\.dropped\.\*\.sha1 | string |  `sha1` 
action\_result\.data\.\*\.report\.dropped\.\*\.sha256 | string |  `sha256` 
action\_result\.data\.\*\.report\.dropped\.\*\.sha512 | string | 
action\_result\.data\.\*\.report\.dropped\.\*\.size | numeric | 
action\_result\.data\.\*\.report\.dropped\.\*\.type | string | 
action\_result\.data\.\*\.report\.info\.added | numeric | 
action\_result\.data\.\*\.report\.info\.category | string | 
action\_result\.data\.\*\.report\.info\.custom | string | 
action\_result\.data\.\*\.report\.info\.duration | numeric | 
action\_result\.data\.\*\.report\.info\.ended | numeric | 
action\_result\.data\.\*\.report\.info\.git\.fetch\_head | string | 
action\_result\.data\.\*\.report\.info\.git\.head | string | 
action\_result\.data\.\*\.report\.info\.id | numeric | 
action\_result\.data\.\*\.report\.info\.machine\.label | string | 
action\_result\.data\.\*\.report\.info\.machine\.manager | string | 
action\_result\.data\.\*\.report\.info\.machine\.name | string | 
action\_result\.data\.\*\.report\.info\.machine\.shutdown\_on | string | 
action\_result\.data\.\*\.report\.info\.machine\.started\_on | string | 
action\_result\.data\.\*\.report\.info\.machine\.status | string | 
action\_result\.data\.\*\.report\.info\.monitor | string |  `sha1` 
action\_result\.data\.\*\.report\.info\.options | string | 
action\_result\.data\.\*\.report\.info\.owner | string | 
action\_result\.data\.\*\.report\.info\.package | string | 
action\_result\.data\.\*\.report\.info\.platform | string | 
action\_result\.data\.\*\.report\.info\.route | string | 
action\_result\.data\.\*\.report\.info\.score | numeric | 
action\_result\.data\.\*\.report\.info\.started | numeric | 
action\_result\.data\.\*\.report\.info\.version | string | 
action\_result\.data\.\*\.report\.metadata\.output\.dropped\.\*\.basename | string | 
action\_result\.data\.\*\.report\.metadata\.output\.dropped\.\*\.dirname | string | 
action\_result\.data\.\*\.report\.metadata\.output\.dropped\.\*\.sha256 | string |  `sha256` 
action\_result\.data\.\*\.report\.metadata\.output\.pcap\.basename | string | 
action\_result\.data\.\*\.report\.metadata\.output\.pcap\.dirname | string | 
action\_result\.data\.\*\.report\.metadata\.output\.pcap\.sha256 | string |  `sha256` 
action\_result\.data\.\*\.report\.network\.dns\.\*\.answers\.\*\.data | string |  `ip` 
action\_result\.data\.\*\.report\.network\.dns\.\*\.answers\.\*\.type | string | 
action\_result\.data\.\*\.report\.network\.dns\.\*\.request | string | 
action\_result\.data\.\*\.report\.network\.dns\.\*\.type | string | 
action\_result\.data\.\*\.report\.network\.dns\_servers | string |  `ip` 
action\_result\.data\.\*\.report\.network\.domains\.\*\.domain | string |  `domain` 
action\_result\.data\.\*\.report\.network\.domains\.\*\.ip | string |  `ip` 
action\_result\.data\.\*\.report\.network\.hosts | string |  `ip` 
action\_result\.data\.\*\.report\.network\.pcap\_sha256 | string |  `sha256` 
action\_result\.data\.\*\.report\.network\.sorted\_pcap\_sha256 | string |  `sha256` 
action\_result\.data\.\*\.report\.network\.udp\.\*\.dport | numeric | 
action\_result\.data\.\*\.report\.network\.udp\.\*\.dst | string |  `ip` 
action\_result\.data\.\*\.report\.network\.udp\.\*\.offset | numeric | 
action\_result\.data\.\*\.report\.network\.udp\.\*\.sport | numeric | 
action\_result\.data\.\*\.report\.network\.udp\.\*\.src | string |  `ip` 
action\_result\.data\.\*\.report\.network\.udp\.\*\.time | numeric | 
action\_result\.data\.\*\.report\.screenshots\.\*\.ocr | string | 
action\_result\.data\.\*\.report\.screenshots\.\*\.path | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.description | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.families | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.markcount | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.api | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.allocation\_type | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.base\_address | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.desired\_access | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.display\_name | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.error\_control | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.filepath | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.filepath\_r | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.password | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.process\_handle | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.process\_identifier | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.protection | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.region\_size | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.service\_handle | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.service\_manager\_handle | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.service\_name | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.service\_start\_name | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.service\_type | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.start\_type | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.category | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.flags\.allocation\_type | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.flags\.protection | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.return\_value | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.status | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.tid | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.time | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.category | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.cid | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.description | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.entropy | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.filetype | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.ioc | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.language | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.name | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.offset | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.pid | numeric |  `pid` 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.section\.entropy | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.section\.name | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.section\.size\_of\_data | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.section\.virtual\_address | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.section\.virtual\_size | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.service\_name | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.service\_path | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.size | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.sublanguage | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.type | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.name | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.references | string |  `url` 
action\_result\.data\.\*\.report\.signatures\.\*\.severity | numeric | 
action\_result\.data\.\*\.report\.static\.imported\_dll\_count | numeric | 
action\_result\.data\.\*\.report\.static\.pe\_exports\.\*\.address | string | 
action\_result\.data\.\*\.report\.static\.pe\_exports\.\*\.name | string | 
action\_result\.data\.\*\.report\.static\.pe\_exports\.\*\.ordinal | numeric | 
action\_result\.data\.\*\.report\.static\.pe\_imphash | string |  `md5` 
action\_result\.data\.\*\.report\.static\.pe\_imports\.\*\.dll | string |  `file name` 
action\_result\.data\.\*\.report\.static\.pe\_imports\.\*\.imports\.\*\.address | string | 
action\_result\.data\.\*\.report\.static\.pe\_imports\.\*\.imports\.\*\.name | string | 
action\_result\.data\.\*\.report\.static\.pe\_resources\.\*\.filetype | string | 
action\_result\.data\.\*\.report\.static\.pe\_resources\.\*\.language | string | 
action\_result\.data\.\*\.report\.static\.pe\_resources\.\*\.name | string | 
action\_result\.data\.\*\.report\.static\.pe\_resources\.\*\.offset | string | 
action\_result\.data\.\*\.report\.static\.pe\_resources\.\*\.size | string | 
action\_result\.data\.\*\.report\.static\.pe\_resources\.\*\.sublanguage | string | 
action\_result\.data\.\*\.report\.static\.pe\_sections\.\*\.entropy | numeric | 
action\_result\.data\.\*\.report\.static\.pe\_sections\.\*\.name | string | 
action\_result\.data\.\*\.report\.static\.pe\_sections\.\*\.size\_of\_data | string | 
action\_result\.data\.\*\.report\.static\.pe\_sections\.\*\.virtual\_address | string | 
action\_result\.data\.\*\.report\.static\.pe\_sections\.\*\.virtual\_size | string | 
action\_result\.data\.\*\.report\.static\.pe\_timestamp | string | 
action\_result\.data\.\*\.report\.static\.pe\_versioninfo\.\*\.name | string | 
action\_result\.data\.\*\.report\.static\.pe\_versioninfo\.\*\.value | string |  `file name` 
action\_result\.data\.\*\.report\.strings | string | 
action\_result\.data\.\*\.report\.target\.category | string | 
action\_result\.data\.\*\.report\.target\.file\.crc32 | string | 
action\_result\.data\.\*\.report\.target\.file\.md5 | string |  `md5` 
action\_result\.data\.\*\.report\.target\.file\.name | string |  `file name` 
action\_result\.data\.\*\.report\.target\.file\.path | string | 
action\_result\.data\.\*\.report\.target\.file\.sha1 | string |  `sha1` 
action\_result\.data\.\*\.report\.target\.file\.sha256 | string |  `sha256` 
action\_result\.data\.\*\.report\.target\.file\.sha512 | string | 
action\_result\.data\.\*\.report\.target\.file\.size | numeric | 
action\_result\.data\.\*\.report\.target\.file\.type | string | 
action\_result\.data\.\*\.task\_status\.added\_on | string | 
action\_result\.data\.\*\.task\_status\.category | string | 
action\_result\.data\.\*\.task\_status\.clock | string | 
action\_result\.data\.\*\.task\_status\.completed\_on | string | 
action\_result\.data\.\*\.task\_status\.custom | string | 
action\_result\.data\.\*\.task\_status\.duration | numeric | 
action\_result\.data\.\*\.task\_status\.enforce\_timeout | boolean | 
action\_result\.data\.\*\.task\_status\.guest\.id | numeric | 
action\_result\.data\.\*\.task\_status\.guest\.label | string | 
action\_result\.data\.\*\.task\_status\.guest\.manager | string | 
action\_result\.data\.\*\.task\_status\.guest\.name | string | 
action\_result\.data\.\*\.task\_status\.guest\.shutdown\_on | string | 
action\_result\.data\.\*\.task\_status\.guest\.started\_on | string | 
action\_result\.data\.\*\.task\_status\.guest\.status | string | 
action\_result\.data\.\*\.task\_status\.guest\.task\_id | numeric | 
action\_result\.data\.\*\.task\_status\.id | numeric | 
action\_result\.data\.\*\.task\_status\.machine | string | 
action\_result\.data\.\*\.task\_status\.memory | boolean | 
action\_result\.data\.\*\.task\_status\.owner | string | 
action\_result\.data\.\*\.task\_status\.package | string | 
action\_result\.data\.\*\.task\_status\.platform | string | 
action\_result\.data\.\*\.task\_status\.priority | numeric | 
action\_result\.data\.\*\.task\_status\.route | string | 
action\_result\.data\.\*\.task\_status\.sample\.crc32 | string | 
action\_result\.data\.\*\.task\_status\.sample\.file\_size | numeric | 
action\_result\.data\.\*\.task\_status\.sample\.file\_type | string | 
action\_result\.data\.\*\.task\_status\.sample\.id | numeric | 
action\_result\.data\.\*\.task\_status\.sample\.md5 | string |  `md5` 
action\_result\.data\.\*\.task\_status\.sample\.sha1 | string |  `sha1` 
action\_result\.data\.\*\.task\_status\.sample\.sha256 | string |  `sha256` 
action\_result\.data\.\*\.task\_status\.sample\.sha512 | string | 
action\_result\.data\.\*\.task\_status\.sample\_id | numeric | 
action\_result\.data\.\*\.task\_status\.started\_on | string | 
action\_result\.data\.\*\.task\_status\.status | string | 
action\_result\.data\.\*\.task\_status\.target | string |  `file name` 
action\_result\.data\.\*\.task\_status\.timeout | numeric | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.id | numeric |  `cuckoo task id` 
action\_result\.summary\.results\_url | string |  `url` 
action\_result\.summary\.target | string |  `file name` 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'get report'
Query for results of an already completed detonation

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**id** |  required  | Task ID to get the results of | string |  `cuckoo task id` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.id | string |  `cuckoo task id` 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.CopyFileA | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.CreateServiceA | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.FindResourceExW | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.GetFileAttributesW | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.GetFileSize | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.GetFileType | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.GetSystemInfo | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.GetSystemMetrics | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.GetSystemTimeAsFileTime | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.GetSystemWindowsDirectoryW | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.GetTempPathW | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.GetTimeZoneInformation | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.LdrGetDllHandle | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.LdrGetProcedureAddress | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.LdrLoadDll | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.LoadResource | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.LoadStringA | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtAllocateVirtualMemory | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtClose | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtCreateFile | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtCreateMutant | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtCreateSection | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtCreateThreadEx | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtDelayExecution | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtDuplicateObject | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtFreeVirtualMemory | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtMapViewOfSection | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtOpenKey | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtOpenMutant | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtProtectVirtualMemory | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtQueryAttributesFile | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtQueryInformationFile | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtQueryValueKey | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtReadFile | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtResumeThread | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.NtWriteFile | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.OpenSCManagerA | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.OutputDebugStringA | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.RegCloseKey | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.RegOpenKeyExA | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.RegOpenKeyExW | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.RegQueryValueExA | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.RegQueryValueExW | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.RegSetValueExA | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.SetEndOfFile | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.SetFileAttributesW | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.SetFilePointer | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.SetFileTime | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.SetUnhandledExceptionFilter | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.SetWindowsHookExA | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.984\.StartServiceA | numeric | 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.first\_seen | numeric | 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.pid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.ppid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.process\_name | string |  `file name` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.process\_path | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.dll\_loaded | string | 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.file\_copied\.\* | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.file\_created | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.file\_exists | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.file\_opened | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.file\_read | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.file\_recreated | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.file\_written | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.mutex | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.regkey\_opened | string | 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.regkey\_read | string | 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.regkey\_written | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.api | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.access | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.allocation\_type | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.base\_address | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.base\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.basename | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.buffer | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.callback\_function | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.commit\_size | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.create\_disposition | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.create\_options | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.database\_name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.desired\_access | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.dirpath | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.display\_name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.error\_control | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.fail\_if\_exists | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.file\_attributes | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.file\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.file\_size\_low | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.filepath | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.filepath\_r | string |  `file name`  `file path` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.flags | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.free\_type | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.function\_address | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.function\_name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.handle\_attributes | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.hook\_identifier | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.id | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.index | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.information\_class | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.initial\_owner | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.key\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.key\_name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.language\_identifier | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.length | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.machine\_name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.milliseconds | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.module | string |  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.module\_address | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.module\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.module\_name | string |  `file name`  `file path` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.move\_method | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.mutant\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.mutant\_name | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.newfilepath | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.newfilepath\_r | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.object\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.offset | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.oldfilepath | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.oldfilepath\_r | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.options | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.ordinal | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.parameter | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.password | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.pointer | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.process\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.process\_identifier | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.processor\_count | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.protection | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.reg\_type | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.region\_size | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.regkey | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.regkey\_r | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.resource\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.section\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.section\_name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.section\_offset | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.service\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.service\_manager\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.service\_name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.service\_start\_name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.service\_type | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.share\_access | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.size | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.skipped | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.source\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.source\_process\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.source\_process\_identifier | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.stack\_zero\_bits | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.start\_type | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.status\_info | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.string | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.suspend\_count | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.suspended | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.target\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.target\_process\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.target\_process\_identifier | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.thread\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.thread\_identifier | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.thread\_name | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.type | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.value | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.view\_size | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.win32\_protect | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.category | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.allocation\_type | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.create\_disposition | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.create\_options | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.desired\_access | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.file\_attributes | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.hook\_identifier | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.index | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.information\_class | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.protection | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.reg\_type | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.share\_access | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.status\_info | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.win32\_protect | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.last\_error | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.nt\_status | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.return\_value | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.status | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.tid | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.time | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.command\_line | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.first\_seen | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.modules\.\*\.baseaddr | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.modules\.\*\.basename | string |  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.modules\.\*\.filepath | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.modules\.\*\.imgsize | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.pid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.ppid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.process\_name | string |  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.process\_path | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.tid | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.time | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.track | boolean | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.type | string | 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.command\_line | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.first\_seen | numeric | 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.pid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.ppid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.process\_name | string |  `file name` 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.track | boolean | 
action\_result\.data\.\*\.report\.behavior\.summary\.dll\_loaded | string | 
action\_result\.data\.\*\.report\.behavior\.summary\.file\_copied\.\* | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.summary\.file\_created | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.summary\.file\_exists | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.summary\.file\_opened | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.summary\.file\_read | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.summary\.file\_recreated | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.summary\.file\_written | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.summary\.mutex | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.summary\.regkey\_opened | string | 
action\_result\.data\.\*\.report\.behavior\.summary\.regkey\_read | string | 
action\_result\.data\.\*\.report\.behavior\.summary\.regkey\_written | string | 
action\_result\.data\.\*\.report\.debug\.cuckoo | string | 
action\_result\.data\.\*\.report\.debug\.log | string | 
action\_result\.data\.\*\.report\.dropped\.\*\.crc32 | string | 
action\_result\.data\.\*\.report\.dropped\.\*\.filepath | string |  `file path` 
action\_result\.data\.\*\.report\.dropped\.\*\.md5 | string |  `md5` 
action\_result\.data\.\*\.report\.dropped\.\*\.name | string | 
action\_result\.data\.\*\.report\.dropped\.\*\.path | string | 
action\_result\.data\.\*\.report\.dropped\.\*\.pids | numeric | 
action\_result\.data\.\*\.report\.dropped\.\*\.sha1 | string |  `sha1` 
action\_result\.data\.\*\.report\.dropped\.\*\.sha256 | string |  `sha256` 
action\_result\.data\.\*\.report\.dropped\.\*\.sha512 | string | 
action\_result\.data\.\*\.report\.dropped\.\*\.size | numeric | 
action\_result\.data\.\*\.report\.dropped\.\*\.type | string | 
action\_result\.data\.\*\.report\.info\.added | numeric | 
action\_result\.data\.\*\.report\.info\.category | string | 
action\_result\.data\.\*\.report\.info\.custom | string | 
action\_result\.data\.\*\.report\.info\.duration | numeric | 
action\_result\.data\.\*\.report\.info\.ended | numeric | 
action\_result\.data\.\*\.report\.info\.git\.fetch\_head | string | 
action\_result\.data\.\*\.report\.info\.git\.head | string | 
action\_result\.data\.\*\.report\.info\.id | numeric | 
action\_result\.data\.\*\.report\.info\.machine\.label | string | 
action\_result\.data\.\*\.report\.info\.machine\.manager | string | 
action\_result\.data\.\*\.report\.info\.machine\.name | string | 
action\_result\.data\.\*\.report\.info\.machine\.shutdown\_on | string | 
action\_result\.data\.\*\.report\.info\.machine\.started\_on | string | 
action\_result\.data\.\*\.report\.info\.machine\.status | string | 
action\_result\.data\.\*\.report\.info\.monitor | string |  `sha1` 
action\_result\.data\.\*\.report\.info\.options | string | 
action\_result\.data\.\*\.report\.info\.owner | string | 
action\_result\.data\.\*\.report\.info\.package | string | 
action\_result\.data\.\*\.report\.info\.platform | string | 
action\_result\.data\.\*\.report\.info\.route | string | 
action\_result\.data\.\*\.report\.info\.score | numeric | 
action\_result\.data\.\*\.report\.info\.started | numeric | 
action\_result\.data\.\*\.report\.info\.version | string | 
action\_result\.data\.\*\.report\.metadata\.output\.dropped\.\*\.basename | string | 
action\_result\.data\.\*\.report\.metadata\.output\.dropped\.\*\.dirname | string | 
action\_result\.data\.\*\.report\.metadata\.output\.dropped\.\*\.sha256 | string |  `sha256` 
action\_result\.data\.\*\.report\.metadata\.output\.pcap\.basename | string | 
action\_result\.data\.\*\.report\.metadata\.output\.pcap\.dirname | string | 
action\_result\.data\.\*\.report\.metadata\.output\.pcap\.sha256 | string |  `sha256` 
action\_result\.data\.\*\.report\.network\.dns\.\*\.answers\.\*\.data | string |  `ip` 
action\_result\.data\.\*\.report\.network\.dns\.\*\.answers\.\*\.type | string | 
action\_result\.data\.\*\.report\.network\.dns\.\*\.request | string | 
action\_result\.data\.\*\.report\.network\.dns\.\*\.type | string | 
action\_result\.data\.\*\.report\.network\.dns\_servers | string |  `ip` 
action\_result\.data\.\*\.report\.network\.domains\.\*\.domain | string |  `domain` 
action\_result\.data\.\*\.report\.network\.domains\.\*\.ip | string |  `ip` 
action\_result\.data\.\*\.report\.network\.hosts | string |  `ip` 
action\_result\.data\.\*\.report\.network\.pcap\_sha256 | string |  `sha256` 
action\_result\.data\.\*\.report\.network\.sorted\_pcap\_sha256 | string |  `sha256` 
action\_result\.data\.\*\.report\.network\.udp\.\*\.dport | numeric | 
action\_result\.data\.\*\.report\.network\.udp\.\*\.dst | string |  `ip` 
action\_result\.data\.\*\.report\.network\.udp\.\*\.offset | numeric | 
action\_result\.data\.\*\.report\.network\.udp\.\*\.sport | numeric | 
action\_result\.data\.\*\.report\.network\.udp\.\*\.src | string |  `ip` 
action\_result\.data\.\*\.report\.network\.udp\.\*\.time | numeric | 
action\_result\.data\.\*\.report\.screenshots\.\*\.ocr | string | 
action\_result\.data\.\*\.report\.screenshots\.\*\.path | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.description | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.families | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.markcount | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.api | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.allocation\_type | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.base\_address | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.desired\_access | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.display\_name | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.error\_control | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.filepath | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.filepath\_r | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.password | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.process\_handle | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.process\_identifier | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.protection | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.region\_size | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.service\_handle | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.service\_manager\_handle | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.service\_name | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.service\_start\_name | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.service\_type | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.start\_type | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.category | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.flags\.allocation\_type | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.flags\.protection | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.return\_value | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.status | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.tid | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.time | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.category | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.cid | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.description | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.entropy | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.filetype | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.ioc | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.language | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.name | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.offset | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.pid | numeric |  `pid` 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.section\.entropy | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.section\.name | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.section\.size\_of\_data | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.section\.virtual\_address | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.section\.virtual\_size | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.service\_name | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.service\_path | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.size | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.sublanguage | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.type | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.name | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.references | string |  `url` 
action\_result\.data\.\*\.report\.signatures\.\*\.severity | numeric | 
action\_result\.data\.\*\.report\.static\.imported\_dll\_count | numeric | 
action\_result\.data\.\*\.report\.static\.pe\_exports\.\*\.address | string | 
action\_result\.data\.\*\.report\.static\.pe\_exports\.\*\.name | string | 
action\_result\.data\.\*\.report\.static\.pe\_exports\.\*\.ordinal | numeric | 
action\_result\.data\.\*\.report\.static\.pe\_imphash | string |  `md5` 
action\_result\.data\.\*\.report\.static\.pe\_imports\.\*\.dll | string |  `file name` 
action\_result\.data\.\*\.report\.static\.pe\_imports\.\*\.imports\.\*\.address | string | 
action\_result\.data\.\*\.report\.static\.pe\_imports\.\*\.imports\.\*\.name | string | 
action\_result\.data\.\*\.report\.static\.pe\_resources\.\*\.filetype | string | 
action\_result\.data\.\*\.report\.static\.pe\_resources\.\*\.language | string | 
action\_result\.data\.\*\.report\.static\.pe\_resources\.\*\.name | string | 
action\_result\.data\.\*\.report\.static\.pe\_resources\.\*\.offset | string | 
action\_result\.data\.\*\.report\.static\.pe\_resources\.\*\.size | string | 
action\_result\.data\.\*\.report\.static\.pe\_resources\.\*\.sublanguage | string | 
action\_result\.data\.\*\.report\.static\.pe\_sections\.\*\.entropy | numeric | 
action\_result\.data\.\*\.report\.static\.pe\_sections\.\*\.name | string | 
action\_result\.data\.\*\.report\.static\.pe\_sections\.\*\.size\_of\_data | string | 
action\_result\.data\.\*\.report\.static\.pe\_sections\.\*\.virtual\_address | string | 
action\_result\.data\.\*\.report\.static\.pe\_sections\.\*\.virtual\_size | string | 
action\_result\.data\.\*\.report\.static\.pe\_timestamp | string | 
action\_result\.data\.\*\.report\.static\.pe\_versioninfo\.\*\.name | string | 
action\_result\.data\.\*\.report\.static\.pe\_versioninfo\.\*\.value | string |  `file name` 
action\_result\.data\.\*\.report\.strings | string | 
action\_result\.data\.\*\.report\.target\.category | string | 
action\_result\.data\.\*\.report\.target\.file\.crc32 | string | 
action\_result\.data\.\*\.report\.target\.file\.md5 | string |  `md5` 
action\_result\.data\.\*\.report\.target\.file\.name | string |  `file name` 
action\_result\.data\.\*\.report\.target\.file\.path | string | 
action\_result\.data\.\*\.report\.target\.file\.sha1 | string |  `sha1` 
action\_result\.data\.\*\.report\.target\.file\.sha256 | string |  `sha256` 
action\_result\.data\.\*\.report\.target\.file\.sha512 | string | 
action\_result\.data\.\*\.report\.target\.file\.size | numeric | 
action\_result\.data\.\*\.report\.target\.file\.type | string | 
action\_result\.data\.\*\.task\_status\.added\_on | string | 
action\_result\.data\.\*\.task\_status\.category | string | 
action\_result\.data\.\*\.task\_status\.clock | string | 
action\_result\.data\.\*\.task\_status\.completed\_on | string | 
action\_result\.data\.\*\.task\_status\.custom | string | 
action\_result\.data\.\*\.task\_status\.duration | numeric | 
action\_result\.data\.\*\.task\_status\.enforce\_timeout | boolean | 
action\_result\.data\.\*\.task\_status\.guest\.id | numeric | 
action\_result\.data\.\*\.task\_status\.guest\.label | string | 
action\_result\.data\.\*\.task\_status\.guest\.manager | string | 
action\_result\.data\.\*\.task\_status\.guest\.name | string | 
action\_result\.data\.\*\.task\_status\.guest\.shutdown\_on | string | 
action\_result\.data\.\*\.task\_status\.guest\.started\_on | string | 
action\_result\.data\.\*\.task\_status\.guest\.status | string | 
action\_result\.data\.\*\.task\_status\.guest\.task\_id | numeric | 
action\_result\.data\.\*\.task\_status\.id | numeric | 
action\_result\.data\.\*\.task\_status\.machine | string | 
action\_result\.data\.\*\.task\_status\.memory | boolean | 
action\_result\.data\.\*\.task\_status\.owner | string | 
action\_result\.data\.\*\.task\_status\.package | string | 
action\_result\.data\.\*\.task\_status\.platform | string | 
action\_result\.data\.\*\.task\_status\.priority | numeric | 
action\_result\.data\.\*\.task\_status\.route | string | 
action\_result\.data\.\*\.task\_status\.sample\.crc32 | string | 
action\_result\.data\.\*\.task\_status\.sample\.file\_size | numeric | 
action\_result\.data\.\*\.task\_status\.sample\.file\_type | string | 
action\_result\.data\.\*\.task\_status\.sample\.id | numeric | 
action\_result\.data\.\*\.task\_status\.sample\.md5 | string |  `md5` 
action\_result\.data\.\*\.task\_status\.sample\.sha1 | string |  `sha1` 
action\_result\.data\.\*\.task\_status\.sample\.sha256 | string |  `sha256` 
action\_result\.data\.\*\.task\_status\.sample\.sha512 | string | 
action\_result\.data\.\*\.task\_status\.sample\_id | numeric | 
action\_result\.data\.\*\.task\_status\.started\_on | string | 
action\_result\.data\.\*\.task\_status\.status | string | 
action\_result\.data\.\*\.task\_status\.target | string |  `file name` 
action\_result\.data\.\*\.task\_status\.timeout | numeric | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.id | string |  `cuckoo task id` 
action\_result\.summary\.results\_url | string |  `url` 
action\_result\.summary\.target | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'detonate url'
Load a URL in the Cuckoo sandbox and retrieve the analysis results

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  required  | URL to detonate | string |  `url`  `domain` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.url | string |  `url`  `domain` 
action\_result\.data\.\*\.report\.behavior\.apistats\.1432\.CoCreateInstance | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.1432\.CoGetClassObject | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.1432\.CoInitializeEx | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.1432\.CoInitializeSecurity | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.1432\.CoUninitialize | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.1432\.CreateProcessInternalW | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.1432\.LdrLoadDll | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.1432\.NtCreateFile | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.1432\.NtDelayExecution | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.1432\.NtOpenFile | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.1432\.NtWriteFile | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.1432\.OleInitialize | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.444\.PRF | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.552\.CImgElement\_put\_src | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.552\.COleScript\_Compile | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.552\.CWindow\_AddTimeoutCode | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.552\.CoCreateInstance | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.552\.CoGetClassObject | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.552\.CoInitializeEx | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.552\.CoInitializeSecurity | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.552\.CoUninitialize | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.552\.LdrLoadDll | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.552\.NtCreateFile | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.552\.NtDelayExecution | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.552\.NtOpenFile | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.552\.NtWriteFile | numeric | 
action\_result\.data\.\*\.report\.behavior\.apistats\.552\.OleInitialize | numeric | 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.first\_seen | numeric | 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.pid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.ppid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.process\_name | string |  `file name` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.process\_path | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.command\_line | string | 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.dll\_loaded | string |  `file name` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.file\_created | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.file\_failed | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.file\_opened | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.file\_recreated | string | 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.file\_written | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.guid | string | 
action\_result\.data\.\*\.report\.behavior\.generic\.\*\.summary\.tls\_master\.\* | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.api | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.argument | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.basename | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.buffer | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.class\_context | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.client\_random | string |  `sha256` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.clsid | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.code | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.command\_line | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.create\_disposition | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.create\_options | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.creation\_flags | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.current\_directory | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.desired\_access | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.file\_attributes | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.file\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.filepath | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.filepath\_r | string |  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.flags | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.iid | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.inherit\_handles | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.master\_secret | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.milliseconds | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.module\_address | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.module\_name | string |  `file name`  `file path` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.offset | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.open\_options | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.options | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.process\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.process\_identifier | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.repeat | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.script | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.server\_random | string |  `sha256` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.share\_access | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.skipped | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.src | string |  `url` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.status\_info | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.thread\_handle | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.thread\_identifier | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.track | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.arguments\.type | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.category | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.clsid | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.create\_disposition | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.create\_options | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.creation\_flags | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.desired\_access | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.file\_attributes | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.iid | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.open\_options | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.share\_access | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.flags\.status\_info | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.last\_error | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.nt\_status | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.raw | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.return\_value | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.status | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.tid | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.calls\.\*\.time | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.command\_line | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.first\_seen | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.modules\.\*\.baseaddr | string | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.modules\.\*\.basename | string |  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.modules\.\*\.filepath | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.modules\.\*\.imgsize | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.pid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.ppid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.process\_name | string |  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.process\_path | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.tid | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.time | numeric | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.track | boolean | 
action\_result\.data\.\*\.report\.behavior\.processes\.\*\.type | string | 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.children\.\*\.command\_line | string | 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.children\.\*\.first\_seen | numeric | 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.children\.\*\.pid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.children\.\*\.ppid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.children\.\*\.process\_name | string |  `file name` 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.children\.\*\.track | boolean | 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.command\_line | string |  `file path`  `file name` 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.first\_seen | numeric | 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.pid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.ppid | numeric |  `pid` 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.process\_name | string |  `file name` 
action\_result\.data\.\*\.report\.behavior\.processtree\.\*\.track | boolean | 
action\_result\.data\.\*\.report\.behavior\.summary\.command\_line | string | 
action\_result\.data\.\*\.report\.behavior\.summary\.dll\_loaded | string |  `file name` 
action\_result\.data\.\*\.report\.behavior\.summary\.file\_created | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.summary\.file\_failed | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.summary\.file\_opened | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.summary\.file\_recreated | string | 
action\_result\.data\.\*\.report\.behavior\.summary\.file\_written | string |  `file path` 
action\_result\.data\.\*\.report\.behavior\.summary\.guid | string | 
action\_result\.data\.\*\.report\.behavior\.summary\.tls\_master\.\* | string | 
action\_result\.data\.\*\.report\.debug\.cuckoo | string | 
action\_result\.data\.\*\.report\.debug\.log | string | 
action\_result\.data\.\*\.report\.dropped\.\*\.crc32 | string | 
action\_result\.data\.\*\.report\.dropped\.\*\.filepath | string |  `file path` 
action\_result\.data\.\*\.report\.dropped\.\*\.md5 | string |  `md5` 
action\_result\.data\.\*\.report\.dropped\.\*\.name | string | 
action\_result\.data\.\*\.report\.dropped\.\*\.path | string | 
action\_result\.data\.\*\.report\.dropped\.\*\.pids | numeric | 
action\_result\.data\.\*\.report\.dropped\.\*\.sha1 | string |  `sha1` 
action\_result\.data\.\*\.report\.dropped\.\*\.sha256 | string |  `sha256` 
action\_result\.data\.\*\.report\.dropped\.\*\.sha512 | string | 
action\_result\.data\.\*\.report\.dropped\.\*\.size | numeric | 
action\_result\.data\.\*\.report\.dropped\.\*\.type | string | 
action\_result\.data\.\*\.report\.dropped\.\*\.urls | string |  `url` 
action\_result\.data\.\*\.report\.info\.added | numeric | 
action\_result\.data\.\*\.report\.info\.category | string | 
action\_result\.data\.\*\.report\.info\.custom | string | 
action\_result\.data\.\*\.report\.info\.duration | numeric | 
action\_result\.data\.\*\.report\.info\.ended | numeric | 
action\_result\.data\.\*\.report\.info\.git\.fetch\_head | string | 
action\_result\.data\.\*\.report\.info\.git\.head | string | 
action\_result\.data\.\*\.report\.info\.id | numeric | 
action\_result\.data\.\*\.report\.info\.machine\.label | string | 
action\_result\.data\.\*\.report\.info\.machine\.manager | string | 
action\_result\.data\.\*\.report\.info\.machine\.name | string | 
action\_result\.data\.\*\.report\.info\.machine\.shutdown\_on | string | 
action\_result\.data\.\*\.report\.info\.machine\.started\_on | string | 
action\_result\.data\.\*\.report\.info\.machine\.status | string | 
action\_result\.data\.\*\.report\.info\.monitor | string |  `sha1` 
action\_result\.data\.\*\.report\.info\.options | string | 
action\_result\.data\.\*\.report\.info\.owner | string | 
action\_result\.data\.\*\.report\.info\.package | string | 
action\_result\.data\.\*\.report\.info\.platform | string | 
action\_result\.data\.\*\.report\.info\.route | string | 
action\_result\.data\.\*\.report\.info\.score | numeric | 
action\_result\.data\.\*\.report\.info\.started | numeric | 
action\_result\.data\.\*\.report\.info\.version | string | 
action\_result\.data\.\*\.report\.metadata\.output\.dropped\.\*\.basename | string | 
action\_result\.data\.\*\.report\.metadata\.output\.dropped\.\*\.dirname | string | 
action\_result\.data\.\*\.report\.metadata\.output\.dropped\.\*\.sha256 | string |  `sha256` 
action\_result\.data\.\*\.report\.metadata\.output\.pcap\.basename | string | 
action\_result\.data\.\*\.report\.metadata\.output\.pcap\.dirname | string | 
action\_result\.data\.\*\.report\.metadata\.output\.pcap\.sha256 | string |  `sha256` 
action\_result\.data\.\*\.report\.network\.dns\.\*\.answers\.\*\.data | string |  `ip` 
action\_result\.data\.\*\.report\.network\.dns\.\*\.answers\.\*\.type | string | 
action\_result\.data\.\*\.report\.network\.dns\.\*\.request | string | 
action\_result\.data\.\*\.report\.network\.dns\.\*\.type | string | 
action\_result\.data\.\*\.report\.network\.dns\_servers | string |  `ip` 
action\_result\.data\.\*\.report\.network\.domains\.\*\.domain | string |  `domain` 
action\_result\.data\.\*\.report\.network\.domains\.\*\.ip | string |  `ip` 
action\_result\.data\.\*\.report\.network\.hosts | string |  `ip` 
action\_result\.data\.\*\.report\.network\.http\.\*\.body | string | 
action\_result\.data\.\*\.report\.network\.http\.\*\.count | numeric | 
action\_result\.data\.\*\.report\.network\.http\.\*\.data | string | 
action\_result\.data\.\*\.report\.network\.http\.\*\.host | string | 
action\_result\.data\.\*\.report\.network\.http\.\*\.method | string | 
action\_result\.data\.\*\.report\.network\.http\.\*\.path | string | 
action\_result\.data\.\*\.report\.network\.http\.\*\.port | numeric | 
action\_result\.data\.\*\.report\.network\.http\.\*\.uri | string |  `url` 
action\_result\.data\.\*\.report\.network\.http\.\*\.user\-agent | string | 
action\_result\.data\.\*\.report\.network\.http\.\*\.version | string | 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.dport | numeric | 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.dst | string |  `ip` 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.host | string | 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.md5 | string |  `md5` 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.method | string | 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.path | string | 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.protocol | string |  `url` 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.req\.md5 | string |  `md5` 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.req\.path | string | 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.req\.sha1 | string |  `sha1` 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.request | string | 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.resp\.md5 | string |  `md5` 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.resp\.path | string | 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.resp\.sha1 | string |  `sha1` 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.response | string | 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.sha1 | string |  `sha1` 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.sport | numeric | 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.src | string |  `ip` 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.status | numeric | 
action\_result\.data\.\*\.report\.network\.http\_ex\.\*\.uri | string | 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.dport | numeric | 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.dst | string |  `ip` 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.host | string | 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.md5 | string |  `md5` 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.method | string | 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.path | string | 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.protocol | string |  `url` 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.req\.md5 | string |  `md5` 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.req\.path | string | 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.req\.sha1 | string |  `sha1` 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.request | string | 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.resp\.md5 | string |  `md5` 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.resp\.path | string | 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.resp\.sha1 | string |  `sha1` 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.response | string | 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.sha1 | string |  `sha1` 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.sport | numeric | 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.src | string |  `ip` 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.status | numeric | 
action\_result\.data\.\*\.report\.network\.https\_ex\.\*\.uri | string | 
action\_result\.data\.\*\.report\.network\.pcap\_sha256 | string |  `sha256` 
action\_result\.data\.\*\.report\.network\.sorted\_pcap\_sha256 | string |  `sha256` 
action\_result\.data\.\*\.report\.network\.tcp\.\*\.dport | numeric | 
action\_result\.data\.\*\.report\.network\.tcp\.\*\.dst | string |  `ip` 
action\_result\.data\.\*\.report\.network\.tcp\.\*\.offset | numeric | 
action\_result\.data\.\*\.report\.network\.tcp\.\*\.sport | numeric | 
action\_result\.data\.\*\.report\.network\.tcp\.\*\.src | string |  `ip` 
action\_result\.data\.\*\.report\.network\.tcp\.\*\.time | numeric | 
action\_result\.data\.\*\.report\.network\.tls\.\*\.server\_random | string |  `sha256` 
action\_result\.data\.\*\.report\.network\.tls\.\*\.session\_id | string |  `sha256` 
action\_result\.data\.\*\.report\.network\.udp\.\*\.dport | numeric | 
action\_result\.data\.\*\.report\.network\.udp\.\*\.dst | string |  `ip` 
action\_result\.data\.\*\.report\.network\.udp\.\*\.offset | numeric | 
action\_result\.data\.\*\.report\.network\.udp\.\*\.sport | numeric | 
action\_result\.data\.\*\.report\.network\.udp\.\*\.src | string |  `ip` 
action\_result\.data\.\*\.report\.network\.udp\.\*\.time | numeric | 
action\_result\.data\.\*\.report\.screenshots\.\*\.ocr | string | 
action\_result\.data\.\*\.report\.screenshots\.\*\.path | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.description | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.markcount | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.api | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.script | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.arguments\.type | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.category | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.raw | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.return\_value | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.status | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.tid | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.call\.time | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.category | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.cid | numeric | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.ioc | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.pid | numeric |  `pid` 
action\_result\.data\.\*\.report\.signatures\.\*\.marks\.\*\.type | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.name | string | 
action\_result\.data\.\*\.report\.signatures\.\*\.severity | numeric | 
action\_result\.data\.\*\.report\.target\.category | string | 
action\_result\.data\.\*\.report\.target\.url | string |  `url` 
action\_result\.data\.\*\.task\_status\.added\_on | string | 
action\_result\.data\.\*\.task\_status\.category | string | 
action\_result\.data\.\*\.task\_status\.clock | string | 
action\_result\.data\.\*\.task\_status\.completed\_on | string | 
action\_result\.data\.\*\.task\_status\.custom | string | 
action\_result\.data\.\*\.task\_status\.duration | numeric | 
action\_result\.data\.\*\.task\_status\.enforce\_timeout | boolean | 
action\_result\.data\.\*\.task\_status\.guest\.id | numeric | 
action\_result\.data\.\*\.task\_status\.guest\.label | string | 
action\_result\.data\.\*\.task\_status\.guest\.manager | string | 
action\_result\.data\.\*\.task\_status\.guest\.name | string | 
action\_result\.data\.\*\.task\_status\.guest\.shutdown\_on | string | 
action\_result\.data\.\*\.task\_status\.guest\.started\_on | string | 
action\_result\.data\.\*\.task\_status\.guest\.status | string | 
action\_result\.data\.\*\.task\_status\.guest\.task\_id | numeric | 
action\_result\.data\.\*\.task\_status\.id | numeric | 
action\_result\.data\.\*\.task\_status\.machine | string | 
action\_result\.data\.\*\.task\_status\.memory | boolean | 
action\_result\.data\.\*\.task\_status\.owner | string | 
action\_result\.data\.\*\.task\_status\.package | string | 
action\_result\.data\.\*\.task\_status\.platform | string | 
action\_result\.data\.\*\.task\_status\.priority | numeric | 
action\_result\.data\.\*\.task\_status\.route | string | 
action\_result\.data\.\*\.task\_status\.started\_on | string | 
action\_result\.data\.\*\.task\_status\.status | string | 
action\_result\.data\.\*\.task\_status\.target | string |  `url` 
action\_result\.data\.\*\.task\_status\.timeout | numeric | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.id | numeric |  `cuckoo task id` 
action\_result\.summary\.results\_url | string |  `url` 
action\_result\.summary\.target | string |  `url` 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'submit strings'
Add VirusTotal compatible URL/Domain to the list of pending tasks

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** |  required  | Single VirusTotal compatible URL/Domain | string |  `url`  `domain` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.url | string |  `url`  `domain` 
action\_result\.data\.\*\.task\_status\.started\_on | string | 
action\_result\.data\.\*\.task\_status\.sample\.sha1 | string |  `sha1` 
action\_result\.data\.\*\.task\_status\.sample\.file\_type | string | 
action\_result\.data\.\*\.task\_status\.sample\.file\_size | numeric | 
action\_result\.data\.\*\.task\_status\.sample\.crc32 | string | 
action\_result\.data\.\*\.task\_status\.sample\.ssdeep | string | 
action\_result\.data\.\*\.task\_status\.sample\.sha256 | string |  `sha256` 
action\_result\.data\.\*\.task\_status\.sample\.sha512 | string | 
action\_result\.data\.\*\.task\_status\.sample\.id | numeric | 
action\_result\.data\.\*\.task\_status\.sample\.md5 | string |  `md5` 
action\_result\.data\.\*\.task\_status\.owner | string | 
action\_result\.data\.\*\.task\_status\.sample\_id | numeric | 
action\_result\.data\.\*\.task\_status\.duration | numeric | 
action\_result\.data\.\*\.task\_status\.id | numeric | 
action\_result\.data\.\*\.task\_status\.category | string | 
action\_result\.data\.\*\.task\_status\.machine | string | 
action\_result\.data\.\*\.task\_status\.clock | string | 
action\_result\.data\.\*\.task\_status\.custom | string | 
action\_result\.data\.\*\.task\_status\.priority | numeric | 
action\_result\.data\.\*\.task\_status\.platform | string | 
action\_result\.data\.\*\.task\_status\.memory | boolean | 
action\_result\.data\.\*\.task\_status\.status | string | 
action\_result\.data\.\*\.task\_status\.processing | string | 
action\_result\.data\.\*\.task\_status\.enforce\_timeout | boolean | 
action\_result\.data\.\*\.task\_status\.target | string |  `url` 
action\_result\.data\.\*\.task\_status\.completed\_on | string | 
action\_result\.data\.\*\.task\_status\.package | string | 
action\_result\.data\.\*\.task\_status\.route | string | 
action\_result\.data\.\*\.task\_status\.timeout | numeric | 
action\_result\.data\.\*\.task\_status\.submit\_id | numeric | 
action\_result\.data\.\*\.task\_status\.options\.procmemdump | string | 
action\_result\.data\.\*\.task\_status\.added\_on | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary\.id | numeric | 
action\_result\.summary\.target | string | 
action\_result\.summary\.results\_url | string |  `url` 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 