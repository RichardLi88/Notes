
## Activity 1

- Confidentiality: ensuring that data is only accessible to authorised users
- Integrity: ensuring that data remains accurate and unaltered
- Availability: Ensuring that systems and data are accessible when needed
- Vulnerability: A weakness in software that can be exploited
- Threat: A potential danger that can exploit a vulnerability
- Attack: An action taken to exploit a vulnerability
- Mitigation: A security measure to reduce risk

#### Discussion Questions
1. How do the CIA Triad relate to security requirements?
	- Triads outline the three basic security requirements
2. What's the difference between a threat and a vulnerability?
	- a threat is someone (a malicious entity) exploiting a vulnerability
	- a vulnerability is an area of weakness in the application that can be exploited to cause undesired behaviour
3. Can you give a real-world example of a software vulnerability being exploited?
	- Heartbleed
		- buffer overflow bug in the (open source) OpenSSL Library
		- Allows attacker to read server private keys
		- 17% of "secure" Internet servers worldwide estimated to be vulnerable
		- Simple patch, but huge cost of patching all these servers

## Activity 2

^e0882a

#### Discussion Questions
Why is confidentiality important to the banking systems?
- As each user will have their money stored in the bank, and they access it using their identification. A lack of confidentiality will lead to the user's money being stolen 
What happens if integrity is compromised?
- Then transfers will be transferred to the wrong person
How can we ensure availability against cyber threats?
- Having backup servers available

## Activity 3
How do standards help software developers build secure applications?
- having guidelines which they have to meet will ensure a minimum security for the application
Why is compliance with security regulations important for companies?
- To not break the law
- To ensure that their security at least meets minimum standards
Can you think of an example where failure to meet security requirements led to a read-world breach?
- No

## Activity 4

#### Scenario: Student records management system

Why are access controls necessary in such a system?
- has different users only need to view different materials, limiting the controls of users so that they cannot access unnecessary information is important to ensure confidentiality.
How does encryption help maintain confidentiality?
- Ensure that even if the database is hacked, that they only have access to encrypted values which they cannot use
What are non-functional security requirements, and why are they important?
- we want to know when there is a breach
- important as we can track / potentially figure out how they breached it


