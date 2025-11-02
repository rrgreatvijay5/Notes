## Get all domain computers
```Get-DomainComputer | select samaccountname```
```Get-DomainComputer | select dnshostname```

## Get all domain users
Get-DomainUser | select samaccountname

Get domain details
Get-Domain

Get domain SID
Get-DomainSID

Get list of domain admins and enterprise admins
Get-DomainGroup -Identity "Domain Admins"
Get-DomainGroupMember -Identity "Domain Admins"
Get-DomainGroup -Identity "Enterprise Admins" -Domain moneycorp.local
Get-DomainGroupMember -Identity "Enterprise Admins" -Domain moneycorp.local

Blooudhound collection
Invoke-BloodHound -CollectionMethod All

Find all computers with local admin access
Find-LocalAdminAccess
