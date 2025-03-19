# Cuckoo

Publisher: Splunk Community \
Connector Version: 2.2.1 \
Product Vendor: Cuckoo \
Product Name: Cuckoo \
Minimum Product Version: 5.0.0

This app supports executing various investigative and generic actions on the Cuckoo sandbox

### Configuration variables

This table lists the configuration variables required to operate Cuckoo. These variables are specified when configuring a Cuckoo asset in Splunk SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**server** | required | string | Server IP/Hostname |
**port** | required | string | REST API Port |
**use_https** | optional | boolean | Connect with HTTPS |
**verify_server_cert** | optional | boolean | Verify server certificate |
**timeout** | required | numeric | Timeout (seconds) |
**username** | optional | string | HTTP Basic Auth Username |
**password** | optional | password | HTTP Basic Auth Password |
**append_uri** | optional | string | Additional URI Path to Add to the Server |
**web_ui_base_url** | optional | string | Base URL to the Web Interface (e.g. https://10.16.6.42:8000/) |

### Supported Actions

[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration \
[detonate file](#action-detonate-file) - Run the file in the sandbox and retrieve the analysis results \
[get report](#action-get-report) - Query for results of an already completed detonation \
[detonate url](#action-detonate-url) - Load a URL in the Cuckoo sandbox and retrieve the analysis results \
[submit strings](#action-submit-strings) - Add VirusTotal compatible URL/Domain to the list of pending tasks

## action: 'test connectivity'

Validate the asset configuration for connectivity using supplied configuration

Type: **test** \
Read only: **True**

#### Action Parameters

No parameters are required for this action

#### Action Output

No Output

## action: 'detonate file'

Run the file in the sandbox and retrieve the analysis results

Type: **generic** \
Read only: **False**

#### Action Parameters

PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**vault_id** | required | Vault ID of file to detonate | string | `vault id` `sha1` |
**file_name** | optional | Filename to use | string | `file name` |
**zip_and_encrypt** | optional | Option to zip and encrypt file, WARNING: password visible as zip command line argument | boolean | |

#### Action Output

DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.file_name | string | `file name` | |
action_result.parameter.vault_id | string | `vault id` `sha1` | ac8682258ec2a9556c5b06dac4b70aa7f408146b |
action_result.parameter.zip_and_encrypt | string | | |
action_result.data.\*.report.behavior.apistats.984.CopyFileA | numeric | | 2 |
action_result.data.\*.report.behavior.apistats.984.CreateServiceA | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.FindResourceExW | numeric | | 16 |
action_result.data.\*.report.behavior.apistats.984.GetFileAttributesW | numeric | | 3 |
action_result.data.\*.report.behavior.apistats.984.GetFileSize | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.GetFileType | numeric | | 7 |
action_result.data.\*.report.behavior.apistats.984.GetSystemInfo | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.GetSystemMetrics | numeric | | 4 |
action_result.data.\*.report.behavior.apistats.984.GetSystemTimeAsFileTime | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.GetSystemWindowsDirectoryW | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.GetTempPathW | numeric | | 2 |
action_result.data.\*.report.behavior.apistats.984.GetTimeZoneInformation | numeric | | 2 |
action_result.data.\*.report.behavior.apistats.984.LdrGetDllHandle | numeric | | 7 |
action_result.data.\*.report.behavior.apistats.984.LdrGetProcedureAddress | numeric | | 548 |
action_result.data.\*.report.behavior.apistats.984.LdrLoadDll | numeric | | 35 |
action_result.data.\*.report.behavior.apistats.984.LoadResource | numeric | | 14 |
action_result.data.\*.report.behavior.apistats.984.LoadStringA | numeric | | 49 |
action_result.data.\*.report.behavior.apistats.984.NtAllocateVirtualMemory | numeric | | 14 |
action_result.data.\*.report.behavior.apistats.984.NtClose | numeric | | 17 |
action_result.data.\*.report.behavior.apistats.984.NtCreateFile | numeric | | 8 |
action_result.data.\*.report.behavior.apistats.984.NtCreateMutant | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.NtCreateSection | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.NtCreateThreadEx | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.NtDelayExecution | numeric | | 71680 |
action_result.data.\*.report.behavior.apistats.984.NtDuplicateObject | numeric | | 2 |
action_result.data.\*.report.behavior.apistats.984.NtFreeVirtualMemory | numeric | | 2 |
action_result.data.\*.report.behavior.apistats.984.NtMapViewOfSection | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.NtOpenKey | numeric | | 2 |
action_result.data.\*.report.behavior.apistats.984.NtOpenMutant | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.NtProtectVirtualMemory | numeric | | 4 |
action_result.data.\*.report.behavior.apistats.984.NtQueryAttributesFile | numeric | | 4 |
action_result.data.\*.report.behavior.apistats.984.NtQueryInformationFile | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.NtQueryValueKey | numeric | | 2 |
action_result.data.\*.report.behavior.apistats.984.NtReadFile | numeric | | 22 |
action_result.data.\*.report.behavior.apistats.984.NtResumeThread | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.NtWriteFile | numeric | | 22 |
action_result.data.\*.report.behavior.apistats.984.OpenSCManagerA | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.OutputDebugStringA | numeric | | 3 |
action_result.data.\*.report.behavior.apistats.984.RegCloseKey | numeric | | 5 |
action_result.data.\*.report.behavior.apistats.984.RegOpenKeyExA | numeric | | 7 |
action_result.data.\*.report.behavior.apistats.984.RegOpenKeyExW | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.RegQueryValueExA | numeric | | 3 |
action_result.data.\*.report.behavior.apistats.984.RegQueryValueExW | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.RegSetValueExA | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.SetEndOfFile | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.SetFileAttributesW | numeric | | 2 |
action_result.data.\*.report.behavior.apistats.984.SetFilePointer | numeric | | 10 |
action_result.data.\*.report.behavior.apistats.984.SetFileTime | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.SetUnhandledExceptionFilter | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.SetWindowsHookExA | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.StartServiceA | numeric | | 1 |
action_result.data.\*.report.behavior.generic.\*.first_seen | numeric | | 1509432420.046875 |
action_result.data.\*.report.behavior.generic.\*.pid | numeric | `pid` | 984 |
action_result.data.\*.report.behavior.generic.\*.ppid | numeric | `pid` | 1104 |
action_result.data.\*.report.behavior.generic.\*.process_name | string | `file name` | Mh.exe |
action_result.data.\*.report.behavior.generic.\*.process_path | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.generic.\*.summary.dll_loaded | string | | COMCTL32.DLL |
action_result.data.\*.report.behavior.generic.\*.summary.file_copied.\* | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\aul9806.tmp |
action_result.data.\*.report.behavior.generic.\*.summary.file_created | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\aul9806.tmp |
action_result.data.\*.report.behavior.generic.\*.summary.file_exists | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp |
action_result.data.\*.report.behavior.generic.\*.summary.file_opened | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.generic.\*.summary.file_read | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.generic.\*.summary.file_recreated | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\rql71B0.tmp |
action_result.data.\*.report.behavior.generic.\*.summary.file_written | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\aul9806.tmp |
action_result.data.\*.report.behavior.generic.\*.summary.mutex | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.generic.\*.summary.regkey_opened | string | | HKEY_CURRENT_USER\\Software\\Borland\\Delphi\\Locales |
action_result.data.\*.report.behavior.generic.\*.summary.regkey_read | string | | HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Security_HKLM_only |
action_result.data.\*.report.behavior.generic.\*.summary.regkey_written | string | | HKEY_LOCAL_MACHINE\\SYSTEM\\ControlSet001\\services\\Abcdef Hijklmno Qrs\\Description |
action_result.data.\*.report.behavior.processes.\*.calls.\*.api | string | | LdrLoadDll |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.access | string | | 0x00020019 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.allocation_type | numeric | | 8192 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.base_address | string | | 0x01e30000 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.base_handle | string | | 0x80000001 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.basename | string | | Kernel32 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.buffer | string | | |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.callback_function | string | | 0x00451ebc |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.commit_size | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.create_disposition | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.create_options | numeric | | 96 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.database_name | string | | |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.desired_access | string | | 0x80100080 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.dirpath | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\ |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.display_name | string | | Abcdef Hijklmno Qrstuvwx Abcd |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.error_control | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.fail_if_exists | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.file_attributes | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.file_handle | string | | 0x0000006c |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.file_size_low | numeric | | 420314 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.filepath | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.filepath_r | string | `file name` `file path` | \\??\\C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.flags | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.free_type | numeric | | 32768 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.function_address | string | | 0x77031410 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.function_name | string | | CloseHandle |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.handle | string | | 0x00000070 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.handle_attributes | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.hook_identifier | numeric | | 4 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.id | numeric | | 65398 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.index | numeric | | 74 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.information_class | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.initial_owner | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.key_handle | string | | 0x0000006c |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.key_name | string | | |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.language_identifier | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.length | numeric | | 10240 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.machine_name | string | | |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.milliseconds | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.module | string | `file name` | kernel32 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.module_address | string | | 0x77020000 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.module_handle | string | | 0x00450000 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.module_name | string | `file name` `file path` | Kernel32.dll |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.move_method | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.mutant_handle | string | | 0x00000000 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.mutant_name | string | `file path` `file name` | Residented |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.name | string | | #12 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.newfilepath | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\aul9806.tmp |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.newfilepath_r | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\aul9806.tmp |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.object_handle | string | | 0x00000000 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.offset | numeric | | 244186 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.oldfilepath | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.oldfilepath_r | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.options | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.ordinal | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.parameter | string | | 0x005d4c10 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.password | string | | |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.pointer | string | | 0x004b5da0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.process_handle | string | | 0xffffffff |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.process_identifier | numeric | | 984 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.processor_count | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.protection | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.reg_type | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.region_size | numeric | | 1048576 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.regkey | string | | HKEY_CURRENT_USER\\Software\\Microsoft\\Windows\\CurrentVersion\\Explorer |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.regkey_r | string | | Software\\Microsoft\\Windows\\CurrentVersion\\Explorer |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.resource_handle | string | | 0x004c24b0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.section_handle | string | | 0x000000a4 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.section_name | string | | |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.section_offset | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.service_handle | string | | 0x005d1dd0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.service_manager_handle | string | | 0x005d1e70 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.service_name | string | | Abcdef Hijklmno Qrs |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.service_start_name | string | | |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.service_type | numeric | | 272 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.share_access | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.size | numeric | | 1835008 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.skipped | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.source_handle | string | | 0x00000100 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.source_process_handle | string | | 0xffffffff |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.source_process_identifier | numeric | | 984 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.stack_zero_bits | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.start_type | numeric | | 2 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.status_info | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.string | string | | Exception in safecall method |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.suspend_count | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.suspended | numeric | | 3 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.target_handle | string | | 0x00000104 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.target_process_handle | string | | 0xffffffff |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.target_process_identifier | numeric | | 984 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.thread_handle | string | | 0x00000100 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.thread_identifier | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.thread_name | string | | 0x0018ec1c |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.type | string | | #32761 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.value | string | | |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.view_size | numeric | | 2945024 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.win32_protect | numeric | | 2 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.category | string | | system |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.allocation_type | string | | MEM_RESERVE |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.create_disposition | string | | FILE_OPEN |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.create_options | string | | FILE_NON_DIRECTORY_FILE|FILE_SYNCHRONOUS_IO_NONALERT |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.desired_access | string | | FILE_READ_ATTRIBUTES|SYNCHRONIZE |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.file_attributes | string | | FILE_ATTRIBUTE_READONLY |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.hook_identifier | string | | WH_CALLWNDPROC |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.index | string | | SM_MIDEASTENABLED |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.information_class | string | | KeyValueFullInformation |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.protection | string | | PAGE_NOACCESS |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.reg_type | string | | REG_NONE |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.share_access | string | | FILE_SHARE_READ |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.status_info | string | | FILE_OPENED |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.win32_protect | string | | PAGE_READONLY |
action_result.data.\*.report.behavior.processes.\*.calls.\*.last_error | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.nt_status | numeric | | -1073741772 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.return_value | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.status | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.tid | numeric | | 800 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.time | numeric | | 1509432420.530875 |
action_result.data.\*.report.behavior.processes.\*.command_line | string | `file path` `file name` | C:\\Windows\\system32\\lsass.exe |
action_result.data.\*.report.behavior.processes.\*.first_seen | numeric | | 1509432418.0625 |
action_result.data.\*.report.behavior.processes.\*.modules.\*.baseaddr | string | | 0xff180000 |
action_result.data.\*.report.behavior.processes.\*.modules.\*.basename | string | `file name` | lsass.exe |
action_result.data.\*.report.behavior.processes.\*.modules.\*.filepath | string | `file path` `file name` | C:\\Windows\\system32\\lsass.exe |
action_result.data.\*.report.behavior.processes.\*.modules.\*.imgsize | numeric | | 49152 |
action_result.data.\*.report.behavior.processes.\*.pid | numeric | `pid` | 444 |
action_result.data.\*.report.behavior.processes.\*.ppid | numeric | `pid` | 340 |
action_result.data.\*.report.behavior.processes.\*.process_name | string | `file name` | lsass.exe |
action_result.data.\*.report.behavior.processes.\*.process_path | string | `file path` `file name` | C:\\Windows\\System32\\lsass.exe |
action_result.data.\*.report.behavior.processes.\*.tid | numeric | | 1604 |
action_result.data.\*.report.behavior.processes.\*.time | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.track | boolean | | True False |
action_result.data.\*.report.behavior.processes.\*.type | string | | process |
action_result.data.\*.report.behavior.processtree.\*.command_line | string | `file path` `file name` | C:\\Windows\\system32\\lsass.exe |
action_result.data.\*.report.behavior.processtree.\*.first_seen | numeric | | 1509432418.0625 |
action_result.data.\*.report.behavior.processtree.\*.pid | numeric | `pid` | 444 |
action_result.data.\*.report.behavior.processtree.\*.ppid | numeric | `pid` | 340 |
action_result.data.\*.report.behavior.processtree.\*.process_name | string | `file name` | lsass.exe |
action_result.data.\*.report.behavior.processtree.\*.track | boolean | | True False |
action_result.data.\*.report.behavior.summary.dll_loaded | string | | COMCTL32.DLL |
action_result.data.\*.report.behavior.summary.file_copied.\* | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\aul9806.tmp |
action_result.data.\*.report.behavior.summary.file_created | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\aul9806.tmp |
action_result.data.\*.report.behavior.summary.file_exists | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp |
action_result.data.\*.report.behavior.summary.file_opened | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.summary.file_read | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.summary.file_recreated | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\rql71B0.tmp |
action_result.data.\*.report.behavior.summary.file_written | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\aul9806.tmp |
action_result.data.\*.report.behavior.summary.mutex | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.summary.regkey_opened | string | | HKEY_CURRENT_USER\\Software\\Borland\\Delphi\\Locales |
action_result.data.\*.report.behavior.summary.regkey_read | string | | HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Security_HKLM_only |
action_result.data.\*.report.behavior.summary.regkey_written | string | | HKEY_LOCAL_MACHINE\\SYSTEM\\ControlSet001\\services\\Abcdef Hijklmno Qrs\\Description |
action_result.data.\*.report.debug.cuckoo | string | | 2017-10-30 23:49:15,341 [cuckoo.core.plugins] DEBUG: Analysis matched signature: pe_features |
action_result.data.\*.report.debug.log | string | | 2017-10-30 23:48:59,125 [analyzer] INFO: Analysis completed. |
action_result.data.\*.report.dropped.\*.crc32 | string | | CB1602FC |
action_result.data.\*.report.dropped.\*.filepath | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\rql71B0.tmp |
action_result.data.\*.report.dropped.\*.md5 | string | `md5` | 685f1cbd4af30a1d0c25f252d399a666 |
action_result.data.\*.report.dropped.\*.name | string | | 0e478c95a7a07570_rql71b0.tmp |
action_result.data.\*.report.dropped.\*.path | string | | /home/cuckoo/.cuckoo/storage/analyses/27/files/0e478c95a7a07570_rql71b0.tmp |
action_result.data.\*.report.dropped.\*.pids | numeric | | 984 |
action_result.data.\*.report.dropped.\*.sha1 | string | `sha1` | 6a1b978f5e6150b88c8634146f1406ed97d2f134 |
action_result.data.\*.report.dropped.\*.sha256 | string | `sha256` | 0e478c95a7a07570a69e6061e7c1da9001bccad9cc454f2ed4da58824a13e0f4 |
action_result.data.\*.report.dropped.\*.sha512 | string | | 6555ad6b4f4f26105ca8aad64501d74519a3e091f559b4b563d6ffb20a2ddfcde65e4fe94971a9bc65e86db577f2548ca00f9920d341c8ea808b04c0947d61d9 |
action_result.data.\*.report.dropped.\*.size | numeric | | 176128 |
action_result.data.\*.report.dropped.\*.type | string | | PE32 executable (DLL) (GUI) Intel 80386 (stripped to external PDB), for MS Windows |
action_result.data.\*.report.info.added | numeric | | 1509407217.087696 |
action_result.data.\*.report.info.category | string | | file |
action_result.data.\*.report.info.custom | string | | |
action_result.data.\*.report.info.duration | numeric | | 132 |
action_result.data.\*.report.info.ended | numeric | | 1509407349.736956 |
action_result.data.\*.report.info.git.fetch_head | string | | |
action_result.data.\*.report.info.git.head | string | | |
action_result.data.\*.report.info.id | numeric | | 27 |
action_result.data.\*.report.info.machine.label | string | | cuckoo2 |
action_result.data.\*.report.info.machine.manager | string | | VirtualBox |
action_result.data.\*.report.info.machine.name | string | | cuckoo2 |
action_result.data.\*.report.info.machine.shutdown_on | string | | 2017-10-30 23:49:09 |
action_result.data.\*.report.info.machine.started_on | string | | 2017-10-30 23:46:57 |
action_result.data.\*.report.info.machine.status | string | | stopped |
action_result.data.\*.report.info.monitor | string | `sha1` | 2bd01ede5c5258d5fce2e38bc58348a62c11ce33 |
action_result.data.\*.report.info.options | string | | |
action_result.data.\*.report.info.owner | string | | |
action_result.data.\*.report.info.package | string | | |
action_result.data.\*.report.info.platform | string | | |
action_result.data.\*.report.info.route | string | | none |
action_result.data.\*.report.info.score | numeric | | 3 |
action_result.data.\*.report.info.started | numeric | | 1509407217.208121 |
action_result.data.\*.report.info.version | string | | 2.0.3 |
action_result.data.\*.report.metadata.output.dropped.\*.basename | string | | 0e478c95a7a07570_rql71b0.tmp |
action_result.data.\*.report.metadata.output.dropped.\*.dirname | string | | files |
action_result.data.\*.report.metadata.output.dropped.\*.sha256 | string | `sha256` | 0e478c95a7a07570a69e6061e7c1da9001bccad9cc454f2ed4da58824a13e0f4 |
action_result.data.\*.report.metadata.output.pcap.basename | string | | dump.pcap |
action_result.data.\*.report.metadata.output.pcap.dirname | string | | |
action_result.data.\*.report.metadata.output.pcap.sha256 | string | `sha256` | 08d4daf8f1d393aa6cceff4235dc666465f49cbe3c01a9aea9f7e4c8e9be8c43 |
action_result.data.\*.report.network.dns.\*.answers.\*.data | string | `ip` | 120.210.207.151 |
action_result.data.\*.report.network.dns.\*.answers.\*.type | string | | A |
action_result.data.\*.report.network.dns.\*.request | string | | zebing520.vicp.cc |
action_result.data.\*.report.network.dns.\*.type | string | | A |
action_result.data.\*.report.network.dns_servers | string | `ip` | 8.8.8.8 |
action_result.data.\*.report.network.domains.\*.domain | string | `domain` | teredo.ipv6.microsoft.com |
action_result.data.\*.report.network.domains.\*.ip | string | `ip` | |
action_result.data.\*.report.network.hosts | string | `ip` | 72.21.91.29 |
action_result.data.\*.report.network.pcap_sha256 | string | `sha256` | 08d4daf8f1d393aa6cceff4235dc666465f49cbe3c01a9aea9f7e4c8e9be8c43 |
action_result.data.\*.report.network.sorted_pcap_sha256 | string | `sha256` | 819ac5fcbe6aa7f4d49795a5c0c47bf52feb3be3d24b47c28e79a7ecd9eba9c4 |
action_result.data.\*.report.network.udp.\*.dport | numeric | | 5355 |
action_result.data.\*.report.network.udp.\*.dst | string | `ip` | 224.0.0.252 |
action_result.data.\*.report.network.udp.\*.offset | numeric | | 1822 |
action_result.data.\*.report.network.udp.\*.sport | numeric | | 51966 |
action_result.data.\*.report.network.udp.\*.src | string | `ip` | 192.168.56.11 |
action_result.data.\*.report.network.udp.\*.time | numeric | | 6.255922079086304 |
action_result.data.\*.report.screenshots.\*.ocr | string | | |
action_result.data.\*.report.screenshots.\*.path | string | | /home/cuckoo/.cuckoo/storage/analyses/27/shots/0001.jpg |
action_result.data.\*.report.signatures.\*.description | string | | The executable contains unknown PE section names indicative of a packer (could be a false positive) |
action_result.data.\*.report.signatures.\*.families | string | | nitol |
action_result.data.\*.report.signatures.\*.markcount | numeric | | 1 |
action_result.data.\*.report.signatures.\*.marks.\*.call.api | string | | NtAllocateVirtualMemory |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.allocation_type | numeric | | 4096 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.base_address | string | | 0x004e0000 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.desired_access | numeric | | 983551 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.display_name | string | | Abcdef Hijklmno Qrstuvwx Abcd |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.error_control | numeric | | 0 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.filepath | string | `file path` `file name` | C:\\Windows\\update.exe |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.filepath_r | string | `file path` `file name` | C:\\Windows\\update.exe |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.password | string | | |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.process_handle | string | | 0xffffffff |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.process_identifier | numeric | | 984 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.protection | numeric | | 64 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.region_size | numeric | | 4096 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.service_handle | string | | 0x005d1dd0 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.service_manager_handle | string | | 0x005d1e70 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.service_name | string | | Abcdef Hijklmno Qrs |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.service_start_name | string | | |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.service_type | numeric | | 272 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.start_type | numeric | | 2 |
action_result.data.\*.report.signatures.\*.marks.\*.call.category | string | | process |
action_result.data.\*.report.signatures.\*.marks.\*.call.flags.allocation_type | string | | MEM_COMMIT |
action_result.data.\*.report.signatures.\*.marks.\*.call.flags.protection | string | | PAGE_EXECUTE_READWRITE |
action_result.data.\*.report.signatures.\*.marks.\*.call.return_value | numeric | | 0 |
action_result.data.\*.report.signatures.\*.marks.\*.call.status | numeric | | 1 |
action_result.data.\*.report.signatures.\*.marks.\*.call.tid | numeric | | 800 |
action_result.data.\*.report.signatures.\*.marks.\*.call.time | numeric | | 1509432420.843875 |
action_result.data.\*.report.signatures.\*.marks.\*.category | string | | section |
action_result.data.\*.report.signatures.\*.marks.\*.cid | numeric | | 575 |
action_result.data.\*.report.signatures.\*.marks.\*.description | string | | A section with a high entropy has been found |
action_result.data.\*.report.signatures.\*.marks.\*.entropy | numeric | | 7.888327654005668 |
action_result.data.\*.report.signatures.\*.marks.\*.filetype | string | | data |
action_result.data.\*.report.signatures.\*.marks.\*.ioc | string | | .tqn\\x07 |
action_result.data.\*.report.signatures.\*.marks.\*.language | string | | LANG_CHINESE |
action_result.data.\*.report.signatures.\*.marks.\*.name | string | | RT_BITMAP |
action_result.data.\*.report.signatures.\*.marks.\*.offset | string | | 0x00036b80 |
action_result.data.\*.report.signatures.\*.marks.\*.pid | numeric | `pid` | 984 |
action_result.data.\*.report.signatures.\*.marks.\*.section.entropy | numeric | | 7.888327654005668 |
action_result.data.\*.report.signatures.\*.marks.\*.section.name | string | | .reloc |
action_result.data.\*.report.signatures.\*.marks.\*.section.size_of_data | string | | 0x00007600 |
action_result.data.\*.report.signatures.\*.marks.\*.section.virtual_address | string | | 0x00038000 |
action_result.data.\*.report.signatures.\*.marks.\*.section.virtual_size | string | | 0x00007a00 |
action_result.data.\*.report.signatures.\*.marks.\*.service_name | string | | Abcdef Hijklmno Qrs |
action_result.data.\*.report.signatures.\*.marks.\*.service_path | string | `file path` `file name` | C:\\Windows\\update.exe |
action_result.data.\*.report.signatures.\*.marks.\*.size | string | | 0x000004e8 |
action_result.data.\*.report.signatures.\*.marks.\*.sublanguage | string | | SUBLANG_CHINESE_SIMPLIFIED |
action_result.data.\*.report.signatures.\*.marks.\*.type | string | | ioc |
action_result.data.\*.report.signatures.\*.name | string | | pe_features |
action_result.data.\*.report.signatures.\*.references | string | `url` | http://virii.es/U/Using%20Entropy%20Analysis%20to%20Find%20Encrypted%20and%20Packed%20Malware.pdf |
action_result.data.\*.report.signatures.\*.severity | numeric | | 1 |
action_result.data.\*.report.static.imported_dll_count | numeric | | 2 |
action_result.data.\*.report.static.pe_exports.\*.address | string | | 0x40162c |
action_result.data.\*.report.static.pe_exports.\*.name | string | | Exetest |
action_result.data.\*.report.static.pe_exports.\*.ordinal | numeric | | 1 |
action_result.data.\*.report.static.pe_imphash | string | `md5` | 3134150f803531d1ecfdf79165357a25 |
action_result.data.\*.report.static.pe_imports.\*.dll | string | `file name` | KERNEL32.dll |
action_result.data.\*.report.static.pe_imports.\*.imports.\*.address | string | | 0x41f12c |
action_result.data.\*.report.static.pe_imports.\*.imports.\*.name | string | | LoadLibraryA |
action_result.data.\*.report.static.pe_resources.\*.filetype | string | | data |
action_result.data.\*.report.static.pe_resources.\*.language | string | | LANG_CHINESE |
action_result.data.\*.report.static.pe_resources.\*.name | string | | RT_BITMAP |
action_result.data.\*.report.static.pe_resources.\*.offset | string | | 0x00036b80 |
action_result.data.\*.report.static.pe_resources.\*.size | string | | 0x000004e8 |
action_result.data.\*.report.static.pe_resources.\*.sublanguage | string | | SUBLANG_CHINESE_SIMPLIFIED |
action_result.data.\*.report.static.pe_sections.\*.entropy | numeric | | 6.629141043894987 |
action_result.data.\*.report.static.pe_sections.\*.name | string | | .text |
action_result.data.\*.report.static.pe_sections.\*.size_of_data | string | | 0x00007000 |
action_result.data.\*.report.static.pe_sections.\*.virtual_address | string | | 0x00001000 |
action_result.data.\*.report.static.pe_sections.\*.virtual_size | string | | 0x00007000 |
action_result.data.\*.report.static.pe_timestamp | string | | 2009-12-04 13:35:59 |
action_result.data.\*.report.static.pe_versioninfo.\*.name | string | | LegalCopyright |
action_result.data.\*.report.static.pe_versioninfo.\*.value | string | `file name` | Copyright(C) 2004-2015 KuGou-Inc.All Rights Reserved |
action_result.data.\*.report.strings | string | | Translation |
action_result.data.\*.report.target.category | string | | file |
action_result.data.\*.report.target.file.crc32 | string | | 04D96C4B |
action_result.data.\*.report.target.file.md5 | string | `md5` | 6b6fa473cd53b3b1d20fb7d0d7d94dd2 |
action_result.data.\*.report.target.file.name | string | `file name` | Mh.exe |
action_result.data.\*.report.target.file.path | string | | /home/cuckoo/.cuckoo/storage/binaries/e4a5f740683ce26d8312c336e1a2d50aa5b56efe61fc793ff3f9dc08af2da30d |
action_result.data.\*.report.target.file.sha1 | string | `sha1` | ac8682258ec2a9556c5b06dac4b70aa7f408146b |
action_result.data.\*.report.target.file.sha256 | string | `sha256` | e4a5f740683ce26d8312c336e1a2d50aa5b56efe61fc793ff3f9dc08af2da30d |
action_result.data.\*.report.target.file.sha512 | string | | 59a132a04c621aad34c2130895e1c33f8a988a1d400b91ab712c4058ab6fefda698d01f395dd88f15cc8382f6826eee6550296b00981581a5b8abb10682fe9b0 |
action_result.data.\*.report.target.file.size | numeric | | 420314 |
action_result.data.\*.report.target.file.type | string | | PE32 executable (GUI) Intel 80386, for MS Windows |
action_result.data.\*.task_status.added_on | string | | Mon, 30 Oct 2017 23:46:57 GMT |
action_result.data.\*.task_status.category | string | | file |
action_result.data.\*.task_status.clock | string | | Mon, 30 Oct 2017 23:46:57 GMT |
action_result.data.\*.task_status.completed_on | string | | Mon, 30 Oct 2017 23:49:09 GMT |
action_result.data.\*.task_status.custom | string | | |
action_result.data.\*.task_status.duration | numeric | | 132 |
action_result.data.\*.task_status.enforce_timeout | boolean | | True False |
action_result.data.\*.task_status.guest.id | numeric | | 27 |
action_result.data.\*.task_status.guest.label | string | | cuckoo2 |
action_result.data.\*.task_status.guest.manager | string | | VirtualBox |
action_result.data.\*.task_status.guest.name | string | | cuckoo2 |
action_result.data.\*.task_status.guest.shutdown_on | string | | 2017-10-30 23:49:09 |
action_result.data.\*.task_status.guest.started_on | string | | 2017-10-30 23:46:57 |
action_result.data.\*.task_status.guest.status | string | | stopped |
action_result.data.\*.task_status.guest.task_id | numeric | | 27 |
action_result.data.\*.task_status.id | numeric | | 27 |
action_result.data.\*.task_status.machine | string | | |
action_result.data.\*.task_status.memory | boolean | | True False |
action_result.data.\*.task_status.owner | string | | |
action_result.data.\*.task_status.package | string | | |
action_result.data.\*.task_status.platform | string | | |
action_result.data.\*.task_status.priority | numeric | | 1 |
action_result.data.\*.task_status.route | string | | none |
action_result.data.\*.task_status.sample.crc32 | string | | 04D96C4B |
action_result.data.\*.task_status.sample.file_size | numeric | | 420314 |
action_result.data.\*.task_status.sample.file_type | string | | PE32 executable (GUI) Intel 80386, for MS Windows |
action_result.data.\*.task_status.sample.id | numeric | | 15 |
action_result.data.\*.task_status.sample.md5 | string | `md5` | 6b6fa473cd53b3b1d20fb7d0d7d94dd2 |
action_result.data.\*.task_status.sample.sha1 | string | `sha1` | ac8682258ec2a9556c5b06dac4b70aa7f408146b |
action_result.data.\*.task_status.sample.sha256 | string | `sha256` | e4a5f740683ce26d8312c336e1a2d50aa5b56efe61fc793ff3f9dc08af2da30d |
action_result.data.\*.task_status.sample.sha512 | string | | 59a132a04c621aad34c2130895e1c33f8a988a1d400b91ab712c4058ab6fefda698d01f395dd88f15cc8382f6826eee6550296b00981581a5b8abb10682fe9b0 |
action_result.data.\*.task_status.sample_id | numeric | | 15 |
action_result.data.\*.task_status.started_on | string | | Mon, 30 Oct 2017 23:46:57 GMT |
action_result.data.\*.task_status.status | string | | reported |
action_result.data.\*.task_status.target | string | `file name` | /tmp/cuckoo-tmp/tmpbKwc78/Mh.exe |
action_result.data.\*.task_status.timeout | numeric | | 0 |
action_result.status | string | | success failed |
action_result.message | string | | Successfully retrieved report |
action_result.summary.id | numeric | `cuckoo task id` | 27 |
action_result.summary.results_url | string | `url` | https://10.16.6.42:8000/analysis/27/summary |
action_result.summary.target | string | `file name` | Mh.exe |
summary.total_objects | numeric | | 1 |
summary.total_objects_successful | numeric | | 1 |

## action: 'get report'

Query for results of an already completed detonation

Type: **investigate** \
Read only: **True**

#### Action Parameters

PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**id** | required | Task ID to get the results of | string | `cuckoo task id` |

#### Action Output

DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.id | string | `cuckoo task id` | 340 |
action_result.data.\*.report.behavior.apistats.984.CopyFileA | numeric | | 2 |
action_result.data.\*.report.behavior.apistats.984.CreateServiceA | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.FindResourceExW | numeric | | 16 |
action_result.data.\*.report.behavior.apistats.984.GetFileAttributesW | numeric | | 3 |
action_result.data.\*.report.behavior.apistats.984.GetFileSize | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.GetFileType | numeric | | 7 |
action_result.data.\*.report.behavior.apistats.984.GetSystemInfo | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.GetSystemMetrics | numeric | | 4 |
action_result.data.\*.report.behavior.apistats.984.GetSystemTimeAsFileTime | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.GetSystemWindowsDirectoryW | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.GetTempPathW | numeric | | 2 |
action_result.data.\*.report.behavior.apistats.984.GetTimeZoneInformation | numeric | | 2 |
action_result.data.\*.report.behavior.apistats.984.LdrGetDllHandle | numeric | | 7 |
action_result.data.\*.report.behavior.apistats.984.LdrGetProcedureAddress | numeric | | 548 |
action_result.data.\*.report.behavior.apistats.984.LdrLoadDll | numeric | | 35 |
action_result.data.\*.report.behavior.apistats.984.LoadResource | numeric | | 14 |
action_result.data.\*.report.behavior.apistats.984.LoadStringA | numeric | | 49 |
action_result.data.\*.report.behavior.apistats.984.NtAllocateVirtualMemory | numeric | | 14 |
action_result.data.\*.report.behavior.apistats.984.NtClose | numeric | | 17 |
action_result.data.\*.report.behavior.apistats.984.NtCreateFile | numeric | | 8 |
action_result.data.\*.report.behavior.apistats.984.NtCreateMutant | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.NtCreateSection | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.NtCreateThreadEx | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.NtDelayExecution | numeric | | 71680 |
action_result.data.\*.report.behavior.apistats.984.NtDuplicateObject | numeric | | 2 |
action_result.data.\*.report.behavior.apistats.984.NtFreeVirtualMemory | numeric | | 2 |
action_result.data.\*.report.behavior.apistats.984.NtMapViewOfSection | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.NtOpenKey | numeric | | 2 |
action_result.data.\*.report.behavior.apistats.984.NtOpenMutant | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.NtProtectVirtualMemory | numeric | | 4 |
action_result.data.\*.report.behavior.apistats.984.NtQueryAttributesFile | numeric | | 4 |
action_result.data.\*.report.behavior.apistats.984.NtQueryInformationFile | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.NtQueryValueKey | numeric | | 2 |
action_result.data.\*.report.behavior.apistats.984.NtReadFile | numeric | | 22 |
action_result.data.\*.report.behavior.apistats.984.NtResumeThread | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.NtWriteFile | numeric | | 22 |
action_result.data.\*.report.behavior.apistats.984.OpenSCManagerA | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.OutputDebugStringA | numeric | | 3 |
action_result.data.\*.report.behavior.apistats.984.RegCloseKey | numeric | | 5 |
action_result.data.\*.report.behavior.apistats.984.RegOpenKeyExA | numeric | | 7 |
action_result.data.\*.report.behavior.apistats.984.RegOpenKeyExW | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.RegQueryValueExA | numeric | | 3 |
action_result.data.\*.report.behavior.apistats.984.RegQueryValueExW | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.RegSetValueExA | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.SetEndOfFile | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.SetFileAttributesW | numeric | | 2 |
action_result.data.\*.report.behavior.apistats.984.SetFilePointer | numeric | | 10 |
action_result.data.\*.report.behavior.apistats.984.SetFileTime | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.SetUnhandledExceptionFilter | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.SetWindowsHookExA | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.984.StartServiceA | numeric | | 1 |
action_result.data.\*.report.behavior.generic.\*.first_seen | numeric | | 1509432420.046875 |
action_result.data.\*.report.behavior.generic.\*.pid | numeric | `pid` | 984 |
action_result.data.\*.report.behavior.generic.\*.ppid | numeric | `pid` | 1104 |
action_result.data.\*.report.behavior.generic.\*.process_name | string | `file name` | Mh.exe |
action_result.data.\*.report.behavior.generic.\*.process_path | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.generic.\*.summary.dll_loaded | string | | COMCTL32.DLL |
action_result.data.\*.report.behavior.generic.\*.summary.file_copied.\* | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\aul9806.tmp |
action_result.data.\*.report.behavior.generic.\*.summary.file_created | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\aul9806.tmp |
action_result.data.\*.report.behavior.generic.\*.summary.file_exists | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp |
action_result.data.\*.report.behavior.generic.\*.summary.file_opened | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.generic.\*.summary.file_read | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.generic.\*.summary.file_recreated | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\rql71B0.tmp |
action_result.data.\*.report.behavior.generic.\*.summary.file_written | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\aul9806.tmp |
action_result.data.\*.report.behavior.generic.\*.summary.mutex | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.generic.\*.summary.regkey_opened | string | | HKEY_CURRENT_USER\\Software\\Borland\\Delphi\\Locales |
action_result.data.\*.report.behavior.generic.\*.summary.regkey_read | string | | HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Security_HKLM_only |
action_result.data.\*.report.behavior.generic.\*.summary.regkey_written | string | | HKEY_LOCAL_MACHINE\\SYSTEM\\ControlSet001\\services\\Abcdef Hijklmno Qrs\\Description |
action_result.data.\*.report.behavior.processes.\*.calls.\*.api | string | | LdrLoadDll |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.access | string | | 0x00020019 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.allocation_type | numeric | | 8192 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.base_address | string | | 0x01e30000 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.base_handle | string | | 0x80000001 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.basename | string | | Kernel32 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.buffer | string | | áÌh®8¨7Si88¬8ì"¬8¬8¬8¬8¬8¬8¬8¬8¬88³"1Â.9Ca·¨øþQ|æJ`ËäYbûM|Ø¶ZjäMaãVkÉäXÅø=¡8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8üÓ8à;â:4¬8¬8L6,§=¬6:¬8¬æ<¼?¬<¬¶?¬x¬8¬8¨8¬8¨8¬8¬¦?¬8¬8®8¬8¬8¬(¬8¬8¼8`±?H8t³?X8¬¶?t8¬8¬8¬8¬8¸? 8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8â\]wØ8¬æ\<¬8¬8¬8¬8¬8¬8,8ïòY{Í8¬6:¬\<¬ :¬8¬8¬8¬8ì8ïäK}Ï8¬8¬¶?¬8¬6:¬8¬8¬8ì8Ï¦¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬+¦¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬8¬¸+¦8¬·4®hÂho\[âr6úªá®8Kª¬ÜÃáSiÓÊôL½p@ãÝ¨æ¬
'ÎLÓáÇ±|+¤©ð¸>/«4ÙÈWxS)¸L+D=°,4#8ØÏùsè3Cþ\<ËÎÏE,ÿRRWx4¶ìWþlU¥ã´K4U©Hüü8 ?Öag×¤§@ì(â/®â6°éO\*~öþZ,Ó¤'ÏáULü7h0´ÆÇ¸;×¼k |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.callback_function | string | | 0x00451ebc |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.commit_size | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.create_disposition | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.create_options | numeric | | 96 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.database_name | string | | |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.desired_access | string | | 0x80100080 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.dirpath | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\ |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.display_name | string | | Abcdef Hijklmno Qrstuvwx Abcd |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.error_control | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.fail_if_exists | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.file_attributes | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.file_handle | string | | 0x0000006c |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.file_size_low | numeric | | 420314 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.filepath | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.filepath_r | string | `file name` `file path` | \\??\\C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.flags | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.free_type | numeric | | 32768 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.function_address | string | | 0x77031410 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.function_name | string | | CloseHandle |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.handle | string | | 0x00000070 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.handle_attributes | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.hook_identifier | numeric | | 4 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.id | numeric | | 65398 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.index | numeric | | 74 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.information_class | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.initial_owner | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.key_handle | string | | 0x0000006c |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.key_name | string | | |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.language_identifier | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.length | numeric | | 10240 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.machine_name | string | | |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.milliseconds | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.module | string | `file name` | kernel32 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.module_address | string | | 0x77020000 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.module_handle | string | | 0x00450000 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.module_name | string | `file name` `file path` | Kernel32.dll |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.move_method | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.mutant_handle | string | | 0x00000000 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.mutant_name | string | `file path` `file name` | Residented |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.name | string | | #12 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.newfilepath | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\aul9806.tmp |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.newfilepath_r | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\aul9806.tmp |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.object_handle | string | | 0x00000000 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.offset | numeric | | 244186 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.oldfilepath | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.oldfilepath_r | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.options | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.ordinal | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.parameter | string | | 0x005d4c10 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.password | string | | |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.pointer | string | | 0x004b5da0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.process_handle | string | | 0xffffffff |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.process_identifier | numeric | | 984 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.processor_count | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.protection | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.reg_type | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.region_size | numeric | | 1048576 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.regkey | string | | HKEY_CURRENT_USER\\Software\\Microsoft\\Windows\\CurrentVersion\\Explorer |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.regkey_r | string | | Software\\Microsoft\\Windows\\CurrentVersion\\Explorer |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.resource_handle | string | | 0x004c24b0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.section_handle | string | | 0x000000a4 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.section_name | string | | |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.section_offset | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.service_handle | string | | 0x005d1dd0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.service_manager_handle | string | | 0x005d1e70 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.service_name | string | | Abcdef Hijklmno Qrs |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.service_start_name | string | | |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.service_type | numeric | | 272 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.share_access | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.size | numeric | | 1835008 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.skipped | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.source_handle | string | | 0x00000100 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.source_process_handle | string | | 0xffffffff |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.source_process_identifier | numeric | | 984 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.stack_zero_bits | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.start_type | numeric | | 2 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.status_info | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.string | string | | Exception in safecall method |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.suspend_count | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.suspended | numeric | | 3 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.target_handle | string | | 0x00000104 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.target_process_handle | string | | 0xffffffff |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.target_process_identifier | numeric | | 984 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.thread_handle | string | | 0x00000100 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.thread_identifier | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.thread_name | string | | 0x0018ec1c |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.type | string | | #32761 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.value | string | | |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.view_size | numeric | | 2945024 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.win32_protect | numeric | | 2 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.category | string | | system |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.allocation_type | string | | MEM_RESERVE |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.create_disposition | string | | FILE_OPEN |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.create_options | string | | FILE_NON_DIRECTORY_FILE|FILE_SYNCHRONOUS_IO_NONALERT |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.desired_access | string | | FILE_READ_ATTRIBUTES|SYNCHRONIZE |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.file_attributes | string | | FILE_ATTRIBUTE_READONLY |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.hook_identifier | string | | WH_CALLWNDPROC |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.index | string | | SM_MIDEASTENABLED |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.information_class | string | | KeyValueFullInformation |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.protection | string | | PAGE_NOACCESS |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.reg_type | string | | REG_NONE |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.share_access | string | | FILE_SHARE_READ |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.status_info | string | | FILE_OPENED |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.win32_protect | string | | PAGE_READONLY |
action_result.data.\*.report.behavior.processes.\*.calls.\*.last_error | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.nt_status | numeric | | -1073741772 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.return_value | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.status | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.tid | numeric | | 800 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.time | numeric | | 1509432420.530875 |
action_result.data.\*.report.behavior.processes.\*.command_line | string | `file path` `file name` | C:\\Windows\\system32\\lsass.exe |
action_result.data.\*.report.behavior.processes.\*.first_seen | numeric | | 1509432418.0625 |
action_result.data.\*.report.behavior.processes.\*.modules.\*.baseaddr | string | | 0xff180000 |
action_result.data.\*.report.behavior.processes.\*.modules.\*.basename | string | `file name` | lsass.exe |
action_result.data.\*.report.behavior.processes.\*.modules.\*.filepath | string | `file path` `file name` | C:\\Windows\\system32\\lsass.exe |
action_result.data.\*.report.behavior.processes.\*.modules.\*.imgsize | numeric | | 49152 |
action_result.data.\*.report.behavior.processes.\*.pid | numeric | `pid` | 444 |
action_result.data.\*.report.behavior.processes.\*.ppid | numeric | `pid` | 340 |
action_result.data.\*.report.behavior.processes.\*.process_name | string | `file name` | lsass.exe |
action_result.data.\*.report.behavior.processes.\*.process_path | string | `file path` `file name` | C:\\Windows\\System32\\lsass.exe |
action_result.data.\*.report.behavior.processes.\*.tid | numeric | | 1604 |
action_result.data.\*.report.behavior.processes.\*.time | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.track | boolean | | True False |
action_result.data.\*.report.behavior.processes.\*.type | string | | process |
action_result.data.\*.report.behavior.processtree.\*.command_line | string | `file path` `file name` | C:\\Windows\\system32\\lsass.exe |
action_result.data.\*.report.behavior.processtree.\*.first_seen | numeric | | 1509432418.0625 |
action_result.data.\*.report.behavior.processtree.\*.pid | numeric | `pid` | 444 |
action_result.data.\*.report.behavior.processtree.\*.ppid | numeric | `pid` | 340 |
action_result.data.\*.report.behavior.processtree.\*.process_name | string | `file name` | lsass.exe |
action_result.data.\*.report.behavior.processtree.\*.track | boolean | | True False |
action_result.data.\*.report.behavior.summary.dll_loaded | string | | COMCTL32.DLL |
action_result.data.\*.report.behavior.summary.file_copied.\* | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\aul9806.tmp |
action_result.data.\*.report.behavior.summary.file_created | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\aul9806.tmp |
action_result.data.\*.report.behavior.summary.file_exists | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp |
action_result.data.\*.report.behavior.summary.file_opened | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.summary.file_read | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.summary.file_recreated | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\rql71B0.tmp |
action_result.data.\*.report.behavior.summary.file_written | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\aul9806.tmp |
action_result.data.\*.report.behavior.summary.mutex | string | `file path` `file name` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\Mh.exe |
action_result.data.\*.report.behavior.summary.regkey_opened | string | | HKEY_CURRENT_USER\\Software\\Borland\\Delphi\\Locales |
action_result.data.\*.report.behavior.summary.regkey_read | string | | HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Security_HKLM_only |
action_result.data.\*.report.behavior.summary.regkey_written | string | | HKEY_LOCAL_MACHINE\\SYSTEM\\ControlSet001\\services\\Abcdef Hijklmno Qrs\\Description |
action_result.data.\*.report.debug.cuckoo | string | | 2017-10-30 23:49:15,341 [cuckoo.core.plugins] DEBUG: Analysis matched signature: pe_features |
action_result.data.\*.report.debug.log | string | | 2017-10-30 23:48:59,125 [analyzer] INFO: Analysis completed. |
action_result.data.\*.report.dropped.\*.crc32 | string | | CB1602FC |
action_result.data.\*.report.dropped.\*.filepath | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Temp\\rql71B0.tmp |
action_result.data.\*.report.dropped.\*.md5 | string | `md5` | 685f1cbd4af30a1d0c25f252d399a666 |
action_result.data.\*.report.dropped.\*.name | string | | 0e478c95a7a07570_rql71b0.tmp |
action_result.data.\*.report.dropped.\*.path | string | | /home/cuckoo/.cuckoo/storage/analyses/27/files/0e478c95a7a07570_rql71b0.tmp |
action_result.data.\*.report.dropped.\*.pids | numeric | | 984 |
action_result.data.\*.report.dropped.\*.sha1 | string | `sha1` | 6a1b978f5e6150b88c8634146f1406ed97d2f134 |
action_result.data.\*.report.dropped.\*.sha256 | string | `sha256` | 0e478c95a7a07570a69e6061e7c1da9001bccad9cc454f2ed4da58824a13e0f4 |
action_result.data.\*.report.dropped.\*.sha512 | string | | 6555ad6b4f4f26105ca8aad64501d74519a3e091f559b4b563d6ffb20a2ddfcde65e4fe94971a9bc65e86db577f2548ca00f9920d341c8ea808b04c0947d61d9 |
action_result.data.\*.report.dropped.\*.size | numeric | | 176128 |
action_result.data.\*.report.dropped.\*.type | string | | PE32 executable (DLL) (GUI) Intel 80386 (stripped to external PDB), for MS Windows |
action_result.data.\*.report.info.added | numeric | | 1509407217.087696 |
action_result.data.\*.report.info.category | string | | file |
action_result.data.\*.report.info.custom | string | | |
action_result.data.\*.report.info.duration | numeric | | 132 |
action_result.data.\*.report.info.ended | numeric | | 1509407349.736956 |
action_result.data.\*.report.info.git.fetch_head | string | | |
action_result.data.\*.report.info.git.head | string | | |
action_result.data.\*.report.info.id | numeric | | 27 |
action_result.data.\*.report.info.machine.label | string | | cuckoo2 |
action_result.data.\*.report.info.machine.manager | string | | VirtualBox |
action_result.data.\*.report.info.machine.name | string | | cuckoo2 |
action_result.data.\*.report.info.machine.shutdown_on | string | | 2017-10-30 23:49:09 |
action_result.data.\*.report.info.machine.started_on | string | | 2017-10-30 23:46:57 |
action_result.data.\*.report.info.machine.status | string | | stopped |
action_result.data.\*.report.info.monitor | string | `sha1` | 2bd01ede5c5258d5fce2e38bc58348a62c11ce33 |
action_result.data.\*.report.info.options | string | | |
action_result.data.\*.report.info.owner | string | | |
action_result.data.\*.report.info.package | string | | |
action_result.data.\*.report.info.platform | string | | |
action_result.data.\*.report.info.route | string | | none |
action_result.data.\*.report.info.score | numeric | | 3 |
action_result.data.\*.report.info.started | numeric | | 1509407217.208121 |
action_result.data.\*.report.info.version | string | | 2.0.3 |
action_result.data.\*.report.metadata.output.dropped.\*.basename | string | | 0e478c95a7a07570_rql71b0.tmp |
action_result.data.\*.report.metadata.output.dropped.\*.dirname | string | | files |
action_result.data.\*.report.metadata.output.dropped.\*.sha256 | string | `sha256` | 0e478c95a7a07570a69e6061e7c1da9001bccad9cc454f2ed4da58824a13e0f4 |
action_result.data.\*.report.metadata.output.pcap.basename | string | | dump.pcap |
action_result.data.\*.report.metadata.output.pcap.dirname | string | | |
action_result.data.\*.report.metadata.output.pcap.sha256 | string | `sha256` | 08d4daf8f1d393aa6cceff4235dc666465f49cbe3c01a9aea9f7e4c8e9be8c43 |
action_result.data.\*.report.network.dns.\*.answers.\*.data | string | `ip` | 120.210.207.151 |
action_result.data.\*.report.network.dns.\*.answers.\*.type | string | | A |
action_result.data.\*.report.network.dns.\*.request | string | | zebing520.vicp.cc |
action_result.data.\*.report.network.dns.\*.type | string | | A |
action_result.data.\*.report.network.dns_servers | string | `ip` | 8.8.8.8 |
action_result.data.\*.report.network.domains.\*.domain | string | `domain` | teredo.ipv6.microsoft.com |
action_result.data.\*.report.network.domains.\*.ip | string | `ip` | |
action_result.data.\*.report.network.hosts | string | `ip` | 72.21.91.29 |
action_result.data.\*.report.network.pcap_sha256 | string | `sha256` | 08d4daf8f1d393aa6cceff4235dc666465f49cbe3c01a9aea9f7e4c8e9be8c43 |
action_result.data.\*.report.network.sorted_pcap_sha256 | string | `sha256` | 819ac5fcbe6aa7f4d49795a5c0c47bf52feb3be3d24b47c28e79a7ecd9eba9c4 |
action_result.data.\*.report.network.udp.\*.dport | numeric | | 5355 |
action_result.data.\*.report.network.udp.\*.dst | string | `ip` | 224.0.0.252 |
action_result.data.\*.report.network.udp.\*.offset | numeric | | 1822 |
action_result.data.\*.report.network.udp.\*.sport | numeric | | 51966 |
action_result.data.\*.report.network.udp.\*.src | string | `ip` | 192.168.56.11 |
action_result.data.\*.report.network.udp.\*.time | numeric | | 6.255922079086304 |
action_result.data.\*.report.screenshots.\*.ocr | string | | |
action_result.data.\*.report.screenshots.\*.path | string | | /home/cuckoo/.cuckoo/storage/analyses/27/shots/0001.jpg |
action_result.data.\*.report.signatures.\*.description | string | | The executable contains unknown PE section names indicative of a packer (could be a false positive) |
action_result.data.\*.report.signatures.\*.families | string | | nitol |
action_result.data.\*.report.signatures.\*.markcount | numeric | | 1 |
action_result.data.\*.report.signatures.\*.marks.\*.call.api | string | | NtAllocateVirtualMemory |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.allocation_type | numeric | | 4096 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.base_address | string | | 0x004e0000 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.desired_access | numeric | | 983551 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.display_name | string | | Abcdef Hijklmno Qrstuvwx Abcd |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.error_control | numeric | | 0 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.filepath | string | `file path` `file name` | C:\\Windows\\update.exe |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.filepath_r | string | `file path` `file name` | C:\\Windows\\update.exe |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.password | string | | |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.process_handle | string | | 0xffffffff |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.process_identifier | numeric | | 984 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.protection | numeric | | 64 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.region_size | numeric | | 4096 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.service_handle | string | | 0x005d1dd0 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.service_manager_handle | string | | 0x005d1e70 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.service_name | string | | Abcdef Hijklmno Qrs |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.service_start_name | string | | |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.service_type | numeric | | 272 |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.start_type | numeric | | 2 |
action_result.data.\*.report.signatures.\*.marks.\*.call.category | string | | process |
action_result.data.\*.report.signatures.\*.marks.\*.call.flags.allocation_type | string | | MEM_COMMIT |
action_result.data.\*.report.signatures.\*.marks.\*.call.flags.protection | string | | PAGE_EXECUTE_READWRITE |
action_result.data.\*.report.signatures.\*.marks.\*.call.return_value | numeric | | 0 |
action_result.data.\*.report.signatures.\*.marks.\*.call.status | numeric | | 1 |
action_result.data.\*.report.signatures.\*.marks.\*.call.tid | numeric | | 800 |
action_result.data.\*.report.signatures.\*.marks.\*.call.time | numeric | | 1509432420.843875 |
action_result.data.\*.report.signatures.\*.marks.\*.category | string | | section |
action_result.data.\*.report.signatures.\*.marks.\*.cid | numeric | | 575 |
action_result.data.\*.report.signatures.\*.marks.\*.description | string | | A section with a high entropy has been found |
action_result.data.\*.report.signatures.\*.marks.\*.entropy | numeric | | 7.888327654005668 |
action_result.data.\*.report.signatures.\*.marks.\*.filetype | string | | data |
action_result.data.\*.report.signatures.\*.marks.\*.ioc | string | | .tqn\\x07 |
action_result.data.\*.report.signatures.\*.marks.\*.language | string | | LANG_CHINESE |
action_result.data.\*.report.signatures.\*.marks.\*.name | string | | RT_BITMAP |
action_result.data.\*.report.signatures.\*.marks.\*.offset | string | | 0x00036b80 |
action_result.data.\*.report.signatures.\*.marks.\*.pid | numeric | `pid` | 984 |
action_result.data.\*.report.signatures.\*.marks.\*.section.entropy | numeric | | 7.888327654005668 |
action_result.data.\*.report.signatures.\*.marks.\*.section.name | string | | .reloc |
action_result.data.\*.report.signatures.\*.marks.\*.section.size_of_data | string | | 0x00007600 |
action_result.data.\*.report.signatures.\*.marks.\*.section.virtual_address | string | | 0x00038000 |
action_result.data.\*.report.signatures.\*.marks.\*.section.virtual_size | string | | 0x00007a00 |
action_result.data.\*.report.signatures.\*.marks.\*.service_name | string | | Abcdef Hijklmno Qrs |
action_result.data.\*.report.signatures.\*.marks.\*.service_path | string | `file path` `file name` | C:\\Windows\\update.exe |
action_result.data.\*.report.signatures.\*.marks.\*.size | string | | 0x000004e8 |
action_result.data.\*.report.signatures.\*.marks.\*.sublanguage | string | | SUBLANG_CHINESE_SIMPLIFIED |
action_result.data.\*.report.signatures.\*.marks.\*.type | string | | ioc |
action_result.data.\*.report.signatures.\*.name | string | | pe_features |
action_result.data.\*.report.signatures.\*.references | string | `url` | http://virii.es/U/Using%20Entropy%20Analysis%20to%20Find%20Encrypted%20and%20Packed%20Malware.pdf |
action_result.data.\*.report.signatures.\*.severity | numeric | | 1 |
action_result.data.\*.report.static.imported_dll_count | numeric | | 2 |
action_result.data.\*.report.static.pe_exports.\*.address | string | | 0x40162c |
action_result.data.\*.report.static.pe_exports.\*.name | string | | Exetest |
action_result.data.\*.report.static.pe_exports.\*.ordinal | numeric | | 1 |
action_result.data.\*.report.static.pe_imphash | string | `md5` | 3134150f803531d1ecfdf79165357a25 |
action_result.data.\*.report.static.pe_imports.\*.dll | string | `file name` | KERNEL32.dll |
action_result.data.\*.report.static.pe_imports.\*.imports.\*.address | string | | 0x41f12c |
action_result.data.\*.report.static.pe_imports.\*.imports.\*.name | string | | LoadLibraryA |
action_result.data.\*.report.static.pe_resources.\*.filetype | string | | data |
action_result.data.\*.report.static.pe_resources.\*.language | string | | LANG_CHINESE |
action_result.data.\*.report.static.pe_resources.\*.name | string | | RT_BITMAP |
action_result.data.\*.report.static.pe_resources.\*.offset | string | | 0x00036b80 |
action_result.data.\*.report.static.pe_resources.\*.size | string | | 0x000004e8 |
action_result.data.\*.report.static.pe_resources.\*.sublanguage | string | | SUBLANG_CHINESE_SIMPLIFIED |
action_result.data.\*.report.static.pe_sections.\*.entropy | numeric | | 6.629141043894987 |
action_result.data.\*.report.static.pe_sections.\*.name | string | | .text |
action_result.data.\*.report.static.pe_sections.\*.size_of_data | string | | 0x00007000 |
action_result.data.\*.report.static.pe_sections.\*.virtual_address | string | | 0x00001000 |
action_result.data.\*.report.static.pe_sections.\*.virtual_size | string | | 0x00007000 |
action_result.data.\*.report.static.pe_timestamp | string | | 2009-12-04 13:35:59 |
action_result.data.\*.report.static.pe_versioninfo.\*.name | string | | LegalCopyright |
action_result.data.\*.report.static.pe_versioninfo.\*.value | string | `file name` | Copyright(C) 2004-2015 KuGou-Inc.All Rights Reserved |
action_result.data.\*.report.strings | string | | Translation |
action_result.data.\*.report.target.category | string | | file |
action_result.data.\*.report.target.file.crc32 | string | | 04D96C4B |
action_result.data.\*.report.target.file.md5 | string | `md5` | 6b6fa473cd53b3b1d20fb7d0d7d94dd2 |
action_result.data.\*.report.target.file.name | string | `file name` | Mh.exe |
action_result.data.\*.report.target.file.path | string | | /home/cuckoo/.cuckoo/storage/binaries/e4a5f740683ce26d8312c336e1a2d50aa5b56efe61fc793ff3f9dc08af2da30d |
action_result.data.\*.report.target.file.sha1 | string | `sha1` | ac8682258ec2a9556c5b06dac4b70aa7f408146b |
action_result.data.\*.report.target.file.sha256 | string | `sha256` | e4a5f740683ce26d8312c336e1a2d50aa5b56efe61fc793ff3f9dc08af2da30d |
action_result.data.\*.report.target.file.sha512 | string | | 59a132a04c621aad34c2130895e1c33f8a988a1d400b91ab712c4058ab6fefda698d01f395dd88f15cc8382f6826eee6550296b00981581a5b8abb10682fe9b0 |
action_result.data.\*.report.target.file.size | numeric | | 420314 |
action_result.data.\*.report.target.file.type | string | | PE32 executable (GUI) Intel 80386, for MS Windows |
action_result.data.\*.task_status.added_on | string | | Mon, 30 Oct 2017 23:46:57 GMT |
action_result.data.\*.task_status.category | string | | file |
action_result.data.\*.task_status.clock | string | | Mon, 30 Oct 2017 23:46:57 GMT |
action_result.data.\*.task_status.completed_on | string | | Mon, 30 Oct 2017 23:49:09 GMT |
action_result.data.\*.task_status.custom | string | | |
action_result.data.\*.task_status.duration | numeric | | 132 |
action_result.data.\*.task_status.enforce_timeout | boolean | | True False |
action_result.data.\*.task_status.guest.id | numeric | | 27 |
action_result.data.\*.task_status.guest.label | string | | cuckoo2 |
action_result.data.\*.task_status.guest.manager | string | | VirtualBox |
action_result.data.\*.task_status.guest.name | string | | cuckoo2 |
action_result.data.\*.task_status.guest.shutdown_on | string | | 2017-10-30 23:49:09 |
action_result.data.\*.task_status.guest.started_on | string | | 2017-10-30 23:46:57 |
action_result.data.\*.task_status.guest.status | string | | stopped |
action_result.data.\*.task_status.guest.task_id | numeric | | 27 |
action_result.data.\*.task_status.id | numeric | | 27 |
action_result.data.\*.task_status.machine | string | | |
action_result.data.\*.task_status.memory | boolean | | True False |
action_result.data.\*.task_status.owner | string | | |
action_result.data.\*.task_status.package | string | | |
action_result.data.\*.task_status.platform | string | | |
action_result.data.\*.task_status.priority | numeric | | 1 |
action_result.data.\*.task_status.route | string | | none |
action_result.data.\*.task_status.sample.crc32 | string | | 04D96C4B |
action_result.data.\*.task_status.sample.file_size | numeric | | 420314 |
action_result.data.\*.task_status.sample.file_type | string | | PE32 executable (GUI) Intel 80386, for MS Windows |
action_result.data.\*.task_status.sample.id | numeric | | 15 |
action_result.data.\*.task_status.sample.md5 | string | `md5` | 6b6fa473cd53b3b1d20fb7d0d7d94dd2 |
action_result.data.\*.task_status.sample.sha1 | string | `sha1` | ac8682258ec2a9556c5b06dac4b70aa7f408146b |
action_result.data.\*.task_status.sample.sha256 | string | `sha256` | e4a5f740683ce26d8312c336e1a2d50aa5b56efe61fc793ff3f9dc08af2da30d |
action_result.data.\*.task_status.sample.sha512 | string | | 59a132a04c621aad34c2130895e1c33f8a988a1d400b91ab712c4058ab6fefda698d01f395dd88f15cc8382f6826eee6550296b00981581a5b8abb10682fe9b0 |
action_result.data.\*.task_status.sample_id | numeric | | 15 |
action_result.data.\*.task_status.started_on | string | | Mon, 30 Oct 2017 23:46:57 GMT |
action_result.data.\*.task_status.status | string | | reported |
action_result.data.\*.task_status.target | string | `file name` | /tmp/cuckoo-tmp/tmpbKwc78/Mh.exe |
action_result.data.\*.task_status.timeout | numeric | | 0 |
action_result.status | string | | success failed |
action_result.message | string | | Successfully retrieved report |
action_result.summary.id | string | `cuckoo task id` | 27 |
action_result.summary.results_url | string | `url` | https://10.16.6.42:8000/analysis/27/summary |
action_result.summary.target | string | | |
summary.total_objects | numeric | | 1 |
summary.total_objects_successful | numeric | | 1 |

## action: 'detonate url'

Load a URL in the Cuckoo sandbox and retrieve the analysis results

Type: **generic** \
Read only: **False**

#### Action Parameters

PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** | required | URL to detonate | string | `url` `domain` |

#### Action Output

DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.url | string | `url` `domain` | https://www.test.com |
action_result.data.\*.report.behavior.apistats.1432.CoCreateInstance | numeric | | 79 |
action_result.data.\*.report.behavior.apistats.1432.CoGetClassObject | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.1432.CoInitializeEx | numeric | | 48 |
action_result.data.\*.report.behavior.apistats.1432.CoInitializeSecurity | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.1432.CoUninitialize | numeric | | 39 |
action_result.data.\*.report.behavior.apistats.1432.CreateProcessInternalW | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.1432.LdrLoadDll | numeric | | 120 |
action_result.data.\*.report.behavior.apistats.1432.NtCreateFile | numeric | | 316 |
action_result.data.\*.report.behavior.apistats.1432.NtDelayExecution | numeric | | 2 |
action_result.data.\*.report.behavior.apistats.1432.NtOpenFile | numeric | | 254 |
action_result.data.\*.report.behavior.apistats.1432.NtWriteFile | numeric | | 71 |
action_result.data.\*.report.behavior.apistats.1432.OleInitialize | numeric | | 2 |
action_result.data.\*.report.behavior.apistats.444.PRF | numeric | | 9 |
action_result.data.\*.report.behavior.apistats.552.CImgElement_put_src | numeric | | 2 |
action_result.data.\*.report.behavior.apistats.552.COleScript_Compile | numeric | | 46 |
action_result.data.\*.report.behavior.apistats.552.CWindow_AddTimeoutCode | numeric | | 6 |
action_result.data.\*.report.behavior.apistats.552.CoCreateInstance | numeric | | 48 |
action_result.data.\*.report.behavior.apistats.552.CoGetClassObject | numeric | | 5 |
action_result.data.\*.report.behavior.apistats.552.CoInitializeEx | numeric | | 43 |
action_result.data.\*.report.behavior.apistats.552.CoInitializeSecurity | numeric | | 1 |
action_result.data.\*.report.behavior.apistats.552.CoUninitialize | numeric | | 31 |
action_result.data.\*.report.behavior.apistats.552.LdrLoadDll | numeric | | 211 |
action_result.data.\*.report.behavior.apistats.552.NtCreateFile | numeric | | 235 |
action_result.data.\*.report.behavior.apistats.552.NtDelayExecution | numeric | | 11 |
action_result.data.\*.report.behavior.apistats.552.NtOpenFile | numeric | | 97 |
action_result.data.\*.report.behavior.apistats.552.NtWriteFile | numeric | | 117 |
action_result.data.\*.report.behavior.apistats.552.OleInitialize | numeric | | 2 |
action_result.data.\*.report.behavior.generic.\*.first_seen | numeric | | 1509432136.46875 |
action_result.data.\*.report.behavior.generic.\*.pid | numeric | `pid` | 1432 |
action_result.data.\*.report.behavior.generic.\*.ppid | numeric | `pid` | 944 |
action_result.data.\*.report.behavior.generic.\*.process_name | string | `file name` | iexplore.exe |
action_result.data.\*.report.behavior.generic.\*.process_path | string | `file path` `file name` | C:\\Program Files\\Internet Explorer\\iexplore.exe |
action_result.data.\*.report.behavior.generic.\*.summary.command_line | string | | "C:\\Program Files\\Internet Explorer\\iexplore.exe" SCODEF:1432 CREDAT:14337 |
action_result.data.\*.report.behavior.generic.\*.summary.dll_loaded | string | `file name` | Normaliz.dll |
action_result.data.\*.report.behavior.generic.\*.summary.file_created | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Microsoft\\Windows\\Temporary Internet Files\\Content.IE5\\YJ602KU8\\google_com[1].htm |
action_result.data.\*.report.behavior.generic.\*.summary.file_failed | string | `file path` | C:\\Users\\cuser2\\AppData\\LocalLow\\Microsoft\\CryptnetUrlCache\\MetaData\\828298824EA5549947C17DDABF6871F5_83B81F152A53AA21AE01E022AED042AB |
action_result.data.\*.report.behavior.generic.\*.summary.file_opened | string | `file path` | C:\\Windows\\System32\\ras\\ |
action_result.data.\*.report.behavior.generic.\*.summary.file_recreated | string | | \\??\\STORAGE#Volume#{5265d5dc-bb2d-11e7-9a04-806e6f6e6963}#0000000006500000#{53f5630d-b6bf-11d0-94f2-00a0c91efb8b} |
action_result.data.\*.report.behavior.generic.\*.summary.file_written | string | `file path` | C:\\Users\\cuser2\\AppData\\LocalLow\\Microsoft\\CryptnetUrlCache\\Content\\8059E9A0D314877E40FE93D8CCFB3C69_1BF9768FF0DFF2EF4310FBB421A10F13 |
action_result.data.\*.report.behavior.generic.\*.summary.guid | string | | {08c0e040-62d1-11d1-9326-0060b067b86e} |
action_result.data.\*.report.behavior.generic.\*.summary.tls_master.\* | string | | 0a1dcd2fe098ee2701df6fa90424c49f2f77f9c695a77665ea373bb2488567e8c1f9a6329b22162876dce75ace639808 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.api | string | | PRF |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.argument | string | | |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.basename | string | | user32 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.buffer | string | | ýÿÿÿþÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿÿR |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.class_context | numeric | | 23 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.client_random | string | `sha256` | 59f81b4c419606a24811d6f7321b5cbbe44675ef800fbdd083779167fc15fe5b |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.clsid | string | | {dcb00c01-570f-4a9b-8d69-199fdba5723b} |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.code | string | | function() { var a = document.createElement("script"); a.src = b; google.timers && google.timers.load.t && google.tick("load", { gen204: "xjsls", clearcut: 31 }); document.getElementById("xjsd").appendChild(a) } |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.command_line | string | | "C:\\Program Files\\Internet Explorer\\iexplore.exe" SCODEF:1432 CREDAT:14337 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.create_disposition | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.create_options | numeric | | 96 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.creation_flags | numeric | | 4 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.current_directory | string | | |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.desired_access | string | | 0x80100080 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.file_attributes | numeric | | 128 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.file_handle | string | | 0x00000000000000b0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.filepath | string | `file path` `file name` | C:\\Windows\\Globalization\\Sorting\\sortdefault.nls |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.filepath_r | string | `file name` | \\??\\C:\\Windows\\Globalization\\Sorting\\sortdefault.nls |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.flags | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.iid | string | | {dcb00000-570f-4a9b-8d69-199fdba5723b} |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.inherit_handles | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.master_secret | string | | 0a1dcd2fe098ee2701df6fa90424c49f2f77f9c695a77665ea373bb2488567e8c1f9a6329b22162876dce75ace639808 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.milliseconds | numeric | | 5000 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.module_address | string | | 0x00000000772f0000 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.module_name | string | `file name` `file path` | user32.dll |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.offset | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.open_options | numeric | | 96 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.options | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.process_handle | string | | 0x00000000000004fc |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.process_identifier | numeric | | 552 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.repeat | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.script | string | | (function() { window.google = { kEI: '57j3WdyzAcbwmAH3-6-gDA', kEXPI: '1353458,1353970,1354276,1354401,1354474,1354916,1355004,1355324,1355735,1355820,1356032,1356173,3700278,3700440,4029815,4031109,4041899,4043492,4045841,4048347,4072776,4076999,4078430,4081039,4081164,4092182,4093169,4095910,4097153,4097469,4097922,4097929,4098721,4098728,4098752,4102238,4102827,4103475,4103861,4104259,4104414,4106451,4106452,4107914,4108824,4108894,4109316,4109490,4110259,4110656,4113217,4115404,4115697,4116350,4116724,4116731,4117328,4117979,4118226,4118798,4119032,4119034,4119036,4119811,4119812,4119820,4120414,4120660,4120725,4121035,4121175,4121518,4122184,4122352,4122382,4123640,4123829,4123837,4124091,4124411,4124850,4125837,4126200,4127304,4127473,4127656,4127744,4127775,4127776,4128586,4128875,4128998,4129520,4129555,4129633,4130362,4130412,4130413,4130560,4131073,4131247,4131834,4131879,4132254,4132262,4132456,4132784,4132820,4132956,4132986,4133090,4133113,4133230,4133245,4133416,4133509,4134269,4134328,4134948,4134952,4135088,4135249,4135576,4135744,4135857,4136137,4136220,4136549,4136561,4136580,4137596,4137721,4138258,4138384,4138778,4138780,4138781,4139926,4140017,10200084,10202524,19003868,19003991,19003998,19004000,19004006,19004007,41317155', authuser: 0, kscs: 'c9c918f0_57j3WdyzAcbwmAH3-6-gDA', u: 'c9c918f0', kGL: 'US' }; google.kHL = 'en'; })(); (function() { google.lc = []; google.li = 0; google.getEI = function(a) { for (var b; a && (!a.getAttribute || !(b = a.getAttribute("eid")));) a = a.parentNode; return b || google.kEI }; google.getLEI = function(a) { for (var b = null; a && (!a.getAttribute || !(b = a.getAttribute("leid")));) a = a.parentNode; return b }; google.https = function() { return "https:" == window.location.protocol }; google.ml = function() { return null }; google.wl = function(a, b) { try { google.ml(Error(a), !1, b) } catch (d) {} }; google.time = function() { return (new Date).getTime() }; google.log = function(a, b, d, c, g) { if (a = google.logUrl(a, b, d, c, g)) { b = new Image; var e = google.lc, f = google.li; e[f] = b; b.onerror = b.onload = b.onabort = function() { delete e[f] }; google.vel && google.vel.lu && google.vel.lu(a); b.src = a; google.li = f + 1 } }; google.logUrl = function(a, b, d, c, g) { var e = "", f = google.ls || ""; d || -1 != b.search("&ei=") || (e = "&ei=" + google.getEI(c), -1 == b.search("&lei=") && (c = google.getLEI(c)) && (e += "&lei=" + c)); c = ""; !d && google.cshid && -1 == b.search("&cshid=") && (c = "&cshid=" + google.cshid); a = d || "/" + (g || "gen_204") + "?atyp=i&ct=" + a + "&cad=" + b + e + f + "&zx=" + google.time() + c; /^http:/i.test(a) && google.https() && (google.ml(Error("a"), !1, { src: a, glmm: 1 }), a = ""); return a }; }).call(this); (function() { google.y = {}; google.x = function(a, b) { if (a) var c = a.id; else { do c = Math.random(); while (google.y[c]) } google.y[c] = [a, b]; return !1 }; google.lm = []; google.plm = function(a) { google.lm.push.apply(google.lm, a) }; google.lq = []; google.load = function(a, b, c) { google.lq.push(\[ [a], b, c \]) }; google.loadAll = function(a, b) { google.lq.push([a, b]) }; }).call(this); google.f = {}; (function() { google.c = { c: { a: false, d: false, e: false, i: false, m: true, n: false } }; google.sn = 'webhp'; (function() { var e = { gen204: "iml", clearcut: 8 }; var f = function(a, b, c) { a.addEventListener ? a.removeEventListener(b, c, !1) : a.attachEvent && a.detachEvent("on" + b, c) }, h = function(a, b, c) { g.push({ o: a, s: b, v: c }); a.addEventListener ? a.addEventListener(b, c, !1) : a.attachEvent && a.attachEvent("on" + b, c) }, g = []; google.timers = {}; google.startTick = function(a, b) { var c = b && google.timers[b].t ? google.timers[b].t.start : google.time(); google.timers[a] = { t: { start: c }, e: {}, m: {} }; (c = window.performance) && c.now && (google.timers[a].wsrt = Math.floor(c.now())) }; google.tick = function(a, b, c) { google.timers[a] || google.startTick(a); c = void 0 !== c ? c : google.time(); b instanceof Array || (b = [b]); for (var d = 0; d < b.length; ++d) google.timers[a].t\[b[d].clearcut\] = { key: b[d], ts: c } }; google.c.e = function(a, b, c) { google.timers[a].e[b] = c }; google.c.b = function(a) { var b = google.timers.load.m; b[a] && google.wl("ch_mab", { m: a }); b[a] = !0 }; google.c.u = function(a) { var b = google.timers.load.m; if (b[a]) { b[a] = !1; for (a in b) if (b[a]) return; google.csiReport() } else google.wl("ch_mnb", { m: a }) }; google.rll = function(a, b, c) { var d = function(b) { c(b); f(a, "load", d); f(a, "error", d) }; h(a, "load", d); b && h(a, "error", d) }; google.ull = function() { for (var a; a = g.shift();) f(a.o, a.s, a.v) }; google.iTick = function(a) { var b = google.time(); google.tick("load", e, b); a = a.id || a.src || a.name; google.timers.iml || google.startTick("iml"); google.timers.iml.t[a] = b; google.c.c.a && (google.timers.aft || google.startTick("aft"), google.timers.aft.t[a] = b) }; google.afte = !0; google.aft = function(a) { google.c.c.a && google.afte && (google.timers.aft || google.startTick("aft"), google.timers.aft.t[a.id || a.src || a.name] = google.time()) }; google.c.c.e && google.startTick("webaft"); google.startTick("load"); google.c.b("pr"); google.c.b("xe"); }).call(this); })(); var a = window.location, b = a.href.indexOf("#"); if (0 \<= b) { var c = a.href.substring(b + 1); /(^|&)q=/.test(c) && -1 == c.indexOf("#") && a.replace("/search?" + c.replace(/(^|&)fp=[^&]\*/g, "") + "&cad=h") }; |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.server_random | string | `sha256` | 59f7b8e6f5d74165ca19efa6cd2d046f75c2fd0d34544e2a22371f18e34d87ea |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.share_access | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.skipped | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.src | string | `url` | https://clients1.test.com/generate_204 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.status_info | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.thread_handle | string | | 0x00000000000004f8 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.thread_identifier | numeric | | 1384 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.track | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.arguments.type | string | | key expansion |
action_result.data.\*.report.behavior.processes.\*.calls.\*.category | string | | crypto |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.clsid | string | | INetworkListManager |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.create_disposition | string | | FILE_OPEN |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.create_options | string | | FILE_NON_DIRECTORY_FILE|FILE_SYNCHRONOUS_IO_NONALERT |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.creation_flags | string | | CREATE_SUSPENDED |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.desired_access | string | | FILE_READ_ATTRIBUTES|SYNCHRONIZE |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.file_attributes | string | | FILE_ATTRIBUTE_NORMAL |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.iid | string | | INetworkListManager |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.open_options | string | | FILE_NON_DIRECTORY_FILE|FILE_SYNCHRONOUS_IO_NONALERT |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.share_access | string | | FILE_SHARE_READ |
action_result.data.\*.report.behavior.processes.\*.calls.\*.flags.status_info | string | | FILE_OPENED |
action_result.data.\*.report.behavior.processes.\*.calls.\*.last_error | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.nt_status | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.raw | string | | script |
action_result.data.\*.report.behavior.processes.\*.calls.\*.return_value | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.status | numeric | | 1 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.tid | numeric | | 492 |
action_result.data.\*.report.behavior.processes.\*.calls.\*.time | numeric | | 1509432140.718125 |
action_result.data.\*.report.behavior.processes.\*.command_line | string | `file path` `file name` | C:\\Windows\\system32\\lsass.exe |
action_result.data.\*.report.behavior.processes.\*.first_seen | numeric | | 1509432135.953125 |
action_result.data.\*.report.behavior.processes.\*.modules.\*.baseaddr | string | | 0xff180000 |
action_result.data.\*.report.behavior.processes.\*.modules.\*.basename | string | `file name` | lsass.exe |
action_result.data.\*.report.behavior.processes.\*.modules.\*.filepath | string | `file path` `file name` | C:\\Windows\\system32\\lsass.exe |
action_result.data.\*.report.behavior.processes.\*.modules.\*.imgsize | numeric | | 49152 |
action_result.data.\*.report.behavior.processes.\*.pid | numeric | `pid` | 444 |
action_result.data.\*.report.behavior.processes.\*.ppid | numeric | `pid` | 340 |
action_result.data.\*.report.behavior.processes.\*.process_name | string | `file name` | lsass.exe |
action_result.data.\*.report.behavior.processes.\*.process_path | string | `file path` `file name` | C:\\Windows\\System32\\lsass.exe |
action_result.data.\*.report.behavior.processes.\*.tid | numeric | | 752 |
action_result.data.\*.report.behavior.processes.\*.time | numeric | | 0 |
action_result.data.\*.report.behavior.processes.\*.track | boolean | | True False |
action_result.data.\*.report.behavior.processes.\*.type | string | | process |
action_result.data.\*.report.behavior.processtree.\*.children.\*.command_line | string | | "C:\\Program Files\\Internet Explorer\\iexplore.exe" SCODEF:1432 CREDAT:14337 |
action_result.data.\*.report.behavior.processtree.\*.children.\*.first_seen | numeric | | 1509432139.453125 |
action_result.data.\*.report.behavior.processtree.\*.children.\*.pid | numeric | `pid` | 552 |
action_result.data.\*.report.behavior.processtree.\*.children.\*.ppid | numeric | `pid` | 1432 |
action_result.data.\*.report.behavior.processtree.\*.children.\*.process_name | string | `file name` | iexplore.exe |
action_result.data.\*.report.behavior.processtree.\*.children.\*.track | boolean | | True False |
action_result.data.\*.report.behavior.processtree.\*.command_line | string | `file path` `file name` | C:\\Windows\\system32\\lsass.exe |
action_result.data.\*.report.behavior.processtree.\*.first_seen | numeric | | 1509432135.953125 |
action_result.data.\*.report.behavior.processtree.\*.pid | numeric | `pid` | 444 |
action_result.data.\*.report.behavior.processtree.\*.ppid | numeric | `pid` | 340 |
action_result.data.\*.report.behavior.processtree.\*.process_name | string | `file name` | lsass.exe |
action_result.data.\*.report.behavior.processtree.\*.track | boolean | | True False |
action_result.data.\*.report.behavior.summary.command_line | string | | "C:\\Program Files\\Internet Explorer\\iexplore.exe" SCODEF:1432 CREDAT:14337 |
action_result.data.\*.report.behavior.summary.dll_loaded | string | `file name` | Normaliz.dll |
action_result.data.\*.report.behavior.summary.file_created | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Microsoft\\Internet Explorer\\Recovery\\High\\Active\\{A2380133-BE06-11E7-BB53-080027C008D8}.dat |
action_result.data.\*.report.behavior.summary.file_failed | string | `file path` | C:\\Users\\cuser2\\AppData\\LocalLow\\Microsoft\\CryptnetUrlCache\\MetaData\\828298824EA5549947C17DDABF6871F5_83B81F152A53AA21AE01E022AED042AB |
action_result.data.\*.report.behavior.summary.file_opened | string | `file path` | C:\\Users\\cuser2\\AppData\\Roaming\\Microsoft\\Windows\\Cookies\\index.dat |
action_result.data.\*.report.behavior.summary.file_recreated | string | | \\??\\STORAGE#Volume#{5265d5dc-bb2d-11e7-9a04-806e6f6e6963}#0000000006500000#{53f5630d-b6bf-11d0-94f2-00a0c91efb8b} |
action_result.data.\*.report.behavior.summary.file_written | string | `file path` | C:\\Users\\cuser2\\AppData\\LocalLow\\Microsoft\\CryptnetUrlCache\\Content\\8059E9A0D314877E40FE93D8CCFB3C69_1BF9768FF0DFF2EF4310FBB421A10F13 |
action_result.data.\*.report.behavior.summary.guid | string | | {30a5fb78-e11f-11d1-9064-00c04fd9189d} |
action_result.data.\*.report.behavior.summary.tls_master.\* | string | | 0a1dcd2fe098ee2701df6fa90424c49f2f77f9c695a77665ea373bb2488567e8c1f9a6329b22162876dce75ace639808 |
action_result.data.\*.report.debug.cuckoo | string | | 2017-10-30 23:44:33,838 [cuckoo.core.plugins] DEBUG: Analysis matched signature: network_http |
action_result.data.\*.report.debug.log | string | | 2017-10-30 23:44:15,687 [analyzer] INFO: Analysis completed. |
action_result.data.\*.report.dropped.\*.crc32 | string | | AFDF5A2F |
action_result.data.\*.report.dropped.\*.filepath | string | `file path` | C:\\Users\\cuser2\\AppData\\Local\\Microsoft\\Internet Explorer\\Recovery\\High\\Active\\RecoveryStore.{A2380132-BE06-11E7-BB53-080027C008D8}.dat |
action_result.data.\*.report.dropped.\*.md5 | string | `md5` | d23d18710d507b3b2dee99e1fab56449 |
action_result.data.\*.report.dropped.\*.name | string | | 0ff57aa017e47871_recoverystore.{a2380132-be06-11e7-bb53-080027c008d8}.dat |
action_result.data.\*.report.dropped.\*.path | string | | /home/cuckoo/.cuckoo/storage/analyses/26/files/0ff57aa017e47871_recoverystore.{a2380132-be06-11e7-bb53-080027c008d8}.dat |
action_result.data.\*.report.dropped.\*.pids | numeric | | 552 |
action_result.data.\*.report.dropped.\*.sha1 | string | `sha1` | cbb673d8b2c3d7d55ce62cd4ba03248530594225 |
action_result.data.\*.report.dropped.\*.sha256 | string | `sha256` | 0ff57aa017e47871cd0d9d87232c4914a4e3fc7c48eb4f7fb395de6cfee8f63a |
action_result.data.\*.report.dropped.\*.sha512 | string | | 210b7c5050bbefeabf57c158a1a4ec67974cb173117eebf976c2795084acc1a21ca96fb12c628eaff54fa114245983b262c4ffb803d0a70f5ada372bdd6c08b9 |
action_result.data.\*.report.dropped.\*.size | numeric | | 3584 |
action_result.data.\*.report.dropped.\*.type | string | | Composite Document File V2 Document, No summary info |
action_result.data.\*.report.dropped.\*.urls | string | `url` | https://news.test.com/nwshp?hl=en |
action_result.data.\*.report.info.added | numeric | | 1509406935.63986 |
action_result.data.\*.report.info.category | string | | url |
action_result.data.\*.report.info.custom | string | | |
action_result.data.\*.report.info.duration | numeric | | 130 |
action_result.data.\*.report.info.ended | numeric | | 1509407067.167103 |
action_result.data.\*.report.info.git.fetch_head | string | | |
action_result.data.\*.report.info.git.head | string | | |
action_result.data.\*.report.info.id | numeric | | 26 |
action_result.data.\*.report.info.machine.label | string | | cuckoo2 |
action_result.data.\*.report.info.machine.manager | string | | VirtualBox |
action_result.data.\*.report.info.machine.name | string | | cuckoo2 |
action_result.data.\*.report.info.machine.shutdown_on | string | | 2017-10-30 23:44:27 |
action_result.data.\*.report.info.machine.started_on | string | | 2017-10-30 23:42:16 |
action_result.data.\*.report.info.machine.status | string | | stopped |
action_result.data.\*.report.info.monitor | string | `sha1` | 2bd01ede5c5258d5fce2e38bc58348a62c11ce33 |
action_result.data.\*.report.info.options | string | | |
action_result.data.\*.report.info.owner | string | | |
action_result.data.\*.report.info.package | string | | |
action_result.data.\*.report.info.platform | string | | |
action_result.data.\*.report.info.route | string | | none |
action_result.data.\*.report.info.score | numeric | | 0.8 |
action_result.data.\*.report.info.started | numeric | | 1509406936.583892 |
action_result.data.\*.report.info.version | string | | 2.0.3 |
action_result.data.\*.report.metadata.output.dropped.\*.basename | string | | 0ff57aa017e47871_recoverystore.{a2380132-be06-11e7-bb53-080027c008d8}.dat |
action_result.data.\*.report.metadata.output.dropped.\*.dirname | string | | files |
action_result.data.\*.report.metadata.output.dropped.\*.sha256 | string | `sha256` | 0ff57aa017e47871cd0d9d87232c4914a4e3fc7c48eb4f7fb395de6cfee8f63a |
action_result.data.\*.report.metadata.output.pcap.basename | string | | dump.pcap |
action_result.data.\*.report.metadata.output.pcap.dirname | string | | |
action_result.data.\*.report.metadata.output.pcap.sha256 | string | `sha256` | 3885351e8a803cfa9cfd1851b39a691626ad429d2e72a8522c47680bc7018f6f |
action_result.data.\*.report.network.dns.\*.answers.\*.data | string | `ip` | 172.217.12.174 |
action_result.data.\*.report.network.dns.\*.answers.\*.type | string | | A |
action_result.data.\*.report.network.dns.\*.request | string | | clients1.test.com |
action_result.data.\*.report.network.dns.\*.type | string | | A |
action_result.data.\*.report.network.dns_servers | string | `ip` | 8.8.8.8 |
action_result.data.\*.report.network.domains.\*.domain | string | `domain` | teredo.ipv6.microsoft.com |
action_result.data.\*.report.network.domains.\*.ip | string | `ip` | |
action_result.data.\*.report.network.hosts | string | `ip` | 8.8.8.8 |
action_result.data.\*.report.network.http.\*.body | string | | |
action_result.data.\*.report.network.http.\*.count | numeric | | 1 |
action_result.data.\*.report.network.http.\*.data | string | | GET /MFEwTzBNMEswSTAJBgUrDgMCGgUABBQQX6Z6gAidtSefNc6DC0OInqPHDQQUD4BhHIIxYdUvKOeNRji0LOHG2eICEA05NXoFG5trTNWktC30S2A%3D HTTP/1.1
Cache-Control: max-age = 172800
Connection: Keep-Alive
Accept: \*/\*
If-Modified-Since: Fri, 27 Oct 2017 07:10:24 GMT
If-None-Match: "59f2dbe0-1d7"
User-Agent: Microsoft-CryptoAPI/6.1
Host: ocsp.digicert.com |
action_result.data.\*.report.network.http.\*.host | string | | ocsp.digicert.com |
action_result.data.\*.report.network.http.\*.method | string | | GET |
action_result.data.\*.report.network.http.\*.path | string | | /MFEwTzBNMEswSTAJBgUrDgMCGgUABBQQX6Z6gAidtSefNc6DC0OInqPHDQQUD4BhHIIxYdUvKOeNRji0LOHG2eICEA05NXoFG5trTNWktC30S2A%3D |
action_result.data.\*.report.network.http.\*.port | numeric | | 80 |
action_result.data.\*.report.network.http.\*.uri | string | `url` | http://ocsp.digicert.com/MFEwTzBNMEswSTAJBgUrDgMCGgUABBQQX6Z6gAidtSefNc6DC0OInqPHDQQUD4BhHIIxYdUvKOeNRji0LOHG2eICEA05NXoFG5trTNWktC30S2A%3D |
action_result.data.\*.report.network.http.\*.user-agent | string | | Microsoft-CryptoAPI/6.1 |
action_result.data.\*.report.network.http.\*.version | string | | 1.1 |
action_result.data.\*.report.network.http_ex.\*.dport | numeric | | 80 |
action_result.data.\*.report.network.http_ex.\*.dst | string | `ip` | 204.79.197.200 |
action_result.data.\*.report.network.http_ex.\*.host | string | | www.bing.com |
action_result.data.\*.report.network.http_ex.\*.md5 | string | `md5` | 5b188904e3bc002102653489e7ac4a4a |
action_result.data.\*.report.network.http_ex.\*.method | string | | GET |
action_result.data.\*.report.network.http_ex.\*.path | string | | /home/cuckoo/.cuckoo/storage/analyses/26/network/96607ba47296757df3a005614947a5e83ba8683d |
action_result.data.\*.report.network.http_ex.\*.protocol | string | `url` | http |
action_result.data.\*.report.network.http_ex.\*.req.md5 | string | `md5` | d41d8cd98f00b204e9800998ecf8427e |
action_result.data.\*.report.network.http_ex.\*.req.path | string | | /home/cuckoo/.cuckoo/storage/analyses/26/network/da39a3ee5e6b4b0d3255bfef95601890afd80709 |
action_result.data.\*.report.network.http_ex.\*.req.sha1 | string | `sha1` | da39a3ee5e6b4b0d3255bfef95601890afd80709 |
action_result.data.\*.report.network.http_ex.\*.request | string | | GET /favicon.ico HTTP/1.1
Accept: \*/\*
UA-CPU: AMD64
Accept-Encoding: gzip, deflate
User-Agent: Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1; Win64; x64; Trident/4.0; .NET CLR 2.0.50727; SLCC2; .NET CLR 3.5.30729; .NET CLR 3.0.30729; Media Center PC 6.0)
Host: www.bing.com
Connection: Keep-Alive
Cookie: MUID=0216A86C28F06A303FDDA3442CF06910; SRCHD=AF=NOFORM; SRCHUID=V=2&GUID=1E864A320AF643328ED04DF34386039A&dmnchg=1; SRCHUSR=DOB=20171027 |
action_result.data.\*.report.network.http_ex.\*.resp.md5 | string | `md5` | 5b188904e3bc002102653489e7ac4a4a |
action_result.data.\*.report.network.http_ex.\*.resp.path | string | | /home/cuckoo/.cuckoo/storage/analyses/26/network/96607ba47296757df3a005614947a5e83ba8683d |
action_result.data.\*.report.network.http_ex.\*.resp.sha1 | string | `sha1` | 96607ba47296757df3a005614947a5e83ba8683d |
action_result.data.\*.report.network.http_ex.\*.response | string | | HTTP/1.1 200 OK
Cache-Control: public, max-age=15552000
Content-Type: image/x-icon
Last-Modified: Sat, 28 Oct 2017 06:23:40 GMT
Vary: Accept-Encoding
Date: Mon, 30 Oct 2017 23:42:29 GMT
Content-Length: 300 |
action_result.data.\*.report.network.http_ex.\*.sha1 | string | `sha1` | 96607ba47296757df3a005614947a5e83ba8683d |
action_result.data.\*.report.network.http_ex.\*.sport | numeric | | 49167 |
action_result.data.\*.report.network.http_ex.\*.src | string | `ip` | 192.168.56.11 |
action_result.data.\*.report.network.http_ex.\*.status | numeric | | 200 |
action_result.data.\*.report.network.http_ex.\*.uri | string | | /favicon.ico |
action_result.data.\*.report.network.https_ex.\*.dport | numeric | | 443 |
action_result.data.\*.report.network.https_ex.\*.dst | string | `ip` | 172.217.6.196 |
action_result.data.\*.report.network.https_ex.\*.host | string | | www.test.com |
action_result.data.\*.report.network.https_ex.\*.md5 | string | `md5` | d41d8cd98f00b204e9800998ecf8427e |
action_result.data.\*.report.network.https_ex.\*.method | string | | GET |
action_result.data.\*.report.network.https_ex.\*.path | string | | /home/cuckoo/.cuckoo/storage/analyses/26/network/da39a3ee5e6b4b0d3255bfef95601890afd80709 |
action_result.data.\*.report.network.https_ex.\*.protocol | string | `url` | https |
action_result.data.\*.report.network.https_ex.\*.req.md5 | string | `md5` | d41d8cd98f00b204e9800998ecf8427e |
action_result.data.\*.report.network.https_ex.\*.req.path | string | | /home/cuckoo/.cuckoo/storage/analyses/26/network/da39a3ee5e6b4b0d3255bfef95601890afd80709 |
action_result.data.\*.report.network.https_ex.\*.req.sha1 | string | `sha1` | da39a3ee5e6b4b0d3255bfef95601890afd80709 |
action_result.data.\*.report.network.https_ex.\*.request | string | | GET / HTTP/1.1
Accept: \*/\*
Accept-Language: en-us
User-Agent: Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1; Win64; x64; Trident/4.0; .NET CLR 2.0.50727; SLCC2; .NET CLR 3.5.30729; .NET CLR 3.0.30729; Media Center PC 6.0)
UA-CPU: AMD64
Accept-Encoding: gzip, deflate
Host: www.google.com
Connection: Keep-Alive
Cookie: 1P_JAR=2017-10-27-09; NID=115=m6DKd90oolXddqRUqoi43HkYuI7jqX7-XHbsm8C794Z5sGpMoD-KutRWJWJ3jpuMK937_w4erRNAsL1iLtwYXKt5BJKgzdvr_wMZYXw4h6rnrbYWvbkrEvEJevSvvCrZ |
action_result.data.\*.report.network.https_ex.\*.resp.md5 | string | `md5` | d41d8cd98f00b204e9800998ecf8427e |
action_result.data.\*.report.network.https_ex.\*.resp.path | string | | /home/cuckoo/.cuckoo/storage/analyses/26/network/da39a3ee5e6b4b0d3255bfef95601890afd80709 |
action_result.data.\*.report.network.https_ex.\*.resp.sha1 | string | `sha1` | da39a3ee5e6b4b0d3255bfef95601890afd80709 |
action_result.data.\*.report.network.https_ex.\*.response | string | | |
action_result.data.\*.report.network.https_ex.\*.sha1 | string | `sha1` | da39a3ee5e6b4b0d3255bfef95601890afd80709 |
action_result.data.\*.report.network.https_ex.\*.sport | numeric | | 49166 |
action_result.data.\*.report.network.https_ex.\*.src | string | `ip` | 192.168.56.11 |
action_result.data.\*.report.network.https_ex.\*.status | numeric | | 0 |
action_result.data.\*.report.network.https_ex.\*.uri | string | | / |
action_result.data.\*.report.network.pcap_sha256 | string | `sha256` | 3885351e8a803cfa9cfd1851b39a691626ad429d2e72a8522c47680bc7018f6f |
action_result.data.\*.report.network.sorted_pcap_sha256 | string | `sha256` | 35d9251cf3fc2d0f9ee0d88d8b9a6d37cca28bdf2cde75b390eb525a1927f892 |
action_result.data.\*.report.network.tcp.\*.dport | numeric | | 80 |
action_result.data.\*.report.network.tcp.\*.dst | string | `ip` | 104.18.55.167 |
action_result.data.\*.report.network.tcp.\*.offset | numeric | | 1476 |
action_result.data.\*.report.network.tcp.\*.sport | numeric | | 49186 |
action_result.data.\*.report.network.tcp.\*.src | string | `ip` | 192.168.56.11 |
action_result.data.\*.report.network.tcp.\*.time | numeric | | 62.29629588127136 |
action_result.data.\*.report.network.tls.\*.server_random | string | `sha256` | 59f7b8e8bc9cd7d38e4207da89c854c6582849d9c3f304c6835c396c0178ea32 |
action_result.data.\*.report.network.tls.\*.session_id | string | `sha256` | d60ad168adf3e7c281cc9a1c0fdcfb41d35516110c4501c272c15cf813d46452 |
action_result.data.\*.report.network.udp.\*.dport | numeric | | 5355 |
action_result.data.\*.report.network.udp.\*.dst | string | `ip` | 224.0.0.252 |
action_result.data.\*.report.network.udp.\*.offset | numeric | | 85231 |
action_result.data.\*.report.network.udp.\*.sport | numeric | | 51966 |
action_result.data.\*.report.network.udp.\*.src | string | `ip` | 192.168.56.11 |
action_result.data.\*.report.network.udp.\*.time | numeric | | 6.423335075378418 |
action_result.data.\*.report.screenshots.\*.ocr | string | | |
action_result.data.\*.report.screenshots.\*.path | string | | /home/cuckoo/.cuckoo/storage/analyses/26/shots/0001.jpg |
action_result.data.\*.report.signatures.\*.description | string | | Executes javascript |
action_result.data.\*.report.signatures.\*.markcount | numeric | | 1 |
action_result.data.\*.report.signatures.\*.marks.\*.call.api | string | | COleScript_Compile |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.script | string | | (function() { window.google = { kEI: '57j3WdyzAcbwmAH3-6-gDA', kEXPI: '1353458,1353970,1354276,1354401,1354474,1354916,1355004,1355324,1355735,1355820,1356032,1356173,3700278,3700440,4029815,4031109,4041899,4043492,4045841,4048347,4072776,4076999,4078430,4081039,4081164,4092182,4093169,4095910,4097153,4097469,4097922,4097929,4098721,4098728,4098752,4102238,4102827,4103475,4103861,4104259,4104414,4106451,4106452,4107914,4108824,4108894,4109316,4109490,4110259,4110656,4113217,4115404,4115697,4116350,4116724,4116731,4117328,4117979,4118226,4118798,4119032,4119034,4119036,4119811,4119812,4119820,4120414,4120660,4120725,4121035,4121175,4121518,4122184,4122352,4122382,4123640,4123829,4123837,4124091,4124411,4124850,4125837,4126200,4127304,4127473,4127656,4127744,4127775,4127776,4128586,4128875,4128998,4129520,4129555,4129633,4130362,4130412,4130413,4130560,4131073,4131247,4131834,4131879,4132254,4132262,4132456,4132784,4132820,4132956,4132986,4133090,4133113,4133230,4133245,4133416,4133509,4134269,4134328,4134948,4134952,4135088,4135249,4135576,4135744,4135857,4136137,4136220,4136549,4136561,4136580,4137596,4137721,4138258,4138384,4138778,4138780,4138781,4139926,4140017,10200084,10202524,19003868,19003991,19003998,19004000,19004006,19004007,41317155', authuser: 0, kscs: 'c9c918f0_57j3WdyzAcbwmAH3-6-gDA', u: 'c9c918f0', kGL: 'US' }; google.kHL = 'en'; })(); (function() { google.lc = []; google.li = 0; google.getEI = function(a) { for (var b; a && (!a.getAttribute || !(b = a.getAttribute("eid")));) a = a.parentNode; return b || google.kEI }; google.getLEI = function(a) { for (var b = null; a && (!a.getAttribute || !(b = a.getAttribute("leid")));) a = a.parentNode; return b }; google.https = function() { return "https:" == window.location.protocol }; google.ml = function() { return null }; google.wl = function(a, b) { try { google.ml(Error(a), !1, b) } catch (d) {} }; google.time = function() { return (new Date).getTime() }; google.log = function(a, b, d, c, g) { if (a = google.logUrl(a, b, d, c, g)) { b = new Image; var e = google.lc, f = google.li; e[f] = b; b.onerror = b.onload = b.onabort = function() { delete e[f] }; google.vel && google.vel.lu && google.vel.lu(a); b.src = a; google.li = f + 1 } }; google.logUrl = function(a, b, d, c, g) { var e = "", f = google.ls || ""; d || -1 != b.search("&ei=") || (e = "&ei=" + google.getEI(c), -1 == b.search("&lei=") && (c = google.getLEI(c)) && (e += "&lei=" + c)); c = ""; !d && google.cshid && -1 == b.search("&cshid=") && (c = "&cshid=" + google.cshid); a = d || "/" + (g || "gen_204") + "?atyp=i&ct=" + a + "&cad=" + b + e + f + "&zx=" + google.time() + c; /^http:/i.test(a) && google.https() && (google.ml(Error("a"), !1, { src: a, glmm: 1 }), a = ""); return a }; }).call(this); (function() { google.y = {}; google.x = function(a, b) { if (a) var c = a.id; else { do c = Math.random(); while (google.y[c]) } google.y[c] = [a, b]; return !1 }; google.lm = []; google.plm = function(a) { google.lm.push.apply(google.lm, a) }; google.lq = []; google.load = function(a, b, c) { google.lq.push(\[ [a], b, c \]) }; google.loadAll = function(a, b) { google.lq.push([a, b]) }; }).call(this); google.f = {}; (function() { google.c = { c: { a: false, d: false, e: false, i: false, m: true, n: false } }; google.sn = 'webhp'; (function() { var e = { gen204: "iml", clearcut: 8 }; var f = function(a, b, c) { a.addEventListener ? a.removeEventListener(b, c, !1) : a.attachEvent && a.detachEvent("on" + b, c) }, h = function(a, b, c) { g.push({ o: a, s: b, v: c }); a.addEventListener ? a.addEventListener(b, c, !1) : a.attachEvent && a.attachEvent("on" + b, c) }, g = []; google.timers = {}; google.startTick = function(a, b) { var c = b && google.timers[b].t ? google.timers[b].t.start : google.time(); google.timers[a] = { t: { start: c }, e: {}, m: {} }; (c = window.performance) && c.now && (google.timers[a].wsrt = Math.floor(c.now())) }; google.tick = function(a, b, c) { google.timers[a] || google.startTick(a); c = void 0 !== c ? c : google.time(); b instanceof Array || (b = [b]); for (var d = 0; d < b.length; ++d) google.timers[a].t\[b[d].clearcut\] = { key: b[d], ts: c } }; google.c.e = function(a, b, c) { google.timers[a].e[b] = c }; google.c.b = function(a) { var b = google.timers.load.m; b[a] && google.wl("ch_mab", { m: a }); b[a] = !0 }; google.c.u = function(a) { var b = google.timers.load.m; if (b[a]) { b[a] = !1; for (a in b) if (b[a]) return; google.csiReport() } else google.wl("ch_mnb", { m: a }) }; google.rll = function(a, b, c) { var d = function(b) { c(b); f(a, "load", d); f(a, "error", d) }; h(a, "load", d); b && h(a, "error", d) }; google.ull = function() { for (var a; a = g.shift();) f(a.o, a.s, a.v) }; google.iTick = function(a) { var b = google.time(); google.tick("load", e, b); a = a.id || a.src || a.name; google.timers.iml || google.startTick("iml"); google.timers.iml.t[a] = b; google.c.c.a && (google.timers.aft || google.startTick("aft"), google.timers.aft.t[a] = b) }; google.afte = !0; google.aft = function(a) { google.c.c.a && google.afte && (google.timers.aft || google.startTick("aft"), google.timers.aft.t[a.id || a.src || a.name] = google.time()) }; google.c.c.e && google.startTick("webaft"); google.startTick("load"); google.c.b("pr"); google.c.b("xe"); }).call(this); })(); var a = window.location, b = a.href.indexOf("#"); if (0 \<= b) { var c = a.href.substring(b + 1); /(^|&)q=/.test(c) && -1 == c.indexOf("#") && a.replace("/search?" + c.replace(/(^|&)fp=[^&]\*/g, "") + "&cad=h") }; |
action_result.data.\*.report.signatures.\*.marks.\*.call.arguments.type | string | | JScript - window script block |
action_result.data.\*.report.signatures.\*.marks.\*.call.category | string | | iexplore |
action_result.data.\*.report.signatures.\*.marks.\*.call.raw | string | | script |
action_result.data.\*.report.signatures.\*.marks.\*.call.return_value | numeric | | 0 |
action_result.data.\*.report.signatures.\*.marks.\*.call.status | numeric | | 1 |
action_result.data.\*.report.signatures.\*.marks.\*.call.tid | numeric | | 1624 |
action_result.data.\*.report.signatures.\*.marks.\*.call.time | numeric | | 1509432142.171125 |
action_result.data.\*.report.signatures.\*.marks.\*.category | string | | request |
action_result.data.\*.report.signatures.\*.marks.\*.cid | numeric | | 540 |
action_result.data.\*.report.signatures.\*.marks.\*.ioc | string | | GET http://www.bing.com/favicon.ico |
action_result.data.\*.report.signatures.\*.marks.\*.pid | numeric | `pid` | 552 |
action_result.data.\*.report.signatures.\*.marks.\*.type | string | | call |
action_result.data.\*.report.signatures.\*.name | string | | js_eval |
action_result.data.\*.report.signatures.\*.severity | numeric | | 2 |
action_result.data.\*.report.target.category | string | | url |
action_result.data.\*.report.target.url | string | `url` | https://www.test.com |
action_result.data.\*.task_status.added_on | string | | Mon, 30 Oct 2017 23:42:15 GMT |
action_result.data.\*.task_status.category | string | | url |
action_result.data.\*.task_status.clock | string | | Mon, 30 Oct 2017 23:42:15 GMT |
action_result.data.\*.task_status.completed_on | string | | Mon, 30 Oct 2017 23:44:27 GMT |
action_result.data.\*.task_status.custom | string | | |
action_result.data.\*.task_status.duration | numeric | | 130 |
action_result.data.\*.task_status.enforce_timeout | boolean | | True False |
action_result.data.\*.task_status.guest.id | numeric | | 26 |
action_result.data.\*.task_status.guest.label | string | | cuckoo2 |
action_result.data.\*.task_status.guest.manager | string | | VirtualBox |
action_result.data.\*.task_status.guest.name | string | | cuckoo2 |
action_result.data.\*.task_status.guest.shutdown_on | string | | 2017-10-30 23:44:27 |
action_result.data.\*.task_status.guest.started_on | string | | 2017-10-30 23:42:16 |
action_result.data.\*.task_status.guest.status | string | | stopped |
action_result.data.\*.task_status.guest.task_id | numeric | | 26 |
action_result.data.\*.task_status.id | numeric | | 26 |
action_result.data.\*.task_status.machine | string | | |
action_result.data.\*.task_status.memory | boolean | | True False |
action_result.data.\*.task_status.owner | string | | |
action_result.data.\*.task_status.package | string | | |
action_result.data.\*.task_status.platform | string | | |
action_result.data.\*.task_status.priority | numeric | | 1 |
action_result.data.\*.task_status.route | string | | none |
action_result.data.\*.task_status.started_on | string | | Mon, 30 Oct 2017 23:42:16 GMT |
action_result.data.\*.task_status.status | string | | reported |
action_result.data.\*.task_status.target | string | `url` | https://www.test.com |
action_result.data.\*.task_status.timeout | numeric | | 0 |
action_result.status | string | | success failed |
action_result.message | string | | Successfully retrieved report |
action_result.summary.id | numeric | `cuckoo task id` | 26 |
action_result.summary.results_url | string | `url` | https://10.16.6.42:8000/analysis/27/summary |
action_result.summary.target | string | `url` | https://www.test.com |
summary.total_objects | numeric | | 1 |
summary.total_objects_successful | numeric | | 1 |

## action: 'submit strings'

Add VirusTotal compatible URL/Domain to the list of pending tasks

Type: **generic** \
Read only: **False**

#### Action Parameters

PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**url** | required | Single VirusTotal compatible URL/Domain | string | `url` `domain` |

#### Action Output

DATA PATH | TYPE | CONTAINS | EXAMPLE VALUES
--------- | ---- | -------- | --------------
action_result.parameter.url | string | `url` `domain` | test.com |
action_result.data.\*.task_status.started_on | string | | |
action_result.data.\*.task_status.sample.sha1 | string | `sha1` | 923c2f90bc6724529f9839c7ff22b75863bfb84d |
action_result.data.\*.task_status.sample.file_type | string | | PE32 executable (GUI) Intel 80386, for MS Windows |
action_result.data.\*.task_status.sample.file_size | numeric | | 2545000 |
action_result.data.\*.task_status.sample.crc32 | string | | 062A9292 |
action_result.data.\*.task_status.sample.ssdeep | string | | 49152:VbAc4crr5oZ5iclHlYLtZp3TRIQL2LWX7M7j3JbTe2IqVo/:Bx4cJodFYpPDRIs2WCj3le2HVo/ |
action_result.data.\*.task_status.sample.sha256 | string | `sha256` | eb221521e2eb2651a9318e1487041cca36c75714ee4be548c8bbac160bf0ce03 |
action_result.data.\*.task_status.sample.sha512 | string | | 267a168f6b8cc90fbf71bf1e7bee55ea778a69d5137fb591305339ae817b985b50148848605ea2efcb3a1549f5e49be3ec801511f7d43cb6a6c593adc2d82138 |
action_result.data.\*.task_status.sample.id | numeric | | 1 |
action_result.data.\*.task_status.sample.md5 | string | `md5` | 653222ac6b246b20eb2aee1f2952e8c5 |
action_result.data.\*.task_status.owner | string | | |
action_result.data.\*.task_status.sample_id | numeric | | 1 |
action_result.data.\*.task_status.duration | numeric | | -1 |
action_result.data.\*.task_status.id | numeric | | 16 |
action_result.data.\*.task_status.category | string | | file url |
action_result.data.\*.task_status.machine | string | | |
action_result.data.\*.task_status.clock | string | | Sun, 07 Jun 2020 00:18:07 GMT |
action_result.data.\*.task_status.custom | string | | |
action_result.data.\*.task_status.priority | numeric | | 1 |
action_result.data.\*.task_status.platform | string | | windows |
action_result.data.\*.task_status.memory | boolean | | True False |
action_result.data.\*.task_status.status | string | | pending |
action_result.data.\*.task_status.processing | string | | |
action_result.data.\*.task_status.enforce_timeout | boolean | | True False |
action_result.data.\*.task_status.target | string | `url` | /tmp/cuckoo-tmp/tmpwwgL_J/eb221521e2eb2651a9318e1487041cca36c75714ee4be548c8bbac160bf0ce03 |
action_result.data.\*.task_status.completed_on | string | | |
action_result.data.\*.task_status.package | string | | exe |
action_result.data.\*.task_status.route | string | | |
action_result.data.\*.task_status.timeout | numeric | | 0 |
action_result.data.\*.task_status.submit_id | numeric | | 58 |
action_result.data.\*.task_status.options.procmemdump | string | | yes |
action_result.data.\*.task_status.added_on | string | | Sun, 07 Jun 2020 00:18:07 GMT |
action_result.status | string | | success |
action_result.message | string | | 16: eb221521e2eb2651a9318e1487041cca36c75714ee4be548c8bbac160bf0ce03, 17: eb221521e2eb2651a9318e1487041cca36c75714ee4be548c8bbac160bf0ce03 |
action_result.summary.id | numeric | | 1505 |
action_result.summary.target | string | | test.com |
action_result.summary.results_url | string | `url` | http://10.1.16.69:8000/analysis/1505 |
summary.total_objects | numeric | | 1 |
summary.total_objects_successful | numeric | | 1 |

______________________________________________________________________

Auto-generated Splunk SOAR Connector documentation.

Copyright 2025 Splunk Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and limitations under the License.
