# GcpHttpLbAppID

This repo contains 2 skillets.
1. GcpHttpLbAppID skillet to create the Palo Alto Networks App-ID for the AWS HTTP Load Balancer Health Probe.
2. move_rule_rest skillet to move the rule to its properly location above the actual application rule and commit.

This is also a workflow skillet included to run them in sequence.  Waiting a bug in panhandler to be fixed which is preventing the execution of the second skillet.

- PAN-OS Supported:  v8.1 and v9.0
- Cloud Provider(s) Supported:  GCP
- Type of Skillet:  XML and REST
- Purpose:  Config

## Variables AppID

  - name: appid_name
    - description: appid name (32 total char limit)
    - default: appidname
    - type_hint: text
  - name: appid_description
    - description: appid_description
    - default: appid_description
    - type_hint: text
  - name: address_name
    - description: appgw_source_address_subnet
    - default: appgw_source_address_subnet_name
    - type_hint: text
  - name: address_cidr
    - description: appgw_source_address_subnet
    - default: 10.0.0.0/24
    - type_hint: text    
  - name: address_description
    - description: appgw_source_address_description
    - default: appgw_source_address_description
    - type_hint: text      
  - name: rule_name
    - description: security_rule_name
    - default: security_rule_name
    - type_hint: text
  - name: rule_description
    - description: security_rule_description
    - default: security_rule_description
    - type_hint: text  

## Variables - Move Rule
  - name: TARGET_IP
    - description: Host
    - default: 127.0.0.1
    - type_hint: ip_address
  - name: TARGET_USERNAME
    - description: Username
    - default: admin
    - type_hint: text
  - name: TARGET_PASSWORD
    - description: Password
    - default: admin
    - type_hint: password
  - name: rule_name
    - description: name of security rule to move
    - default: rule1
    - type_hint: text
  - name: ref_rule
    - description: rule to move before or after
    - default: rule2
    - type_hint: text
  - name: where
    - description: move before or after other rule
    - default: top


## Support Policy
The code and templates in the repo are released under an as-is, best effort,
support policy. These scripts should be seen as community supported and
Palo Alto Networks will contribute our expertise as and when possible.
We do not provide technical support or help in using or troubleshooting the
components of the project through our normal support options such as
Palo Alto Networks support teams, or ASC (Authorized Support Centers)
partners and backline support options. The underlying product used
(the VM-Series firewall) by the scripts or templates are still supported,
but the support is only for the product functionality and not for help in
deploying or using the template or script itself. Unless explicitly tagged,
all projects or work posted in our GitHub repository
(at https://github.com/PaloAltoNetworks) or sites other than our official
Downloads page on https://support.paloaltonetworks.com are provided under
the best effort policy.
