## Kubernetes for Dash Enterprise
Modern, agile workflow.
In the context of data science workflows.
Using data science to solve large-scale business problems, execute large cross-team initiatives or develop external product offerings.  

### Why containers?
- Orchestrating containerized applications, modern approachto managing enterprise application deployment.
- Bundles together and isolates th software, configuration files and packages that app needs to run on.
- Ensures portability across different environments.
- This supports modern agile workflows that move through development, testing, deployment and back again.
- Also provides secure siolation between different procsses and applications running on the same server so that you can have one application use one set of dependencies without conflicting with another application's dependencies.
- Faster abd easier to create abd deploy applications to discrete container images than to VM images.

**By 2023, over 70% of global organizations will run at least two containerized apps. - *Gartner*.**
- Complex architectures must be managed (many containers and hosts running); As more applications are deployed, *resource demands* change, user traffic fluctuates.
- Kubernetes helps you systematically manage these changes.
- Containers are uncoupled from their underlying infrastructure; more space efficient.
- Are hosted on **nodes; managed by the Kubernetes control plane.
- Deployent requeirements of an application (YAML file) are provided to the control plane via an API.
- In practice, nodes may run on different VMs managed by a cloud provider.
- On AWS, this might be EC2 instances.

## MAGIC

#### High Availability
- DS application may comprise many containers, each holding a different component;
- Data source, model, GUI etc.
- Kubernetes performs fault-tolerance by "self-heal" process. If a node goes down, it detects this discrepancy between the environment and the app requirements.
- Automatically deploys the missing containers on a different node. - High availability.

#### Load Balancing services.
- In situations of high resource consumption 
- (deploying new apps, scaling up existing apps for high visitor traffic)
- Kubernetes will automatically spin up new containers. - Load balacing for a stable deployment.
- YAML deployment requirements will specify the CPU and memory needs for each container; which Kubernetes will use to efficiently fit containers onto nodes.

#### Container orchestration
- Occurs across multiple VMs. (Amazon Web Services EC2 instances)
- Allowing vertical/Horizontal scaling.
- Enabling organizations to run far more apps, at greater scale across many servers, than what could be run on just a single server.

##Benefits for data science deployment
- Dynamic resource management
- Kubernetes handle the high-activity bursts associated with training ML models.
- Cost effective. Cost is correlated with resource consumption.
- Kubernetes autoscaling tracks containers' CPU usage, adding new VMs to the cluster when new applications are deployed 
- scaled up and then scaling down VMs when those apps are no longer running.
- Beats inflexibility of purchasinf deddicated CPUs or GPUs that are only periodically used for high compute processes.

#Dash Enterprise Kubernetes
- End-to-end development and deployment platform for scalable, production-grade AI dash apps written in Python, Julia, R.
- Infrastructure resources they wouldn't otherwise have on their PC.
- Authentication, git-deploy and automated reporting.

**DES builds upon the power of Kubernetes to provide these full-platform capabilities.*

*No DevOps required:* abstracts away configurations.
- Build, deploy, manage apps entirely in Python vua point-and-click.

*Build container images:* Upload their Dash app source code to a Docker image.
- Custom buildpacks tailored to support pip, conda and NVIDIA GPU.
- Just git push to upload code.
- DEK will install Python and required packages and system dependencies.

*Schedule expensive tasks:* Background job queues will handle long-running jobs like model training, scheduled jobs like:
- Data refreshes/ report generation. - in separate container.

*Control resource consumption:* Enables resiliency against an app monopolizing CPU/ Memory resources.
- DEK platform analytics are displayed in a GUI admin panel
- View no of apps, their container size, CPU/Memory usage.

*Middleware for authorization:* admins can manage user authorization and access to released apps.
- Network traffic is verified before reaching the app
- Viewer metadata is passed to the Dash app enabling implemenation of custom security logic dow to a row level.

*Middleware for embedding:* DEK enables you to embed your app into any web platform.
- Introduce your new sales forecasting app to your company's Salesforce
- Integrate predictive analytics app directly into your client-facing website.
- User's already signed into the parent website need not re-authenticate to view app

*Out-of-the-box database connectors:* facilitates app-level connection to the mst popular big data backends.
- Vaex, Dask, Datashader, RAPIDS, Databricks(PySpark), Snowflake, Postgres, Saleforce.

*Caching and session data:* Dashapps are stateless- many copies can be run simultaneously without disrupting user experience.
- Uses Redis containers to manage shared memory between these copies.

*Logging:* DEK admins can view remote app-level logs of web traffic, usage data and job queues in a web-based userinterface without having to access the server directly.

*Monitoring and alerting:* If model's output exceeds mandated thresholds, receive an automated PDF report in your inbox;
- View an archived snapshot of the app at the point in time.
- DEK's Snapshot Engine handles the lerting, monitoring and reporting.

Develop Production Apps. - Built-in Jupyter & IDE.
Build Source Code + Docker Image: - Buildpacks - Create Docker images from Source Code.
Hyperscale - Docker Image --> Run Docker Containers. - App Manager
Release  - Deployment --> End user traffic - Authentication Middleware.
Configure - Manage Released Application - Secret Manager
Consume --> Value for Line of Business - Dash App UI
