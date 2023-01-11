# GSF announces open source project to enable customers to define the boundary of a software application.

> Define the software boundary for an application in a unified way.

It is difficult to measure the impact of software changes without a clear understanding of *what* you are measuring. The SCI Open Ontology SDK provides a way to describe the software components that make up your software application and their relationship to one another. This is the first step in calculating any sustainability metric for your application, for example, an SCI score.

As enterprises start to understand and apply the [SCI specification](https://sci.greensoftware.foundation), we must provide a common terminology to define the software boundary of the application in a unified way. Having a common terminology to define the software boundary of the application is the first step to driving uniformity for enterprises and practitioners implementing the SCI specification.

One of the critical first steps in SCI is defining the software boundary. However, there are no standards, references, or uniformity in defining a software boundary, which would lead enterprises to define their software boundary using their own set of tools. Uniformity is required if we want to compare two versions of the same application or across applications offered by different enterprises in the future, to understand how changes in software boundaries caused changes in an SCI score. 	

The SCI Open Ontology provides a common terminology to define the software boundary of the SCI application in a unified way. Having a common terminology to define the software boundary of the SCI application is the first step to driving uniformity for enterprises and practitioners implementing the SCI specification. The SCI Open Ontology will provide an SDK. The first version of SDK would provide the following functionality
-	A base ontology model as code constructs. 
-	Enterprises can extend the ontology model to create their software boundary
-	Convert the code to a diagram that visually describes the software boundary.
-	Reference software boundary as examples.

Once the common terminology and software boundary is defined, the scope can be extended to include various use cases like reporting or understanding what changed between two versions of SCI applications by comparing their software boundary. 

For example, assume the first version of an application uses three instances of the same hardware types for running the application. After hardware optimization, the second version of the application now uses two instances of the same hardware type without any changes to the application and workload. This would be captured through the ontology model. When we compare these two versions, we can infer that the reduction in hardware—without changing the application and workload—caused the reduction in the SCI score, which reflects an improvement.

In order to create the software boundary for SCI applications, the user needs to execute the following steps:
-	Download the SDK from GitHub
-	Look at reference examples for SCI boundary and documentation
-	Write code using the SDK to create their software boundary
-	Validate the software boundary using the  SDK validate method
-	Generate the diagram representation using the SDK visualize method, which converts code into a diagram representation of the software boundary.

"The SCI ontology SDK gave our practitioners a head start in defining the SCI boundary. The reference examples were beneficial in understanding and visualizing what constitutes a software boundary. We also integrated the SDK as part of our SCI development work." - Customer Quote.

"The SCI ontology SDK helps answer the question, 'What software components form my application?'. Whether it is calculating an SCI score or another form of software measurement, the first step is clearly describing what exactly you are measuring. The SCI Ontology project gives you a way to describe that." - Asim Hussain, Exec Director, Green Software Foundation.

To learn more, please visit https://sci-ontology.greensoftware.foundation

## FAQ

### How long does this tool take to create an SCI boundary? 

### Who is the audience for this tool - PMs, Devs, Ops?

### Does the tool require any data feeds?

### Can the tool examine an existing application and output the ontology?

### How do you store the definition of an ontology?

### Can a human use the ontology tool from a web interface, or can it only be interacted via code?
