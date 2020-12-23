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
  
