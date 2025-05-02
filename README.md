# BGP Configurations

Each provider requires slightly different BGP configurations to announce my ASN upstream for my IP address range. All configurations are stored here as a reference.

## BGP Server Configuration Files

- **server1.frr.conf**: Used by FRR running on Ubuntu 24.02.2

## Common Variables (with Examples)

- `<local machine hostname>` `localhost.domain.com`
- `<my AS>` `12345`
- `<remote AS>` `54321`
- `<name of upstream provider>` `Upstream Provider BestHosting`
- `<my IP address to announce>` `8.8.8.1`
- `<neighbor IP>` `8.8.1.1`
- `<my IP range and subnet to announce>` `8.8.8.0/24`

## Common BGP Commands

### Show BGP Unicast Summary

```bash
sudo vtysh -c "show bgp ipv4 unicast summary"
```

*Displays a summary of all BGP routes along with the state of BGP peers.  
Use it as a quick check to verify that your BGP sessions are active and that routes are being exchanged.*

### Show Detailed Routing Information for an IP Prefix

```bash
sudo vtysh -c "show bgp ipv4 unicast xxx.xxx.xxx.0/24"
```

*Replace `xxx.xxx.xxx.0/24` with the IP address range being announced.  
This command provides detailed routing information for the specific IP prefix.*

### Show Advertised Routes to a Specific BGP Neighbor

```bash
sudo vtysh -c "show ip bgp neighbors xxx.xxx.xxx.xxx advertised-routes"
```

*Replace `xxx.xxx.xxx.xxx` with your upstream neighbor IP address.  
This command shows the routes being advertised to a specified BGP neighbor and can help troubleshoot to ensure that the expected routes are shared with your upstream neighbor.*
