# BGP Configurations

Each provider requires slightly different BGP configurations to announce my ASN upstream for my IP address range.
All of them are stored here as a reference

## BGP Server Configuration Files

server1.frr.conf: Used by FRR running on Ubuntu 24.02.2

## Common variables with examples

local machine hostname - localhost.domain.com
my ip address to announce - 8.8.8.1
neighbor IP - 8.8.1.1
my ip range and subnet to announce- 8.8.8.0/24


## Common BGP Commands
sudo vtysh -c "show bgp ipv4 unicast summary"
  ### This command displays a summary of all BGP routes along with the state of BGP peers.
  ### Use it as a quick check to verify that your BGP sessions are active and routes are being exchanged.

sudo vtysh -c "show bgp ipv4 unicast xxx.xxx.xxx.0/24"  # Replace xxx.xxx.xxx.0/24 with the IP address range being announced
  ### This command provides detailed routing information for the specific IP prefix.
  ### Use it to confirm that the correct IP range is being advertised in your BGP session.

sudo vtysh -c "show ip bgp neighbors xxx.xxx.xxx.xxx advertised-routes"  # Replace xxx.xxx.xxx.xxx with your upstream neighbor IP address
  ### This command shows the routes being advertised to a specified BGP neighbor.
  ### Use it to troubleshoot and ensure that the expected routes are being shared with your upstream neighbor.
