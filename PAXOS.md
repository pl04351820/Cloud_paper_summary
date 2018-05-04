### Simple Paxos
![simple_paxos](/images/simple_paxos.png)
Phases:
1. Prepare.  
    Number N as version.
2. Promise 
    N > previous version, accept the proposal.
3. Accept 
    Acceptor acquire too many
4. Accepted

Problem: 
1. Liveness. Proposer proposes too many times. Solution: random duration time.
2. Hard to implement. Too many roles and hard to manage
3. Low efficiency. 2 RPC, it's complex

### Multi Paxos
Solution for Simple -> only proposer in system. Call it leader.

![multi_paxos](/images/multi_paxos.png)
1. First round RPC (Leader elect)
2. The following RPC is only one-round untill it crash. 

![simple_multi_paxos](/images/multi_paxos_industry.png)
Reduce the roles. Combine proposer, acceptor, and learner.