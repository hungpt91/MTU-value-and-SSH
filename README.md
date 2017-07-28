# MTU-value-and-SSH
Giá trị mtu của card mạng trong môi trường PPPoE không được quá 1500. Nếu lớn hơn sẽ gây phân mảnh khi truyền gói tin.
Đối với giao thức SSH, khi gói tin truyền đi bị phân mảnh thì không thể kết nối được.Ngoài ra, có thể gây ảnh hưởng đến một số giao thức khác.

For PPPoE, your MaxMTU should be no more than 1492 to allow space for the 8 byte PPPoE "wrapper," but again, experiment to find the optimal value. For PPPoE, the stakes are high: if you get your MTU wrong, you may not just be sub-optimal, things like UPLOADING or web pages may stall or not work at all!
~~~~~~~~~~~~~~~~~~~~~~~~~~~

(TCP, IP, MTU and MSS magic numbers)
40
1500	The biggest-sized IP packet that can normally traverse the Internet without getting fragmented. Typical MTU for non-PPPoE, non-VPN connections.
1492	The maximum MTU recommended for Internet PPPoE implementations.
1472	The maximum ping data payload before fragmentation errors are received on non-PPPoE, non-VPN connections.
1460	TCP Data size (MSS) when MTU is 1500 and not using PPPoE.
1464	The maximum ping data payload before fragmentation errors are received when using a PPPoE-connected machine.
1452	TCP Data size (MSS) when MTU is 1492 and using PPPoE.
576	Typically recommended as the MTU for dial-up type applications, leaving 536 bytes of TCP data.
48	The sum of IP, TCP and PPPoE headers.
The sum of IP and TCP headers.
28	The sum of IP and ICMP headers.


References:
http://www.snailbook.com/faq/mtu-mismatch.auto.html
http://www.dslreports.com/faq/695
