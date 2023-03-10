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

Then, he got the "BIG IDEA" to pretend to be Quanta and to send an invoice to Facebook. So, then, Facebook will pay him and not Quanta. However, to do that, he needs to make everything perfect, by using the previous information.

To achieve his goal he did the following steps:
1. He created a company named Quanta Computer in Latvia and Cypress and he opened bank accounts for them.
2. Then he got a real invoice from the real Quanta Computer company. With this invoice, he knew exactly who was paying them on Facebook.
3. He needed a real email address that look like the one of Quanta Computer. At this point, we don't really know what he did, but we pretend that he registered a domain name very similar as the one of Quanta Computer.

Then, he was finally ready, he had his fake invoice, his fake domain, and fake business all set up.
He wrote the email and sent it to the correct person on Facebook. The email was saying to Facebook to update where payment should be sent. So that, payments would be sent to the fake Quata Computer and not to the real company.
He didn't have to wait for a long time before having first results. He received a notification from his bank, saying that he received money from Facebook. So, his plan has worked!! And the plan worked more than one time, he received several times huge amounts of money from Facebook.

A bit later, Evaldas learned that Quanta was also working with Google. He decided to do the same to Google as he did to Facebook, and Google also fell in the trap. 
He also decided to open different bank accounts in different countries (Slovakia, Lithuania, Hungary, and Hong Kong) to split the money. In addition, if a bank asked him from where does the money come, he could proof the transaction with some fake legal documents.

During two years, Evaldas received money ($23 million from Google and $98 million from Facebook) from the both companies and his system of laundering money was working properly. However, at some point, the both companies understood the scam, maybe because Quanta called them for the unpaid invoices. The FBI has need notified, and because of the huge amount of money that was involved, they directly acted. Evaldas has been finally arrested by the Lithuanian authorities and he was extradited to New York to be judged. His sentence was five years in prison with a fine of $26 million.

In this history, the biggest mistake from Evaldas was to register the fake domain with his personal email address. It has considerably helped the authorities to find him. Nowadays, this kind of attacks is still possible although, mailboxes have some system to prevent for the junk mail and quarantine. However, it reminds us of the dangerousness of not having security for your IT system. The security is not only about system protection but also about human formation.

----
<a name="cve"></a>
# CVE - Explanation
## [Log4j - CVE-2021-44228](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-44228)
When an application is developed, we usually add some logs. The logs are used to track what is made in the application. Logs are really useful to find who did what and when, so, we can easily find when an error as occurred and why. Apache Software Fundation provide a dependency for Java, to help developers for logging.

On 9 December 2021, an important flaw has been discovered for Log4j 2.0-beta9 through 2.15.0 (excluding security releases 2.12.2, 2.12.3, and 2.3.1).
LDAP is a standard way to provide access to directory information. In java, to access directory services such as LDAP, we use the interface JNDI.
Indeed, JNDI is an interface that gives to Java an access to directory services such as LDAP. 
It is a very technical attack, but to make it simple, an attacker can send a web page to a server and have it read the entire page, if this web page contains some Java code. So, you can execute some code remotely on a vulnerable server without being authenticated.

This attack is classified as **critical** with a CVSS score of **9.3**, because you allow a full access to your server to an attacker who can control a log message. The confidentiality, integrity, availability impact are considerate as complete.
Another huge problem with this attack is the number of companies that are involved, like Amazon AWS, Cloudflare, iCloud, Minecraft Java Edition (Yes, of course!), Steam, Flink, ElasticSearch, Azure, etc. 

