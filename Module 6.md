# ETHERNET AND INTERNET PROTOCOL (IP)
## Ethernet
Ethernet opereate in the data link layer and the pysichal layer, ethernet support the following data bandwidth : 
* 10 Mbps
* 100 Mbps
* 1000 Mbps (1 Gbps)
* 10,000 Mbps (10 Gbps)
* 40,000 Mbps (40 Gbps)
* 100,000 Mbps (100 Gbps)
The minimum Ethernet frame size is 64 bytes and the maximum is 1518 bytes.Any frame less than 64 bytes in length is considered a “collision fragment” and is automatically discarded by receiving stations.
Frames with more than 1500 bytes of data are considered “jumbo”
If the size of a transmitted frame is less than the minimum, or greater than the maximum, the receiving device drops the frame.
## Ethernet Frame Fields

![net]()

