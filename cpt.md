<h1>CISCO PACKET TRACER</h1>

<h2>DHCP config on network with single router </h2>
<b>CLI</b><br>
<ol type="roman">
  <li>int <i>port-name</i> - int fa0/0, int serial2/0</li>
  <li>ip address <i>ip-address subnet mask</i> - ip address 192.168.1.1 255.255.255.0</li>
  <li>no shutdown</li>
  <li>exit ip config(ctrl+c)</li>
  <li>conf t (or) configure terminal</li>
  <li>ip dhcp excluded-address <i>Range of excluded ip address for the network</i> - ip dhcp excluded-address 192.168.1.0 192.168.1.100<i>(optional)</i></li>
  <li>ip dhcp pool <i>pool-name</i> - ip dhcp pool XYZ</li>
  <li>network <i>ip-address subnet-mask</i> - network 192.168.1.1 255.255.255.0</li>
  <li>default-router <i>ip-address</i> - default-router 192.168.1.1 (defualt gateway)</li>
  <li>dns-server <i>ip-address</i> - dns-server 8.8.8.8</li>
  <li>ip route <i>newtork ip address subnet mask entry ip address</i> - ip route 192.168.43.1 255.255.255.0 192.168.2.2</li>
</ol>
  
<h2> NATting using static configuration</h2>
<b>CLI/Terminal(system connected to router using rs32 cable)</b>

<ol type="roman">
  <li>en -> conf t</li>
  <li>int <i>port-name</i> - int fa0/0, int serial2/0</li>
  <li>ip address <i>ip-address subnet mask</i> - ip address 192.168.1.1 255.255.255.0</li>
  <li>no shutdown</li>
  <li>exit ip config(ctrl+c)</li>
  <li>conf t (or) configure terminal</li>
  <li>int <i>port-name</i> - int fa1/0, int serial2/0[PORT-2 or the PORT connecting to adjacent router]</li>
  <li>ip address <i>ip-address subnet mask</i> - ip address 192.168.1.2 255.255.255.0[PORT-2 or the PORT connecting to adjacent router]</li>
  <li>no shutdown</li>
  <li>exit ip config(ctrl+c)</li>
  <li>conf t (or) configure terminal</li>
  <li>int <i>port-name</i> - int fa0/0, int serial2/0[Internal]</li>
  <li>nat inside enable - [private network]</li>
  <li>exit</li>
  <li>int <i>port-name</i> - int fa1/0, int serial2/0[PORT-2 or the PORT connecting to adjacent router]</li>
  <li>nat outside enable - [public network]</li>
  <li>access-list <i>arbitrary number</i> permit <i>address range(wildmask subnet)</i> - access-list 1 permit 192.168.1.0 0.0.0.255 {meaning: 192.168.1.0-192.168.1.255}</li>
  <li>ip nat inside source list <i>arbitrary number as given in previous command</i> interface <i>interface connecting to external network</i> overload - ip nat inside source list 1 interface fa1/0 overload</li>
  <li>exit</li>
  <li>ip interface brief - [connection status](optional</li>
  
  <li>GO TO OTHER ROUTER</li>
  <li>en -> conf t</li>
  <li>int <i>interface-name</i> - int fa1/0</li>
  <li>ip address <i>ip address</i> - ip address 117.45.23.2</li>
  <li>no shut -> exit</li>
</ol>
  
  
  
  
