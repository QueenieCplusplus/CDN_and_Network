# CDN_and_Network
Ping、Traceroute


# Ping 

用於監測網路節點是否還活著｜｜抑或用於監測到網路節點的往返時間 RTT, Round Trip Time。

      $ping google.com
      PING google.com (172.217.24.14): 56 data bytes
      64 bytes from 172.217.24.14: icmp_seq=0 ttl=116 time=4.345 ms
      
      $ ping google.com.cn
      PING google.com.cn (172.217.175.99): 56 data bytes
      64 bytes from 172.217.175.99: icmp_seq=0 ttl=112 time=39.128 ms
      

# Traceroute

用來發現測試點和目標主機之間的路由器。
從測試點對目標主機一次發送不同 TTL 值的多封包，可加速地發現路徑上經過的路由器。

原理：路由器在轉送封包至下一個 hop 之前，會將 TTL 值 -1，直到 0 則回到測試點，（回傳傳輸時間的結果）。



      $ traceroute google.com
      
      traceroute to google.com (172.217.24.14), 64 hops max, 52 byte packets
      
       1  192.168.55.1 (192.168.55.1)  2.438 ms  1.181 ms  1.127 ms
       
       2  h254.s98.ts.hinet.net (168.95.98.254)  2.141 ms  2.661 ms  2.341 ms
       
       3  tpe4-3301.hinet.net (168.95.24.58)  2.472 ms  3.809 ms  3.852 ms
       
       4  pcpd-3211.hinet.net (220.128.12.122)  2.616 ms  4.551 ms  3.160 ms
       
       5  72.14.202.34 (72.14.202.34)  4.177 ms

       6  * * *
       
       7  209.85.243.196 (209.85.243.196)  5.646 ms
        
       8  108.170.244.139 (108.170.244.139)  4.739 ms

       9  tsa01s07-in-f14.1e100.net (172.217.24.14)  3.877 ms
       
       
       -------------------------------------------------------------------------
       
       $ traceroute yahoo.com
       
      traceroute: Warning: yahoo.com has multiple addresses; using 74.6.143.25
      traceroute to yahoo.com (74.6.143.25), 64 hops max, 52 byte packets
      
       1  192.168.55.1 (192.168.55.1)  1.764 ms  0.998 ms  1.139 ms
       
       2  h254.s98.ts.hinet.net (168.95.98.254)  2.160 ms  1.995 ms  1.967 ms
       3  tpe4-3302.hinet.net (168.95.25.58)  2.114 ms  2.174 ms  2.474 ms
       
       4  220-128-4-134.hinet-ip.hinet.net (220.128.4.134)  2.733 ms  2.608 ms  2.756 ms
       5  r4102-s2.tp.hinet.net (220.128.14.93)  2.483 ms  2.906 ms
          r4102-s2.tp.hinet.net (220.128.7.69)  3.455 ms
       6  r4002-s2.tp.hinet.net (220.128.31.25)  2.570 ms  2.671 ms  2.559 ms
       7  r12-pa.us.hinet.net (202.39.91.29)  127.031 ms  129.162 ms  127.047 ms
       8  202-39-82-25.hinet-ip.hinet.net (202.39.82.25)  128.945 ms  136.553 ms  131.378 ms
       
       9  ae-7.pat2.dnx.yahoo.com (216.115.96.115)  151.903 ms  152.112 ms  152.077 ms
      10  ae-3.pat2.che.yahoo.com (216.115.96.54)  179.092 ms  176.538 ms  176.435 ms
      11  ae-9.pat2.bfz.yahoo.com (216.115.101.199)  186.858 ms
          ae-10.pat2.bfy.yahoo.com (184.165.16.0)  197.644 ms  206.787 ms
          
      12  et-2-1-1.pat1.bfz.yahoo.com (216.115.104.77)  186.982 ms
      
          
      13  et-19-1-0.msr2.bf1.yahoo.com (74.6.227.141)  188.735 ms

      14  lo0.fab7-1-gdc.bf2.yahoo.com (74.6.123.238)  188.926 ms  188.787 ms
          
      15  lo0.fab4-1-gdc.bf2.yahoo.com (74.6.123.241)  187.604 ms
         
      16  usw2-1-lbb.bf2.yahoo.com (74.6.98.139)  187.076 ms
         

# DHCP & DNS 

倘若主機位置是透過 DHCP 獲得，因為有分配的 ip 位址具時效性，則 DNS 對其無能為力。
