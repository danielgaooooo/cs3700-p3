## High Level Approach
This program uses a TCP sliding window set at 40 packets in  
order to work. The sender sends (up to) 40 packets, and the  
receiver acknowledges what it gets. The sender removes the  
(received) acknowledged packets, advances the window by  
however many acks it received, and re-sends everything in  
that window. The packets in the window are represented by an  
internal queue. Once EOF is reached, the sender dumps the rest  
of its queue to the receiver, who, upon receipt and ack, shuts  
down. The sender shuts down right after.  
  
## Challenges I Faced
I worked on this project myself so that was a big challenge.  
Other challenges were getting the sliding window to properly  
slide upon receiving acks, properly reordering packets on the  
receiving side, and handling dropped acks as well as regular  
packets. Overall, this assignment tested my patience well.  
I was going to implement a slow-start to dynamically adjust the  
sliding window but then that became too difficult, and ended up  
just slowing it down.  
  
## How I Tested
I used print statements and the provided tests. I also used a  
classmate-submitted grading script to estimate my grades on the  
performance section.