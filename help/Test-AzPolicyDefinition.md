---
external help file: AzPolicyTest-help.xml
Module Name: AzPolicyTest
online version: https://github.com/tyconsulting/AzPolicyTest/blob/master/help/Test-AzPolicyDefinition.md
schema: 2.0.0
---

# Test-AzPolicyDefinition

## SYNOPSIS

Perform Pester Test to test Azure Policy definitions

## SYNTAX

### PathNoOutputFile (Default)

```
Test-AzPolicyDefinition -Path <String> [-ExcludePath <String[]>] [-ExcludeTags <String[]>]
 [-PesterVerbosity <String>] [-ProgressAction <ActionPreference>] [<CommonParameters>]
```

### PathProduceOutputFile

```
Test-AzPolicyDefinition -Path <String> [-ExcludePath <String[]>] [-ExcludeTags <String[]>] -OutputFile <String>
 [-OutputFormat <String>] [-PesterVerbosity <String>] [-ProgressAction <ActionPreference>] [<CommonParameters>]
```

### ContentNoOutputFile

```
Test-AzPolicyDefinition -Content <String> [-ExcludeTags <String[]>] [-PesterVerbosity <String>]
 [-ProgressAction <ActionPreference>] [<CommonParameters>]
```

### ContentProduceOutputFile

```
Test-AzPolicyDefinition -Content <String> [-ExcludeTags <String[]>] -OutputFile <String>
 [-OutputFormat <String>] [-PesterVerbosity <String>] [-ProgressAction <ActionPreference>] [<CommonParameters>]
```

## DESCRIPTION

## EXAMPLES

### EXAMPLE 1

```powershell
C:\PS> Test-AzPolicyDefinition -Path "C:\PolicyDefinitionFolder"
```

Test all Azure Policy definitions in a folder and its subfolders and display Pester result on the PowerShell host

### EXAMPLE 2

```powershell
C:\PS> Test-AzPolicyDefinition -Path "C:\PolicyDefinitionFolder\azurepolicy.json" -OutputFile "C:\Temp\MyTestResult.xml"
```

Test a single Azure policy definition and store the test result in a file

### EXAMPLE 3

```powershell
C:\PS> Test-AzPolicyDefinition -Path "C:\PolicyDefinitionFolder\azurepolicy.json" -OutputFile "C:\Temp\MyTestResult.xml" -OutputFormat 'LegacyNUnitXML'
```

Test a single Azure policy definition and store the test result in a file with the 'LegacyNUnitXML' format

### EXAMPLE 4

```powershell
C:\PS> Test-AzPolicyDefinition -Path "C:\PolicyDefinitionFolder\" -OutputFile "C:\Temp\MyTestResult.xml" -ExcludeTags 'ParametersMaxCount', 'ParametersMinCount'
```

Test all Azure Policy definitions in a folder, exclude tests with the `ParametersMaxCount` and `ParametersMinCount` tags and store the test result in a file.

### EXAMPLE 5

```powershell
C:\PS> Test-AzPolicyDefinition -Path "C:\PolicyDefinitionFolder\" -OutputFile "C:\Temp\MyTestResult.xml" -OutputFormat 'NUnitXML' -ExcludePath 'excludeFolder', 'main.json' -PesterVerbosity 'None'
```

Test all Azure Policy definitions in a folder, exclude all files in 'excludeFolder' folder and all files with the name 'main.json' then store the test result in a file with the 'NUnitXML' format. Suppress Pester output in stdout by setting `-PesterVerbosity` to 'None'.

### EXAMPLE 6

```powershell
C:\PS> $json = Get-Content -Path "C:\PolicyDefinitionFolder\azurepolicy.json" -Raw
C:\PS> Test-AzPolicyDefinition -Content $json
```

Test a single Azure Policy definition from in-memory content and display Pester result on the PowerShell host.

### EXAMPLE 7

```powershell
C:\PS> $json = Get-Content -Path "C:\PolicyDefinitionFolder\azurepolicy.json" -Raw
C:\PS> Test-AzPolicyDefinition -Content $json -OutputFile "C:\Temp\MyTestResult.xml" -OutputFormat 'NUnitXML'
```

Test a single Azure Policy definition from in-memory content and store the test result in a file with the 'NUnitXML' format.

## PARAMETERS

### -Path

Specify the file paths for the policy definition files.

```yaml
Type: String
Parameter Sets: PathNoOutputFile, PathProduceOutputFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ExcludePath

Specify the excluded file paths for the policy definition files.

```yaml
Type: String[]
Parameter Sets: PathNoOutputFile, PathProduceOutputFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Content

Specify the JSON content of a single file to test.

```yaml
Type: String
Parameter Sets: ContentNoOutputFile, ContentProduceOutputFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -OutputFile

Specify the file path to save the Pester test result.

```yaml
Type: String
Parameter Sets: PathProduceOutputFile, ContentProduceOutputFile
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputFormat

Specify the output format of the Pester test result file.

```yaml
Type: String
Parameter Sets: PathProduceOutputFile, ContentProduceOutputFile
Aliases:
Accepted values: NUnitXml, LegacyNUnitXML

Required: False
Position: Named
Default value: NUnitXml
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExcludeTags

Specify the tags for excluded tests.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PesterVerbosity

Specify Pester output verbosity. Use 'None' to suppress Pester output in stdout.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: None, Normal, Detailed, Diagnostic

Required: False
Position: Named
Default value: Detailed
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProgressAction

{{ Fill ProgressAction Description }}

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: proga

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Online Version](https://github.com/tyconsulting/AzPolicyTest/blob/master/help/Test-AzPolicyDefinition.md)
