# VYOS Config
set protocols bgp listen range 192.168.86.0/24 peer-group 'k8s'

set protocols bgp peer-group k8s address-family ipv4-unicast

set protocols bgp peer-group k8s remote-as 'internal'

set protocols bgp system-as '64512'

set service ssh

# Cluster Calico Config for RKE2

installation:

    calicoNetwork:
  
      bgp: enabled
