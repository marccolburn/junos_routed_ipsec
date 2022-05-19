Routed IPSec Configuration
=========

Configure Routed IPSec Tunnels for Junos.

Requirements
------------


Role Variables
--------------
ipsec_route_vpns: List of Dictionaries containing IPSec st0 info and security zone config.
* id: tunnel unit, string
* address: st interface IP address, string
* physical_interface_zone: security zone that physical interface is assigned to, string
* tunnel_zone: security zone tunnel interface is assigned to, string

ike_proposals: List of dictionaries containing ike proposals to be used for IPSec tunnels
* name: Name of the IKE proposal, string
* authmethod: Authentication method of IKE proposal, string
* dhgroup: Diffie Helman group for IKE proposal, string
* auth_algorithm: Authentication algorithm for proposal, string
* encrypt_algorithm: Encryption algorithm for proposal, string

ike_policies: List of dictionaries containing IKE policies to be used for IPSec tunnels
* name: IKE Policy Name
* mode: IKE policy mode
* proposal: IKE proposal to be used with policy
* key: Pre-shared Key to be used for policy (optional)

ike_gateways: List of dictionaries containing IKE gateways to be used for IPSec tunnels
* name: IKE Gateway name
* ext_interface: External interface IKE Gateway is assigned to
* ike_policy: IKE Policy attached to this gateway
* address: Address of the far end of the tunnel
* version: IKE version

ipsec_proposals:
ipsec_policies:
ipsec_vpns:
ipsec_mss:


Dependencies
------------

N/A

Example Playbook
----------------

    - hosts: all
      roles:
         - { role: junos_routed_ipsec }

License
-------

BSD

Author Information
------------------

Marc Colburn Juniper
