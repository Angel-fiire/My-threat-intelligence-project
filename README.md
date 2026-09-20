# OSINT-Based Threat Intelligence Assessment

This project is an **OSINT-based Cyber Threat Intelligence (CTI) assessment** of Agoda, a global online travel and hospitality organisation. The investigation examines Agoda's publicly visible digital footprint, potential phishing and brand impersonation activity, exposed infrastructure, and indicators of third-party data exposure using **passive OSINT techniques**. 

## Table of Contents

* Project Overview
* Network Topology
* Tools and Technologies
* Configuration Steps
* Results and Findings
* Author

## Project Overview

The purpose of this project was to conduct a **defensive Cyber Threat Intelligence assessment** of Agoda using publicly available **Open-Source Intelligence (OSINT)**. The investigation focused on identifying information that could potentially be useful to threat actors during reconnaissance, phishing, social engineering, impersonation, or other forms of targeting.

The assessment was conducted using **passive OSINT methods only**. No exploitation, unauthorised access, password attacks, vulnerability exploitation, or attempts to bypass authentication systems were performed. The investigation was designed to understand Agoda's publicly visible exposure while maintaining responsible and ethical research practices. 

The main intelligence requirements were to determine:

* What **domains, subdomains and online services** are publicly associated with Agoda.
* Whether there is evidence of **phishing or brand impersonation** involving Agoda.
* Whether Agoda's brand has been used in **scams or fraudulent activity**.
* What information about Agoda's **internet-facing infrastructure** can be identified through OSINT.
* Whether there are indicators of **publicly exposed or leaked information**.
* How a potential threat actor could use publicly available information during reconnaissance or social engineering.
* What **defensive measures and recommendations** could reduce the identified risks. 

Agoda operates within the **online travel services and hospitality sector**, providing accommodation, flight and activity-related services through its website and mobile applications. The organisation has a global presence, with its headquarters in Singapore and operations across multiple markets. Its large customer base, public-facing services and extensive digital footprint make monitoring publicly available information an important part of defensive security. 

The investigation identified **phishing and brand impersonation** as the most significant threat observed during the assessment. Evidence was found of a scam in which criminals impersonated Agoda recruitment staff through WhatsApp and convinced a victim to make **14 transactions totalling HK$2.6 million**. The attackers reportedly used fake participants, payment screenshots and false testimonials to make the scam appear legitimate. 

The investigation also identified publicly visible Agoda-related infrastructure. A Shodan result associated **`45.113.60.20`** with Agoda Company Pte. Ltd. and `www.agoda.com`, with **port `443`** providing HTTPS services. Agoda-related infrastructure hosted through **Amazon Web Services (AWS)** was also observed. Importantly, the investigation did not establish that this infrastructure was vulnerable or compromised. 

A further investigation using Have I Been Pwned identified an **`@agoda.com` email address** appearing in 10 historical breach datasets between 2016 and 2024. The report explicitly notes that this does **not** demonstrate that Agoda itself experienced ten breaches, as the email address may have been exposed through third-party organisations. However, the exposure could potentially provide useful information for targeted phishing or social engineering. 

Overall, the assessment identified a **Medium overall security risk** based on the evidence collected. The most significant concern was brand impersonation and social engineering, while infrastructure exposure and email exposure represented additional potential risks. No direct compromise or confirmed vulnerability in Agoda's systems was established during the investigation. 

## Network Topology

This project did not involve the construction of a traditional network topology because the assessment was focused on **Cyber Threat Intelligence and OSINT rather than network infrastructure configuration**.

Instead, the investigation examined Agoda's **public digital footprint and external attack surface**. This included publicly visible domains, subdomains, online services, email-security records, internet-facing infrastructure, cloud-hosted infrastructure, social-media presence and publicly reported breach information.

The primary publicly identified domain was:

* **`agoda.com`** - Agoda's primary customer-facing website.

Additional publicly indexed Agoda-related domains and subdomains identified during the investigation included:

* **`flights.agoda.com`** - Agoda's flight-booking service.
* **`partnerhub.agoda.com`** - Agoda Partner Hub for property partners.
* **`partners.agoda.com`** - Agoda partner services.
* **`portal.agoda.com`** - publicly referenced partner portal.
* **`notices.agoda.com`** - public content-reporting portal.
* **`careersatagoda.com`** - publicly visible recruitment/careers domain. 

