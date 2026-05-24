# B26) Help another student in this unit struggling to understand/learn a cybersecurity concept

For this activity, I helped another student in the unit, Anindya Sen, understand the cybersecurity concept of Server-Side Request Forgery (SSRF). Initially, he was confused on the topic and wanted to understand better about how attackers could make a website send requests on their behalf and why internal resources such as localhost or cloud metadata services were dangerous targets. 

I explained that SSRF works by abusing website features that fetch external URLs, such as image fetchers, URL preview tools, PDF generators or import/export functions. In vulnerable applications, attackers can manipulate these features to force the server to access internal systems that normal users cannot directly reach.

During the discussion, I explained that the vulnerable server effectively becomes a proxy for the attacker because it has access to internal networks and trusted services. I also discussed common SSRF mitigation techniques, including strict allow-listing of URLs, blocking internal IP ranges, proper URL validation and network segmentation. By the end of the conversation, Anindya stated that the concept made much more sense and that he now understood SSRF as an abuse of the server’s trust level rather than simply another type of web attack. This activity also helped reinforce my own understanding of SSRF and improved my ability to explain technical cybersecurity concepts in a simpler and more understandable way.

