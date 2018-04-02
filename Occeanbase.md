## Alibaba Strong Consistency Database (Double 11)

### Key insights
- Cross Zone transaction
- SSD + memoery structure (SSD is bad for random write). This strategy reduce the costs.
- Three Zone merge everyday. Hotspot time use three zone to support write/read, and in low level time only support 1 zone. Multi - PAXOS