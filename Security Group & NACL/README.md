This project mainly focuses on one of the concept of Security Groups and NACLs to add security to applications deployed in AWS.

AWS (Amazon Web Services) provides multiple layers of security to protect resources and data within its cloud infrastructure. Two important components for network security in AWS are Security Groups and Network Access Control Lists (NACLs). Let's explore how each of them works:

* Security Groups:
Security Groups act as virtual firewalls for Amazon EC2 instances (virtual servers) at the instance level. They control inbound and outbound traffic by allowing or denying specific protocols, ports, and IP addresses.
Inbound rules determine the traffic that is allowed to reach the EC2 instance, whereas outbound rules control the traffic leaving the instance.
Security Groups are stateful.


* Network Access Control Lists (NACLs):
NACLs are an additional layer of security that operates at the subnet level. They act as stateless traffic filters for inbound and outbound traffic at the subnet boundary.
Unlike Security Groups, NACLs are associated with subnets, and each subnet can have only one NACL. However, multiple subnets can share the same NACL.
NACLs consist of a numbered list of rules (numbered in ascending order) that are evaluated in order from lowest to highest.
Inbound rule allows traffic, the corresponding outbound traffic must be explicitly allowed using a separate outbound rule.



![image](https://github.com/Yogeswari-369/AWS_Projects/assets/85894796/08e8737b-c0e3-4de3-9997-88c396abdad5)



For better understanding, consider this cases

**CASE 1**
- In SG , port 8000 is allowed
- In NACL, all traffic is allowed
- Then output is displayed.

**CASE 2**
- In SG , port 8000 is allowed
- In NACL,  deny port 8080
- Then output is not displayed.

**CASE 3**
- In SG , port 8000 is allowed
- In NACL
            At rule number : 110  **Allow all traffic**
            At rule number : 100  **Deny port 8000**
- Then output is not displayed.

**CASE 4**
- In SG , port 8000 is allowed
- In NACL
            At rule number : 100  **Allow all traffic**
            At rule number : 110  **Deny port 8000**
  - Then output is displayed.
  ![image](https://github.com/Yogeswari-369/AWS_Projects/assets/85894796/9d37994f-27c2-449d-a9be-928fc93812e8)
