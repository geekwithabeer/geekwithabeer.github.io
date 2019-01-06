---
layout: post
title: Default issuance transformation claim rules for ADFS 3.0 + Office 365
date: 2017-04-15 18:26
categories: 
tags: [adfs, office 365, Uncategorized]
---

In case you fucked up the default claims like I did, here are the two default unnamed rules:

`
c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/windowsaccountname"]
 =&gt; issue(store = "Active Directory", types = ("http://schemas.xmlsoap.org/claims/UPN", "http://schemas.microsoft.com/LiveID/Federation/2008/05/ImmutableID"), query = "samAccountName={0};userPrincipalName,objectGUID;{1}", param = regexreplace(c.Value, "(?&lt;domain&gt;[^\\]+)\\(?&lt;user&gt;.+)", "${user}"), param = c.Value);
`

`
c:[Type == "http://schemas.microsoft.com/LiveID/Federation/2008/05/ImmutableID"]
 =&gt; issue(Type = "http://schemas.xmlsoap.org/ws/2005/05/identity/claims/nameidentifier", Value = c.Value, Properties["http://schemas.xmlsoap.org/ws/2005/05/identity/claimproperties/format"] = "urn:oasis:names:tc:SAML:1.1:nameid-format:unspecified");
`

The rules have some HTML entities. If you don't see a domain tag and a user tag in the first rule, something got eaten by WordPress. Here are the base64-encoded values for the two rules:

`
YzpbVHlwZSA9PSAiaHR0cDovL3NjaGVtYXMubWljcm9zb2Z0LmNvbS93cy8yMDA4LzA2L2lkZW50aXR5L2NsYWltcy93aW5kb3dzYWNjb3VudG5hbWUiXQogPT4gaXNz
dWUoc3RvcmUgPSAiQWN0aXZlIERpcmVjdG9yeSIsIHR5cGVzID0gKCJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy9jbGFpbXMvVVBOIiwgImh0dHA6Ly9zY2hlbWFz
Lm1pY3Jvc29mdC5jb20vTGl2ZUlEL0ZlZGVyYXRpb24vMjAwOC8wNS9JbW11dGFibGVJRCIpLCBxdWVyeSA9ICJzYW1BY2NvdW50TmFtZT17MH07dXNlclByaW5jaXBh
bE5hbWUsb2JqZWN0R1VJRDt7MX0iLCBwYXJhbSA9IHJlZ2V4cmVwbGFjZShjLlZhbHVlLCAiKD88ZG9tYWluPlteXFxdKylcXCg/PHVzZXI+LispIiwgIiR7dXNlcn0i
KSwgcGFyYW0gPSBjLlZhbHVlKTs=
`

`
YzpbVHlwZSA9PSAiaHR0cDovL3NjaGVtYXMubWljcm9zb2Z0LmNvbS9MaXZlSUQvRmVkZXJhdGlvbi8yMDA4LzA1L0ltbXV0YWJsZUlEIl0KID0+IGlzc3VlKFR5cGUg
PSAiaHR0cDovL3NjaGVtYXMueG1sc29hcC5vcmcvd3MvMjAwNS8wNS9pZGVudGl0eS9jbGFpbXMvbmFtZWlkZW50aWZpZXIiLCBWYWx1ZSA9IGMuVmFsdWUsIFByb3Bl
cnRpZXNbImh0dHA6Ly9zY2hlbWFzLnhtbHNvYXAub3JnL3dzLzIwMDUvMDUvaWRlbnRpdHkvY2xhaW1wcm9wZXJ0aWVzL2Zvcm1hdCJdID0gInVybjpvYXNpczpuYW1l
czp0YzpTQU1MOjEuMTpuYW1laWQtZm9ybWF0OnVuc3BlY2lmaWVkIik7
`
