# Scaling

Before starting the definition of load balancing,

let’s take an example.

----
Suppose we have 4 employees Ram, Raj, krish and Mohan respectively in a project. The client gave 4 tasks. Let’s say manager assigns these 4 tasks to employ Ram. What will happen? Load on employee A will increase. It will not be handled properly and performance will be low. Instead of assigning all tasks to only one employee distribute 4 tasks among 4 employees. Now, the load will be balanced so performance will be increased. Efficiency will be high.

## What is Load Balancing?

![image](https://user-images.githubusercontent.com/52858203/183289654-4654f8ed-0f76-40a8-ae59-fd4ca0b9509e.png)

Load balancing is the process to distribute the workloads among servers.Load Balancer does the routing.

For example, request1 goes to this particular server and request2 goes to a different server to balance the load.


### Why load balancing is required?

- To avoid overload of any single resource.
- To increase performance.
- To handle sudden traffic spikes.
- To minimize response time.
- To optimize resource use.

## Load Balancing Algorithms:

### 1. Round Robin Algorithm:

Most widely used algorithm. Let’s say you have two servers waiting for requests once the first request arrives, the load balancer will forward that request to the first server. When the second request arrives then that request will be forwarded to the next server. The next request will be forwarded to the first server. The fourth will back to the second server and so on.


### 2. Weighted Round Robin Algorithm:

For example, if server 1’s capacity is more than Server 2 then Weighted Round Robin Algorithm will be good. You assign “weights” to each node while setting up the load balancer. The one with the higher capacity should be given the higher weight.

Let’s take an example. Suppose you have two servers. Server 1 and Server 2 and are having 4 tasks. Server 1 has a capacity 3 times more than Server 2. Server 1 weight = 3. First 3 tasks will be forwarded to Server 1 and task 4 will be forwarded to Server 2.


### 3. Least Connections Algorithm:

Here it will assign the new connection to the server which is having the least number of connections.


### 4. Random Algorithm:

Here we can select a node on randomly.

### 5. IP Hash Algorithm:

Here the request will be sent to the server based on Client IP

### 6. Google Cloud load balancing.

You can balance compute resources in single or multiple regions in Google Cloud Platform. No pre-warming required with Google Cloud Load Balancing.


## Types of Google Cloud load balancing.


### 1. HTTP(S) load balancing:

- It is Global.
- It is used to balance HTTP and HTTPS traffic across multiple regions.


### 2. SSL Proxy load balancing:

- It is Global.
- For non-HTTPS traffic use Cloud SSL Proxy Load Balancing.


### 3. TCP Proxy load balancing:

- It is Global.
- It terminates TCP sessions at the load balancing layer. Using SSL or TCP it will forward the traffic to virtual machine instance.


### 4. Network TCP/UDP load balancing:

- It is the Regional.
- Use Network Load Balancing for UDP, TCP and SSL traffic that is not supported by TCP and SSL Proxy.


### 5. Internal TCP/UDP:

- It is the Regional.
- To configure an Internal Load Balancing IP address use Internal Load Balancing.

## uto Scaling in Cloud Computing:

![image](https://user-images.githubusercontent.com/52858203/183290725-bc1503e0-ef9d-4f18-b5b6-71e31bc7ce98.png)


Auto Scaling adds, removes and computes resources depending upon usage. It scales automatically based on the load. When the application needs more computing resources, you can increase when you don’t need you can decrease the compute resources. Auto Scaling only works with managed instance group.


Let’s take an example of an e-commerce portal. Most of the people are busy on weekdays. They don’t get time for shopping on an e-commerce portal so traffic is low on weekdays as compared to weekends. There is less need for resources on weekdays compared to weekends, for this Auto Scaling works. Resources will automatically increase when there is a spike in traffic.


## You can do Auto Scaling in Google Cloud Platform in following way.

- Create a custom image.

- Create an instance template using the custom image which you have created above. Once you created an instance template, you can use this template in the managed instance group.
- Create a managed instance group. Here you can use the instance template which you created. Also enable Autoscaling, add Autoscaling policy and add the - Maximum number of instances in the given section. While creating a managed instance group here you will receive a warning that tells there is no load balancer. That’s OK; you can attach the managed instance group while creating the load balancer.
- Create a load balancer. While creating a load balancer you can use the managed instance group which you previously created.


### Why Auto Scaling:

- Cost efficient: Pay only for what you required.
- Handle a sudden traffic spike.
- Auto-healing: If HTTP health check sees a service has failed on an instance, re-create instance where service failed.
- Scalability: Scale as per the requirement.








