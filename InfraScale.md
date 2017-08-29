Infra wise I will chose AWS because of the wide variety of services they provide. 
Also I will not dockerize the database as that might affect data persistence.

**Deployment**
	Since we are planning on a scalable microservices, I will go ahead with deployment in ECS along with ECR.
    I will have a jenkins setup which will push the docker artifact to ECR from where it will download in ECS and set the app up for scale using application load balancer.
    
    
**App Scaling**
	This again being done in ECS has its advantage combining this with auto scaling gives me flexibility to scale to numerous workloads.
    
    
**DB Scaling**
	In this section however I will not go with the current setup however I would prefer AWS RDS as that will reduce the operational overhead and has the advantage of geo replication and multiple slave servers.
    So since the current app is a read only app in order to scale it by magnitudes I would introduce a read endpoint which can be load balanced abong multiple slave rds instances.
    
    
**Monitoring/Alerting**
	For monitoring I would prefer Datadog for they provide out of the box support for docker.
    
    
**Logging**
	For logging first I would mount the log directory as a docker volume then would ship the logs using filebeat to an ELK server for log aggregation and processing.
