Sunny is a SOC analyst at E-corp, which manufactures rare earth metals for government and non-government clients. She receives a classified intelligence report that informs her that an APT group (APT28) might be trying to attack organizations similar to E-corp. To act on this intelligence, she must use the MITRE ATT&CK Navigator to identify the TTPs used by the APT group, to ensure it has not already intruded into the network, and to stop it if it has.

**Task 1 - Understand the Adversary**

*Q1: What is a technique used by the APT to both perform recon and gain initial access?*

A: A **Spearphishing Link** is a technique used by the APT to both perform recon, and gain initial access by targeting specific members of an organization.

*Q2: Sunny identified that the APT might have moved forward from the recon phase. Which accounts might the APT compromise while developing resources?*

A: A type of account that the APT may have compromised while developing resources are **Email Accounts**. This is possible assuming they have moved forward from the recon phase.

*Q3: E-corp has found that the APT might have gained initial access using social engineering to make the user execute code for the threat actor. Sunny wants to identify if the APT was also successful in execution. What two techniques of user execution should Sunny look out for? (Answer format: <technique 1> and <technique 2>)*

A: Sunny needs to look out for **Malicious Files and Malicious Links** during the execution phase.

*Q4: If the above technique was successful, which scripting interpreters should Sunny search for to identify successful execution? (Answer format: <technique 1> and <technique 2>)*

A: The two scripting interpreters Sunny should search for in order to identify successful execution are **PowerShell and Windows Command Shell**.

*Q5: While looking at the scripting interpreters identified in Q4, Sunny found some obfuscated scripts that changed the registry. Assuming these changes are for maintaining persistence, which registry keys should Sunny observe to track these changes?*

A: Assuming these changes are for maintaining persistence, Sunny should look at the **Registry Run Keys**.

*Q6: Sunny identified that the APT executes system binaries to evade defences. Which system binary's execution should Sunny scrutinize for proxy execution?*

A: **rundll32** is a system binary whose execution should be scrutinized for proxy execution. 

*Q7: Sunny identified tcpdump on one of the compromised hosts. Assuming this was placed there by the threat actor, which technique might the APT be using here for discovery?*

A: The APT may be using the **Network Sniffing** technique for discovery.

*Q8: It looks like the APT achieved lateral movement by exploiting remote services. Which remote services should Sunny observe to identify APT activity traces?*

A: Since APT achieved lateral movement by exploiting remote services, it is likely that **SMB/Windows Admin Shares** were used.

*Q9: It looked like the primary goal of the APT was to steal intellectual property from E-corp's information repositories. Which information repository can be the likely target of the APT?*

A: If the APT was after intellectual property, they are most likely after E-corp's **Sharepoint** repositories.

*Q10: Although the APT had collected the data, it could not connect to the C2 for data exfiltration. To thwart any attempts to do that, what types of proxy might the APT use? (Answer format: <technique 1> and <technique 2>)*

A: To bypass the firewall and connect to the C2 for data exfiltration, the APT may employ techniques such as utilizing an **External Proxy or a Multi-hop Proxy**.

**Thanks for Reading!**