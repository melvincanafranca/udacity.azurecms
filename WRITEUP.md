# Write-up Template

### Analyze, choose, and justify the appropriate resource option for deploying the app.

*For **both** a VM or App Service solution for the CMS app:*

### App Service justification
- *Costs: Going full serverless for the solution will make you save more money in the long run for you are sure that the you are maximizing the amount of compute that you've put into the solution compared to having idle resources in a VM*
- *Scalability: App Service is dynamically scalable which is a win compared to a VM that wherein you need to create metrics and watch if those metrics are breached before triggering an auto scale or auto de-scale*
- *Availability: App Service has redundant servers which makes it highly available. VMs on the other hand can also achieve availability but will require you to deploy your app in multiple VMs in different Availability zones to make your app resilient*
- *Workflow: App Service deployment is less complex for the dependencies and runtime for Python are already set-up for you. VM deployment on the other hands requires you to hand stitch the dependencies needed in order to run your Python application.*
- *Choose the appropriate solution (VM or App Service) for deploying the app*

### Assess app changes that would change your decision.

*Detail how the app and any other needs would have to change for you to change your decision in the last section.* 

- *The only reason that my choice of solution will change to a VM one is if there are customized features needed by the app that the webapp will not be able to provide.*