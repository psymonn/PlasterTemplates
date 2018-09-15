# Plaster Templates by David Christian

A central repository for my Plater Templates

https://overpoweredshell.com/Working-with-Plaster/

https://www.the-little-things.net/blog/2017/05/15/powershell-creating-plaster-manifest-files/

Generate MD file from Module and using MD file to generate help file:

https://github.com/PowerShell/platyPS


Simple Plaster project generate:
--

$plasterDest = 'F:\GitHub\Source\ProjectSamples\Plaster New Project\Temp4'
$defaultTemplate = Get-PlasterTemplate | 
    Where-Object -FilterScript {$PSItem.Title -eq 'New PowerShell Manifest Module'}

Invoke-Plaster -TemplatePath $defaultTemplate.TemplatePath -DestinationPath $plasterDest\MyFirstPlasterModule  -Verbose 

Genearate Plaster Custom Template:
---

Invoke-Plaster -TemplatePath 'F:\GitHub\Source\ProjectSamples\Plaster New Project\PlasterTemplates\Module' -DestinationPath .\temp3
Invoke-Plaster -TemplatePath 'F:\GitHub\Source\ProjectSamples\Plaster New Project\PlasterTemplates\Function' -DestinationPath .\temp3
Invoke-Plaster -TemplatePath 'F:\GitHub\Source\ProjectSamples\Plaster New Project\PlasterTemplates\BlogPost' -DestinationPath .\temp3

Genearate MD and Help files:
--

New-MarkdownHelp -Module platyPS -OutputFolder .\docs
New-MarkdownHelp -Module PSGraph -OutputFolder .\docs
New-MarkdownHelp -Module Mytools -OutputFolder .\docs
New-MarkdownHelp -Module DiskSpaceInfo -OutputFolder .\docs

New-ExternalHelp .\docs -OutputPath en-US\
