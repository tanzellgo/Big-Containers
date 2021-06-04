# Big-Containers

1. Create EC2 Instances

2. Configure inbound rules

3. HTTP from anywhere

4. Port 8000 from anywhere

5. Initialize the Swarm

6. SSH into manager1: $ docker-machine ssh manager1

7. Prompt should appear as shown

Run $ docker swarm init --advertise-addr MANAGER_IP
The swarm is now initialized and the node that MANAGER_IP belongs to is now a manager
Check swarm status: docker node ls
Output should show details of the node that has been assigned as manager

1Join as worker node or manager node
Find out command on how to join swarm as a worker/manager node
For worker: docker swarm join-token worker
For manager: docker swarm join-token manager
The node will have joined the swarm
Adding worker nodes to the swarm
SSH into worker1 instance
Enter command generated from 2.e
Repeat for other instances
Check the nodes in the swarm
Run docker node ls
Create services
docker stack deploy --compose-file docker-stack.yml vote
Vote_frontend
Vote_backend
Vote_default
Vote_vote
Vote_result
Verify stack deployment
docker stack services vote
