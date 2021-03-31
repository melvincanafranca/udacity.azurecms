# Write-up Template

### Analyze, choose, and justify the appropriate resource option for deploying the app. *For **both** a VM or App Service solution for the CMS app:*

### App Service justification
| Feature | App Service | Virtual Machine |
| ------ | ------ | ------ |
| Costs | Scale only depends on the load applied to the application so at a minimum you are sure that the base amount for app service cost will be invoiced monthly. Platform is managed by Azure so you don't need to pay IT roles to maintain and patch servers. See https://azure.com/e/d26869a9ccf44cfe8c67ffe7313c0845 for costs comparison of the compute services. | To achieve availability and resiliency you need to maked your architecture redundant, at a minimum you need to provision four servers. Two (2) servers deployed per Availability Zone each servers assigned to different fault domains. This means quadruple the cost (plus load balancer cost) with a risk of not using the full potential of the servers that were provisioned. On the other hand, there is an option to purchase a Reserved Instance plan to reduce your cost up to 59% if you are willing to commit up to 3 years. You need to also factor the IT roles needed to maintain and patch the servers.  See https://azure.com/e/d26869a9ccf44cfe8c67ffe7313c0845 for costs comparison of the compute services.
| Scalability | Can dynamically scale without a need to re-deploy application. | Scalability depends on metrics threshold being breached (auto-scale) or not reached (auto de-scale). There is a need to design application and infrastructure to handle fluctuating traffic.
| Availability | Has redundant servers which makes it highly available. | Requires multiple VMs to be deployed in different Availability zones for app resiliency.
| Workflow | Instant deployment! Deployment is less complex for the dependencies and runtime for Python are already set-up for you. Azure takes care of application deployment and management (managed service). | Gives you full control over the application management but it requires you to hand stitch the dependencies needed in order to run your Python application.

### Assess app changes that would change your decision.

*Detail how the app and any other needs would have to change for you to change your decision in the last section.* 

| # | VM over App Service | App Service over VM |
| ------ | ------ | ------ |
| 1 | Choose VMs over App Service if you need more controls for the configuration of your application.| Choose App Service over VMs if you need to deploy your application in painless way with minimum effort needed to configure the dependencies.
| 2 | Choose VMs over App Service if you application is custom or on-prem proprietary. Lift and shift might be a better approach to keep your application's environment with the same with on-prem | Choose App Service over VMs for greenfield and cloud-native applications.
| 3 | Choose VMs over App Service if the image of your VM is not supported by App Service or if needs to support 32 bit and 64 bit environments. | Choose App Service over VMs if your application don't have dependencies on image or bit support.
