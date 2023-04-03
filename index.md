---
layout: page
title: iam:root
---

![logo](/assets/logo.png){:.logo}

iam:root is a list of AWS permissions that can be used to escalate access within misconfigured AWS environments.

The project lists permissions that users or roles may be granted within AWS that singularly, or in combination with other permissions, can be used to gain access to roles and privileges previously restricted from the user.

It is important to note that this is **not** a list of exploits, the permissions listed here have legitimate purposes and uses, and only some of the permissions listed here will immediately allow a user to escalate to root level access. Rather, iam:root is a collection of permissions, that if not properly controlled, may allow users to escalate their permissions to include more than they currently possess based on other configurations within the environment.

The permissions listed within this site include details on other **required** permissions for successful escalation, in addition to **required** configurations within the environment. Additionally listed are permissions that are **useful** and may make the escalation process significantly easier, but will not stop escalation if they are not present.

The permissions within this reference are written with the assumption that the permission has been granted against all resources, within your environment this may not be the case. If suitable resources cannot be targeted with the provided commands it is possible that only limited escalation, or no escalation at all, will occur.

In some cases, depending on the configuration of the environment, some permissions on this list may allow you to create the required conditons for other permissions on this list to become vulnerable. This process will be highly specific to the environment and is beyond the scope of this reference site.

iam:root is a [collaborative][] project created by Lucas Fedyniak-Hopes where everyone can contribute with additional permissions and techniques.

This site is based upon the excellent linux privilege escalation resource [GTFOBins][].

[GTFOBins]: https://github.com/GTFOBins/GTFOBins.github.io/
[collaborative]: #
[contribute]: /contribute/

{% include permission_table.html %}