The assessment also identified Agoda's customer-facing applications and online presence:

* **Agoda.com** online booking platform.
* **Agoda mobile application**.
* Hotel and holiday accommodation services.
* Flight-booking services.
* Customer-support services.
* Partner and affiliate services.
* Public partner-management resources.
* Public social-media profiles, including LinkedIn and Instagram. 

### Public Infrastructure Identified

Shodan was used to identify publicly visible internet-connected infrastructure. One identified result was:

* **IP address:** `45.113.60.20`
* **Organisation:** Agoda Company Pte. Ltd.
* **Associated hostname:** `www.agoda.com`
* **Public service:** HTTPS
* **Port:** `443`
* **Certificate:** associated with `agoda.com`

The presence of port `443` indicates an HTTPS service, which is expected for a public-facing website. The investigation did not identify a confirmed vulnerability associated with this service. 

Agoda-related infrastructure hosted on **Amazon Web Services (AWS)** was also identified. Some of the observed IP addresses redirected to the official Agoda website. This information demonstrates that Agoda has publicly observable cloud infrastructure, although the investigation did not establish that the infrastructure was vulnerable or being actively abused. 

### Email Security Infrastructure

Passive email-security analysis was conducted using **MXToolbox**. An SPF record was identified and the available syntax checks passed. A DMARC record was also identified and reported as syntactically valid, with the results indicating a quarantine/reject policy.

DKIM could not be independently verified because a valid selector could not be identified during the passive OSINT investigation. The report therefore does **not** conclude that DKIM is absent; its status remained unverified. 

## Tools and Technologies

* **Google Search** - used to locate publicly available Agoda websites, domains, pages, documents and other indexed information.
* **Google Dorks** - used to assist with identifying publicly indexed information and potentially exposed documents.
* **MXToolbox** - used to investigate publicly available DNS and email-security information, including SPF and DMARC.
* **VirusTotal** - used for domain, URL and security-reputation investigation where relevant.
* **Shodan** - used to identify publicly visible internet-connected services, IP addresses, ports and infrastructure.
* **AbuseIPDB** - used to investigate the reputation of identified IP addresses.
* **Have I Been Pwned** - used to investigate whether Agoda-associated email information appeared in historical breach datasets.
* **MITRE ATT&CK** - used to relate relevant observations to known threat-actor techniques.
* **Wayback Machine** - used for historical analysis, including previous URLs, trends and historical information.
* **Public websites and search engines** - used as sources for passive intelligence collection.
* **LinkedIn and Instagram** - used to understand Agoda's publicly visible social-media presence.
* **Google Play and Apple App Store** - used to confirm publicly available Agoda mobile applications. 

## Configuration Steps

1. **Defined the intelligence requirements and scope** before beginning the investigation. The main areas of interest were Agoda's digital footprint, phishing and impersonation, infrastructure exposure and possible data leakage.

2. **Established an ethical and passive OSINT methodology**. The investigation was restricted to information already publicly available on the internet and excluded active vulnerability scanning, port scanning, exploitation, password guessing and unauthorised access. 

3. **Conducted initial reconnaissance using Google Search** to identify Agoda's primary domain, publicly indexed pages, services, domains and subdomains.

4. **Investigated Agoda's public domain structure**, identifying services such as `agoda.com`, `flights.agoda.com`, `partnerhub.agoda.com`, `partners.agoda.com`, `portal.agoda.com`, `notices.agoda.com` and `careersatagoda.com`.

5. **Investigated Agoda's public-facing services**, including its main booking platform, flight services, mobile applications, partner services and public reporting portals.

6. **Reviewed Agoda's public social-media presence**, identifying professional and customer-facing channels including LinkedIn and Instagram.

7. **Used MXToolbox** to examine Agoda's publicly available email-security configuration. SPF and DMARC records were identified, while DKIM could not be independently verified during the investigation.

8. **Used Shodan** to identify publicly visible Agoda-related infrastructure. The investigation identified `45.113.60.20`, which was associated with `www.agoda.com` and Agoda Company Pte. Ltd.

9. **Examined publicly accessible services** associated with the identified infrastructure. Port `443` was identified as providing HTTPS services and an SSL certificate associated with `agoda.com` was observed.

