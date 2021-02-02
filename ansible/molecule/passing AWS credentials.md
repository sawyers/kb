# Passing AWS credentials to molecule converge targets

## Issue

Converge stage fails because the target resource, docker for example, doesn't have access to the AWS credentials from the running host.

I'm sure there is a good way, but in the context of the work project requirements I have yet to find a way that seems clean to me. Partly because the play in question connects as centos, then runs everything as root, but some items are run via runuser as another user, so getting the key passed correctly along that chain is neigh impossible without altering the play, which is out of scope for the ticket. I ended up moving from docker to ec2 driver and use the attached IAM role, which does work.

However, because it was taking so long to create a mock application server I ended up needing to drop the attempt for now since it was consuming more time than would be acceptable for the task at hand.  

I hope to re-visit this in the future to get a mock application server so that any number of roles could be tested quickly without needing full stack deployments just to verify a process change.
