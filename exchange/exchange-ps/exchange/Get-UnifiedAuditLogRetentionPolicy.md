---
external help file: Microsoft.Exchange.TransportMailflow-Help.xml
online version: https://docs.microsoft.com/powershell/module/exchange/get-unifiedauditlogretentionpolicy
applicable: Security & Compliance Center
title: Get-UnifiedAuditLogRetentionPolicy
schema: 2.0.0
author: chrisda
ms.author: chrisda
ms.reviewer:
---

# Get-UnifiedAuditLogRetentionPolicy

## SYNOPSIS
This cmdlet is available only in Security & Compliance Center PowerShell. For more information, see [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/scc-powershell).

Use the Get-UnifiedAuditLogRetentionPolicy cmdlet to view the properties of the audit log retention policies in the Microsoft 365 Defender portal or the Microsoft Purview compliance portal.

For information about the parameter sets in the Syntax section below, see [Exchange cmdlet syntax](https://docs.microsoft.com/powershell/exchange/exchange-cmdlet-syntax).

## SYNTAX

```
Get-UnifiedAuditLogRetentionPolicy
 [-Operation <String>]
 [-RecordType <AuditRecordType>]
 [-RetentionDuration <UnifiedAuditLogRetentionDuration>]
 [-UserId <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Audit log retention policies are used to specify a retention duration for audit logs for that are generated by admin and user activity. An audit log retention policy can specify the retention duration based on the type of audited activities, the Microsoft 365 service that activities are performed in, or the users who performed the activities. For more information, see [Manage audit log retention policies](https://docs.microsoft.com/microsoft-365/compliance/audit-log-retention-policies).

To use this cmdlet in Security & Compliance Center PowerShell, you need to be assigned permissions. For more information, see [Permissions in the Microsoft 365 Defender portal](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-microsoft-365-security-center) or [Permissions in the Microsoft Purview compliance portal](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center-permissions).

## EXAMPLES

### Example 1
```powershell
Get-UnifiedAuditLogRetentionPolicy | Sort-Object -Property Priority | Format-List Priority,Name,Description,RecordTypes,Operations,UserIds,RetentionDuration
```

This example lists the configurable properties for all audit log retention policies in your organization. The command also lists the policies in order of highest to lowest priority.

### Example 2
```powershell
Get-UnifiedAuditLogRetentionPolicy -RecordType ExchangeItem | Format-List Name,Description,RecordTypes,Operations,UserIds,RetentionDuration,Priority
```

This example lists the configurable properties for all audit log retention policies that apply to audit records the record type of ExchangeItem.

## PARAMETERS

### -Operation
The Operations parameter filters the results by the operations that are specified in the policy. For a list of the available values for this parameter, see [Audited activities](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#audited-activities).

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance Center

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecordType
The RecordType parameter filters the results by the record types that are defined in the policy. For details about the available values, see [AuditLogRecordType](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).

```yaml
Type: AuditRecordType
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance Center

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RetentionDuration
The RetentionDuration parameter filters the policy results by the retention duration specified in the policy. Valid values are:

- ThreeMonths
- SixMonths
- NineMonths
- TwelveMonths
- TenYears

```yaml
Type: UnifiedAuditLogRetentionDuration
Parameter Sets: (All)
Aliases:
Accepted values: ThreeMonths, SixMonths, NineMonths, TwelveMonths, TenYears
Applicable: Security & Compliance Center

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserId
The UserIds parameter filters the policy results by the ID of the users who are specified in the policy.

You can enter multiple values separated by commas. If the values contain spaces or otherwise require quotation marks, use the following syntax: `"Value1","Value2",..."ValueN"`.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Applicable: Security & Compliance Center

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/p/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
