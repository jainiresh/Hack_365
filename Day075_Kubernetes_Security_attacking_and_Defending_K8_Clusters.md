# TOPIC
KUBERNETES SECURITY Attacking and Defending them

# OVERVIEW
## WHAT IS KUBERNETES ?
It is an open source system for automating deployment, scaling and management of containerized applications.

## ARCHITECTURE
We have the control plane on the left side and the worker nodes on the right side.
The MASTER NODE is present on the control plane.

# ATTACKING AND DEFENDING
## INITIAL ACCESS
- web application exploit using RCE
- The attacker finds an RCE in the web app
- Exposed dashboard or Kube API SERVER
- In some Kube API server the endpoint is public

## EXPLOITATION / EXECUTION
- Reach the API endpoint externally.
- Get a shell inside one of the pods from the cluster
	- Exposed dashboard
	- App vuln RCE
## TOOLS
- kube-hunter
- TOOl used to hunt for vulns in kubernetes cluster.
- open sourced python project

## INTERNAL REON AND MUCH MORE
- Watch the video whose Link is in the REFERENCES section.

# REFERENCES
https://www.youtube.com/watch?v=OOHmg1J_8ck
