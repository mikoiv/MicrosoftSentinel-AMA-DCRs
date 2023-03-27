Data Collecton Rule to transform Windows DHCP text logs.

The TransformKQL parses the Rawdata string into a few useful columns.

To deploy this you will need:
- Windows DHCP server with Audit files in c:\windows\system32\dhcp\.
- Data Collection Endpoint.
- Custom table: WinDHCP_CL.
- Custom columns in the table: EventType, SrcIpAddr, SrcHostname, SrcMacAddr, DhcpSessionId, DhcpVendorClass.
- DHCP servers added as Resources to both the DCE and DCR.

If you want to add more data, check your logs for the correct Rawdata format. For reference, here are the Rawdata fields in the correct order:

| ID | Date | Time | Description | IP Address | Host Name | MAC Address | User Name | TransactionID | QResult | Probationtime | CorrelationID | Dhcid | VendorClass(Hex) | VendorClass(ASCII) | UserClass(Hex) | UserClass(ASCII) | RelayAgentInformation | DnsRegError |
