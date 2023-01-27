# Information Security - H2 Goat - Matthieu Brühwiler

## Table of Contens
1. [ OWASP 10 2021 - summaries. ](#owaspsummaries)
2. [ Darknet Diaries - summary. ](#ddsummary)
3. [ CVE - explanation. ](#cve)
4. [ SQLZoo - Solve. ](#sqlzoo)
5. [ WebGoat - Solve. ](#webgoat)


<a name="owaspsummaries"></a>
# OWASP 10 2021 - Summaries

## [A05:2021-Security Misconfiguration](https://owasp.org/Top10/A05_2021-Security_Misconfiguration/)
* 90% of the tested applications for some form misconfiguration, with an average incidence of 4%.
* We can consider that an application is vulnerable if it is:
  * Not enough security for application stack or cloud permissions are incorrect,
  * Functions installed or activated that are not needed,
  * The default accounts have not been secured (no password change or account deactivation),
  * Error messages are revealing too much information for the users,
  * Latest system upgrades are deactivated or not configured properly,
  * Server applications (Spring, Django, Struts, etc.) are not configured correctly,
  * Server does not send security headers, or they are not set as secure values,
  * Software is **out of date** or **vulnerable**.
* Avoid a misconfiguration by implementing security process:
  * Development, QA, and production should use the same configuration but with some different credentials,
  * Install only useful features or frameworks. Uninstall unnecessary features,
  * Create a process that analyzes and upgrade configurations based on upgrade, security notes, and patches. Review your cloud permissions,
  * Segmenting applications in the architecture, increases the componants' security,
  * Use security headers to send directives to clients,
  * Verify the effectiveness of the configuration with automated processes.
* Possible scenarios
  * A server has a not removed application in the production environment. If a security failure exist and is known on this application, attackers can use it to trade-off the server. Depending of the application level, the impact can be more or less important.
  * A server returns detailed error messages to the users. It can expose sensitive data/information to everyone.

## [A06:2021-Vulnerable and Outdated Components](https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/)


## [A03:2021-Injection](https://owasp.org/Top10/A03_2021-Injection/)


----
<a name="ddsummary"></a>
# Darknet Diaries - Summary

----
<a name="cve"></a>
# CVE - Explanation

----
<a name="sqlzoo"></a>
# SQLZoo - Solve

----
<a name="webgoat"></a>
# WebGoat - Solve
