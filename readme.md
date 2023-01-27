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
  * Segmenting applications in the architecture, increases the components' security,
  * Use security headers to send directives to clients,
  * Verify the effectiveness of the configuration with automated processes.
* Possible scenarios
  * A server has a not removed application in the production environment. If a security failure exist and is known on this application, attackers can use it to trade-off the server. Depending of the application level, the impact can be more or less important.
  * A server returns detailed error messages to the users. It can expose sensitive data/information to everyone.

## [A06:2021-Vulnerable and Outdated Components](https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/)
* A vulnerable and outdated component is a common issue, that we have some difficulties to **test and evaluate** the risk.
* We can consider that you are vulnerable if:
  * You don't consider the versions of all your components (and dependencies) that you use,
  * Your OS or softwares are vulnerable, unsupported, or out of date,
  * You don't scan regularly for searching vulnerabilities or you do not susbcribe to a security bulletin about component security issues,
  * You don't upgrade or fix components or dependencies depending on the risks,
  * You use a software that developers do not test the compatibility of updated, upgraded, or patched libraries,
  * You don't secure your components.
* Avoid vulnarable component with a patch management process:
  * Delete and remove unnecessary features, softwares, components, dependencies,
  * Create a version inventory of your components and dependencies, and update it continuously,
  * Monitor continuously the Common Vulnerability and Exposures (CVE) and National Vulnerability Database (NVD),
  * Use only official sources to obtain components or dependencies.
* Possible scenario
  * A component is always run with the same authorizations as the main application, can cause serious impacts if the component has one or multiple flows.

## [A03:2021-Injection](https://owasp.org/Top10/A03_2021-Injection/)
* 94% of the applications that have been tested for injections issues. The max incidence rate is off 19%, and the average is off 3%.
* We can consider that an application is vulnerable if:
  * Data that are given by the user are not **validated**, **filtered**, or **sanitized**,
  * Non-parameterized calls without context-aware and dynamic calls are directly used in the interpreter,
  * Data given by the users are directly used as parameters to extract additional records,
  * External data are directly used or concatened, so the SQL request can contain malicious queries/commands/procedures.
* Most common injection are SQL, NoSQL, OS, Object Relational Mapping, Expression Level, or Object Graph Navigation Library.
* Reviewing source code is the best way to detect possible injections.
* It is recommended to automate testing of headers, URL, cookies, JSON, SOAP, XML.
* Avoid injections by keeping data separate from commands and queries
  * Use API, which avoids the entirely utilisation of the interpreter, and provides a parameterized interface, or migrates Object Relational mapping.
  * Use input validation for the server side.
  * For the remaining dynamic requests, avoid as much as possible special characters and use the escape syntax.
  * Use controls that prevent mass disclosure of records.
* Possible scenarios
  * If you have an application that uses unsafe data in the construction of a SQL query.
  * It is the same for an HQL query as a SQL query.

----
<a name="ddsummary"></a>
# Darknet Diaries - Summary
I was scrolling on the Darknet Diaries' website, searching for an interesting subject when my attention was caught by the episode: [EP124: SYNTHETIC REMITTANCE](https://darknetdiaries.com/episode/124/). Indeed, this episod is about social engineering, email, crime and finance. So, I decided to analyze and summarize this episode.

It is the story of Evaldas Rimašauskas, a Lithuanian interested in getting rich, but fast. His story starts in 2012, when Facebook bought Instagram for one billion of dollars.
In fact, most of the time, it is long and you need a lot of courage to set up a business that makes it profitable. You need to allocate a lot of resources to it to make it attractive and therefore profitable.
We can take the example of Facebook that needed five years before getting a first profit. It is very long!! However, in 2012 Facebook had a revenue of five billion dollars. By this fact, Facebook bought Instagram for one billion dollars.

In 2012, Evaldas was forty-three years old, and Facebook's purchase of Instagram did not escape his ears. When he heard it, he had several questions in his head, such as: "Who’s the person on Facebook that has the ability to write a one-billion-dollar check?". He was fully fascinated by the financial system of a company. So, he learned a lot about how does check works. He got interested about scamming companies with a fake check. Evaldas was not interested in earning undereds of dollars, he wanted thousands of dollars, and quickly. He quickly understood that for scamming a company he needed to have a lot of information about a company.
He knew that I could not directly ask to Facebook who sign the checks, he needed to go step by step and with the help of his friends.

First of all, we his friends, they started to ask to Facebook some basic questions, like the accounting department number, or what they should do if Facebook needs to pay them, etc. For them, it would be a huge help to have the email address of someone that works in Facebook's accounting department. By having the email, you can write an email and have a phone number in the signature of the reply, then you can call the person to try to social-engineer him.
At the same time, they also had the idea to attack Facebook by using business relations (partners, contractors, etc.). They learned that Facebook was working with Quanta Computer, based in Taiwan. This company repairs and refurbishes tablets and point-of-sale devices as well as bill servers, and provides Cloud computing services. 
So, he social-engineer the both companies to get as much as information possible to know how does Facebook and Quanta Computer are working. It is the set of all the data that he got that gives a better understanding to Evaldas.

Then, he got the "BIG IDEA" to prentend to be Quanta and to send an invoice to Facebook. So then, Facebook will pay him and not Quanta. However, to do that, he need to make everything perfect, by using the previous information.

To achieve his goal he did the following steps:
1. He created a company named Quanta Computer in Latvia and Cypress and he openend bank accounts for them.
2. Then he got a real invoice from the real Quanta Computer company. With this invoice, he knew exactly who was paying them on Facebook.
3. He needed a real email address that look like the one of Quanta Computer. For this point, we don't really know what he did, but we pretend that he registred a domain name very similar as the one of Quanta Computer.

Then, he was finally ready, he had his fake invoice, his fake domain, and fake business all set up.
He wrote the email and sent it to the correct person of Facebook. The email was saying to Facebook to update where payment should be sent. So that, payments would be sent to the fake Quata Computer and not to the real company.
He didn't had to wait for a long time before having first results. He recived a notification from his bank, saying that he recived money from Facebook. So, his plan has worked!! And the plan worked more than one time, he recived several times huge amount of money from Facebook.


----
<a name="cve"></a>
# CVE - Explanation

----
<a name="sqlzoo"></a>
# SQLZoo - Solve

----
<a name="webgoat"></a>
# WebGoat - Solve
