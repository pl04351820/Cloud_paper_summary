### Raft algorithm
Algorithm to guarantee the strong consistency of different replications. 
More easy to understand and implement protocols.
- If there is a leader, leader will send followers synchronization info. 
- If leader fails, election will generate a new leader.

### Key insights
- Leader elect, three states of server.
    ![Docker](/images/SM.jpg)
    - learder.
    - Candidate.
    - Follower.
- log replication, Guarantee the strong consistency by unify log informaiton. To guarantee fault-tolerance. The leader first ask to write log and then commit it to avoid crashing. After writing log, it will commit it. 
- Security.
- Member change.


### Implementation
- Term 
    Divide time slots into diffrent tems. Every term starts an election. Raft algorithm can guarantee there is only one leader in a term.
- RPC 
    - RequestVote. In electron, use this to elect a leader.
    - AppendEntries. Provide logs
- ELection process
    - Every follower become candidate, vote for itself, and send requestVote to RPC.
        - If get votes more than half. Become leader.
        - If another server win election, get receive heartbeat. Become followers.
        - If timeout, No one win election, become Candidate and start it again.

- Details
    - In every term. Followers can only vote once for one of the candiates.
    - When waiting for voting, the follower need to make sure that its item is smaller than candidates.
    - Random time for election timeout (150~300ms).

- Process for receving commandline and run.
    - Leader receive the request from client.
    - Learder add instructions to log. 
    - Sent AppendEntries RPC to followers.
    - When leader receive most of followers ack, commit the log and put to SM, and return to client. 

- Security
    - Append-Only for log.
    - Election vote. Only vote for the candidates that is newer than it.
    - Never commit the log before term. (Only term log)

- Transfer from one configuration to a new configuration.
    - Two phase strategy to guarantee safety. 

- Zip the logs with snapshot
    - Only record the result 

- Communication between clients 
    - Client only send request to leader.
    - Client will first send to follower, the follower will reject client, and then redirect to leader.
    - Client fails, and resend. 

- Avoid multiple request
    - 幕等性（like restful)
    - Use unique logo for each request.