10. **Investigated cloud infrastructure**, identifying Agoda-related IP addresses hosted through **Amazon Web Services (AWS)** that redirected to the official Agoda website.

11. **Checked IP reputation using AbuseIPDB**. The report states that the identified IP address had no reports and a **0% confidence of abuse** at the time of the investigation. 

12. **Investigated phishing and brand impersonation** by searching for reports involving Agoda's name, recruitment processes and online communications.

13. **Analysed the reported WhatsApp recruitment scam** in which criminals impersonated Agoda recruitment staff and used social-engineering techniques, including fake participants, payment screenshots and false testimonials.

14. **Investigated potential look-alike domains and fake login pages**. No confirmed look-alike domains or cloned Agoda login pages were identified within the scope of the investigation. 

15. **Used Have I Been Pwned** to investigate potential breach exposure involving Agoda-associated email addresses.

16. **Recorded the historical email exposure**, identifying an `@agoda.com` email address appearing in 10 historical breach datasets between 2016 and 2024.

17. **Analysed the potential information exposed through the historical breach datasets**, including email addresses, names, phone numbers, physical addresses, purchases, travel plans and partial credit-card information.

18. **Separated confirmed findings from potential risks**. The investigation did not treat the third-party breach exposure as evidence that Agoda itself had suffered the reported breaches.

19. **Assessed potential attack paths** from a threat-actor perspective, considering how publicly available information could support phishing, social engineering, impersonation and reconnaissance.

20. **Assessed business impacts**, including financial loss, reputational damage, customer-trust issues, operational costs and potential regulatory implications if a genuine personal-data compromise were to occur.

21. **Documented the evidence** in an evidence log, including the source, observation, significance and investigation date.

22. **Developed mitigation recommendations** based on the identified findings, including brand monitoring, phishing takedown processes, email authentication, awareness training, continuous OSINT monitoring and breach-exposure monitoring.

23. **Reviewed the investigation for ethical compliance**, ensuring that the assessment remained within the boundaries of passive OSINT and did not involve exploitation, unauthorised access or credential collection. 

## Results and Findings

### 1. Phishing and Brand Impersonation

The most significant finding was evidence of **Agoda brand impersonation being used in a social-engineering scam**.

The investigation identified reporting from **The Standard** describing a case where criminals impersonated Agoda recruitment staff through WhatsApp. The attackers reportedly convinced a victim to make **14 transactions totalling HK$2.6 million**.

The scammers attempted to create credibility through:

* Fake recruitment staff.
* Fake participants.
* Payment screenshots.
* False testimonials.
* Claims relating to earning money through tasks.
* Use of the **Agoda brand and reputation**.

This finding demonstrates that an attacker does not necessarily need to compromise Agoda's technical infrastructure to cause harm associated with the organisation. Instead, criminals can exploit the trust associated with a well-known brand to make fraudulent communications appear legitimate. 

### 2. Infrastructure Exposure

The investigation identified publicly visible infrastructure associated with Agoda through **Shodan**.

The main identified result was:

* **IP:** `45.113.60.20`
* **Hostname:** `www.agoda.com`
* **Organisation:** Agoda Company Pte. Ltd.
* **Port:** `443`
* **Service:** HTTPS
* **SSL certificate:** Associated with `agoda.com`

Additional Agoda-related infrastructure was identified through **AWS**.

These findings demonstrate that information about Agoda's internet-facing infrastructure can be obtained through passive reconnaissance. However, the report did **not** identify a confirmed vulnerability, exposed credential or active compromise. Therefore, the infrastructure should be regarded as **publicly exposed information rather than confirmed vulnerable infrastructure**. 

### 3. Data Leakage Indicators

The investigation did not identify confirmed publicly exposed Agoda documents. However, **Have I Been Pwned** identified an `@agoda.com` email address appearing in **10 historical breach datasets between 2016 and 2024**.

The datasets included breaches involving organisations such as:

* Otelier
* RedDoorz
* Covve
* MGM Resorts

The reported information included:

* Email addresses.
* Names.
* Phone numbers.
* Physical addresses.
* Purchase information.
* Travel plans.
* Partial credit-card information.

This finding does **not** confirm that Agoda itself experienced ten breaches. The email address could have been exposed through third-party services. Nevertheless, the presence of an Agoda-associated email address in multiple breach datasets could potentially assist targeted phishing or social-engineering activity. 

