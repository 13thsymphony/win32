---
description: Gets the security descriptor that controls who is allowed to start a DCOM application.
ms.assetid: ba02807f-aa2a-4b1c-9692-2803d93cd2ee
ms.tgt_platform: multiple
title: GetLaunchSecurityDescriptor method of the Win32_DCOMApplicationSetting class
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- Win32_DCOMApplicationSetting.GetLaunchSecurityDescriptor
api_type: 
- COM
api_location: 
- CIMWin32.dll
---

# GetLaunchSecurityDescriptor method of the Win32\_DCOMApplicationSetting class

The **GetLaunchSecurityDescriptor** WMI method gets the security descriptor that controls who is allowed to start a DCOM application. The security descriptor is an instance of the [**Win32\_SecurityDescriptor**](/previous-versions/windows/desktop/secrcw32prov/win32-securitydescriptor) class. The account running the script or application that calls this method must have the **SeSecurityPrivilege** and **SeRestorePrivilege** privileges. For more information, see [Changing Access Security on Securable Objects](/windows/desktop/WmiSdk/changing-access-security-on-securable-objects).

## Syntax


```mof
uint32 GetLaunchSecurityDescriptor(
  [out] Win32_SecurityDescriptor Descriptor
);
```



## Parameters

<dl> <dt>

*Descriptor* \[out\]
</dt> <dd>

The security descriptor to set that controls who can start the DCOM application.

</dd> </dl>

## Return value

Returns one of the values listed in the following list, or a different value to indicate an error. For more information, see [WMI Return Codes](/windows/desktop/WmiSdk/wmi-return-codes) or [**WbemErrorEnum**](/windows/desktop/api/wbemdisp/ne-wbemdisp-wbemerrorenum).

<dl> <dt>

**Success**
</dt> <dd>

0

Successful completion.

</dd> <dt>

**2**
</dt> <dd>

The user does not have access to the requested information.

</dd> <dt>

**8**
</dt> <dd>

Unknown failure.

</dd> <dt>

**9**
</dt> <dd>

The user does not have adequate privileges to execute the method.

</dd> <dt>

**21**
</dt> <dd>

A parameter specified in the method call is not valid.

</dd> <dt>

**Other**
</dt> <dd>

1 4294967295

</dd> </dl>

## Remarks

The [**Win32\_SecurityDescriptor**](/previous-versions/windows/desktop/secrcw32prov/win32-securitydescriptor) instance represents a [**SECURITY\_DESCRIPTOR\_CONTROL**](/windows/desktop/SecAuthZ/security-descriptor-control) data type and contains a [*discretionary access control list*](/windows/desktop/SecGloss/d-gly) (DACL) and a [*system access control list*](/windows/desktop/SecGloss/s-gly) (SACL). For more information, see [Access Control Lists](/windows/desktop/SecAuthZ/access-control-lists).

If the **SeSecurityPrivilege** is not granted or enabled when getting a security descriptor, then only the DACL is returned in the returned security descriptor. For more information, see [**Privilege Constants**](/windows/desktop/WmiSdk/privilege-constants) and [Executing Privileged Operations](/windows/desktop/WmiSdk/executing-privileged-operations).

## Requirements



| Requirement | Value |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>                                                                |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                          |
| Namespace<br/>                | Root\\CIMV2<br/>                                                                  |
| MOF<br/>                      | <dl> <dt>CIMWin32.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>CIMWin32.dll</dt> </dl> |



## See also

<dl> <dt>

[**Win32\_DCOMApplicationSetting**](win32-dcomapplicationsetting.md)
</dt> <dt>

[**Privilege Constants**](/windows/desktop/WmiSdk/privilege-constants)
</dt> <dt>

[WMI Security Descriptor Objects](/windows/desktop/WmiSdk/wmi-security-descriptor-objects)
</dt> <dt>

[Changing Access Security on Securable Objects](/windows/desktop/WmiSdk/changing-access-security-on-securable-objects)
</dt> </dl>

 