### Sources
* [CVE - CVE-2021-44228](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-44228)
* [CVE details - CVE-2021-44228](https://www.cvedetails.com/cve/CVE-2021-44228/?q=CVE-2021-44228)
* [Info World - LDAP and JNDI: Together forever](https://www.infoworld.com/article/2076073/ldap-and-jndi--together-forever.html)
* [UpGuard](https://www.upguard.com/blog/apache-log4j-vulnerability)
* [DataCenter Magazine (French)](https://datacenter-magazine.fr/tour-savoir-sur-la-faille-apache-log4j-une-vulnerabilite-aux-proportions-catastrophiques-ou-le-pire-reste-a-venir/)
* [SiecleDigital - La faille Log4j considérée comme une « vulnérabilité endémique » (French)](https://siecledigital.fr/2022/07/18/la-faille-log4j-consideree-comme-une-vulnerabilite-endemique/)


----
<a name="sqlzoo"></a>
# SQLZoo - Solve
## [0 - SELECT BASICS](https://sqlzoo.net/wiki/SELECT_basics)

### 1. Modify it to show the population of Germany

    SELECT population FROM world WHERE name = 'Germany';
    # I changed the world France to Germany to select the country that has the name Germany.

### 2. Show the name and the population for 'Sweden', 'Norway' and 'Denmark'.

    SELECT name, population FROM world WHERE name IN ('Sweden', 'Norway', 'Denmark');
    # I changed the countries that were in the parenthesis with: Sweden, Norway, and Denmark.

### 3. Just the right size

    SELECT name, area FROM world WHERE area BETWEEN 200000 AND 250000;
    # I changed the numbers that follow the "between" and the "and", the first one is the smallest area and the second one is the biggest area.

## [2 - SELECT FROM WORLD](https://sqlzoo.net/wiki/SELECT_from_WORLD_Tutorial)

### 1. Introduction

    # We can see all the countries with their continent and their population.

### 2. Large Countries

    SELECT name FROM world WHERE population >= 200000000;
    # I changed to number for the population, and I also changed the operator because it is at least 200000000.

### 3. Per capita GDP

    SELECT name, (gdp/population) FROM world WHERE population >= 200000000;
    # I added "(gdp/population)" to have the result of the calculation for each country. I also changed the population number to have 200 million.

### 4. South America In millions

    SELECT name, (population/1000000) FROM world WHERE continent = 'South America';
    # I wrote name and (population/1000000) to have the name and the population in million for each country of the continent South America (condition where).

### 5. France, Germany, Italy

    SELECT name, population FROM world WHERE name in ('France', 'Germany', 'Italy');
    # I wrote name and the population to have the name and the population attributes. Then, I added the where condition with name IN France, Germany, and Italy. So, it will return each country that has one of this name.

----
<a name="webgoat"></a>
# WebGoat - Solve
*I did not need to install the WebGoat Spring server on my Debian, because it was already installed, due to the exercises of the last week [H1_FirstSteps](https://github.com/MatthieuBruh/h1_FirstSteps)*

*I only started the server with the command*:

    java -jar webgoat-server-8.0.0.M26.jar

*When the server has started, I used Google Chrome to go on: localhost:8080/WebGoat .*

## 2. What is SQL?

    SELECT department FROM employees WHERE first_name = 'Bob' AND last_name = 'Franco';
    # As selected attribute, I choose only department, because we only need the department.
    # To select only the employee Bob Franco, I added the where condition on the first name and the last name.

## 3. Data Manipulation Language (DML)

    UPDATE employees SET department = 'Sales' WHERE first_name = 'Tobi' AND last_name = 'Barnett';
    # I choose the SQL statement UPDATE to modify the table employees.
    # I added the argument SET department to determine which attribute will be updated.
    # To modify the department of the right employee, I added the where condition on first name and last name.

## 4. Data Definition Langugage (DDL)

    ALTER TABLE employees ADD phone varchar(20);
    # I choose the SQL statement ALTER TABLE to modify the scheme of the table employees.
    # Then I said that I want to ADD a column named phone and the type is a varchar of a maximal length of 20.

## 5. Data Control Language (DCL)

    GRANT ALTER TABLE TO UnauthorizedUser;
    # I choose the SQL statement GRANT ALTER TABLE TO, that allow me to change the authorization of the table.

## 9. Try it! String SQL injection

    SELECT * FROM user_data WHERE first_name = 'John' and last_name = '' or '1' = '1'
    # The second term of the where condition of the SQL query, allow me to always have the condition as true.
    # Indeed, one is always equal to one.

## 10. Try it! Numeric SQL injection

    SELECT * FROM user_data WHERE login_count = " + Login_Count + " AND userid = "  + User_ID;
    login_Count: 1
    User_id: 1 or TRUE;
    # The login_count field does not matter. We can choose a random number.
    # However, the user_id need to be always correct, so we create the condition that will always be true by adding "or and TRUE".

## 11. Compromising confidentiality with String SQL injection

    SELECT * FROM employees WHERE last_name = '" + name + "' AND auth_tan = '" + auth_tan + "';
    Employee Name:' OR '1'='1
    Authentication TAN:' OR '1'='1
    # By using ' as the first element of the each entry, you say that the field must be empty OR '1'='1'.
    # The result would be: SELECT * FROM employees WHERE last_name = '' OR '1'='1' AND auth_tan = '' OR '1'='1';

## 12. Compromising Integrity with Query chaining

    Employee Name: matthieu'; UPDATE employees SET salary = '85000' WHERE userid = '37648'--
    Authentication TAN:
    # I left the authentication TAN empty because we only need to write in one field.
    # The value matthieu can be what you want. However, it should finish the query by using ';
    # Then you can create your personalized query by adding the double - at the end of your query.

## 13. Compromising Availability

    Action contains: ';DROP TABLE access_log;--
    # I added a new query at the end of the first one to drop (delete) the table access_log