### 4. Threat-Actor Perspective

The findings demonstrate several potential attack paths.

A significant potential attack path is:

**Brand impersonation → Unsolicited contact → Social engineering → Victim trust → Financial payment → Financial loss**

This reflects the WhatsApp recruitment scam documented in the report. The attack relied primarily on **psychological manipulation and trust**, rather than a technical compromise of Agoda's infrastructure. 

Another potential attack path involves publicly visible infrastructure:

**OSINT reconnaissance → Domain/IP identification → Service identification → Further targeting**

The information discovered through Shodan could potentially be used by threat actors during the reconnaissance stage of an attack. However, the investigation did not identify a vulnerability in the infrastructure. 

A third potential attack path involves exposed corporate email information:

**Third-party breach exposure → Corporate email identification → Targeted phishing/social engineering**

The investigation identified an Agoda-associated email address within historical breach datasets. While this does not prove an attack against Agoda, such information could potentially help an attacker create more convincing targeted communications. 

### 5. Business Impact

The report identified several potential areas of business impact.

* **Financial impact:** Customers may suffer financial losses through scams, while Agoda could face increased support, fraud-response and potential compensation costs.
* **Reputational impact:** Repeated impersonation of Agoda could damage public perception even where criminals are not directly connected to Agoda.
* **Customer trust:** Customers could become less confident in communications, recruitment messages and payment requests appearing to come from Agoda.
* **Operational impact:** Security and customer-support teams may need to respond to phishing reports, fraudulent accounts and impersonation attempts.
* **Regulatory impact:** A genuine personal-data compromise could create data-protection obligations, investigations or notification requirements. The investigation did not identify a confirmed Agoda data breach, so this remains a potential rather than confirmed impact. 

### 6. Recommended Mitigations

Based on the findings, the report recommends that Agoda:

* **Monitor for brand impersonation** across fake websites, domains, social-media accounts and messaging platforms.
* Establish effective **takedown processes** for confirmed phishing websites and fraudulent accounts.
* Maintain strong **SPF, DKIM and DMARC** email-authentication controls.
* Provide regular **phishing and social-engineering awareness training** to employees.
* Educate customers about verifying communications through **official Agoda channels**.
* Continue **passive OSINT monitoring** of domains, IP addresses, certificates, cloud infrastructure and exposed services.
* Monitor whether company or employee email addresses appear in **newly reported third-party breaches**.
* Maintain clear official communication channels so customers can verify whether recruitment offers, payment requests and other communications are legitimate. 

### 7. Overall Findings

The investigation concluded that **brand impersonation and social engineering** represented the clearest threat identified through the available OSINT evidence. This conclusion was primarily supported by the documented case involving a victim who lost **HK$2.6 million** after criminals impersonated Agoda recruitment staff.

The investigation also demonstrated that Agoda has a broad publicly observable digital footprint containing domains, subdomains, public services, cloud infrastructure, social-media profiles and email-related information.

However, the findings should not be interpreted as evidence that Agoda's systems were compromised. **No confirmed vulnerability or direct compromise was identified during the investigation**, and the report specifically distinguishes publicly observable exposure from confirmed security vulnerabilities. 

The assessment demonstrates the importance of **continuous OSINT monitoring** as part of defensive cybersecurity. Publicly available information can provide early indications of changes to an organisation's attack surface, possible targeting, brand abuse and exposure of information that could later be used for social engineering.

## Author

**Angel-Fiiresayemi Aigbokhan**

* **Role:** Cyber Threat Intelligence / OSINT Analyst
* **Project:** OSINT-Based Threat Intelligence Assessment
* **Target Organisation:** Agoda
* **Industry:** Travel Services / Hospitality
* **Cohort:** May '26 Cohort
* **Submission Date:** `15/08/2026`
* **Investigation Date:** `14/08/2026`
* **Contact:** Not provided in the source document

**Project Disclaimer:** This project was completed for **educational and defensive cybersecurity purposes**. The investigation used publicly available information and passive OSINT techniques only. No unauthorised access, exploitation, password attacks, vulnerability exploitation or credential collection was performed. The findings represent observations from the investigation period and should not be interpreted as proof that Agoda's systems were vulnerable or compromised. 
