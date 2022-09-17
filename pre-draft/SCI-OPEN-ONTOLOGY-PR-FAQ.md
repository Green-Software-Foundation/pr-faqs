# GSF Announces Open Ontology Tool to enable customers to define its own software boundary for realising SCI specification 

> Define the software boundary for an application in a unified way

As enterprises start to understand and apply the [SCI specification](https://sci.greensoftware.foundation), it is important that we provide a common terminology to define the software boundary of the SCI application in a unified way. Having a common terminology to define the software boundary of the SCI application is the first step to drive uniformity for enterprises and practitioners implementing the SCI specification

One of the key first steps in SCI is defining the software boundary. Secondly, there are no standards, references and uniformity on how to build a software boundary, which would lead enterprises to define its own software boundary, using their own set of tools. The uniformity is required if we want to compare two versions of same application or across applications offered by different enterprises in future, to understand how changes in software boundary caused changes in SCI score. 	

The SCI Open Ontology provides a common terminology to define the software boundary of the SCI application in a unified way. Having a common terminology to define the software boundary of the SCI application is the first step to drive uniformity for enterprises and practitioners implementing the SCI specification. The SCI Open Ontology will provide an SDK. The first version of SDK would provide the following functionality
-	A base ontology model as code constructs 
-	The ontology model can be extended by enterprises to create their own software boundary
-	Convert the code to diagram representation which visually describes the software boundary.
-	Reference software boundary as examples.
-	
Once the common terminology and software boundary is defined, the scope can be extended to include various use cases like reporting or understanding what changed between two versions of SCI applications by comparing their software boundary. 

For example, assume the first version of SCI application uses three instances of the same hardware types for running the application. And after hardware optimization, the second version of SCI application now uses two instances of the same hardware type, without any changes to application and workload. This would be captured through the ontology model. When we compare these two versions, we can infer the reduction in hardware—without changing the application and workload—caused the reduction in SCI score, which reflects a positive improvement.
Leader’s Quote: One of the key first steps in SCI is defining the software boundary. This is an interesting problem to solve where we can help enterprises define the software boundary of the SCI application in a unified way and help them get started quickly with ready references.

In order to create the software boundary for SCI applications, the user needs to execute the following steps
-	Download the SDK from GitHub
-	Look at reference examples for SCI boundary and documentation
-	Write code using the SDK to create their own software boundary
-	Validate the software boundary using the  SDK validate method
-	Generate the diagram representation using SDK visualize method, which converts code into diagram representation of the software boundary.

"The SCI ontology SDK gave our practitioners a head start in defining the SCI boundary. The reference examples were very helpful to understand and visualize what constitutes a software boundary. We also went ahead and integrated the SDK as part of our SCI development work." - Customer Quote

"The SCI ontology SDK helps answer the question, 'What software components form my application?'. Whether it's calcualting an SCI score or another form of software measurement, the first step is clearly describing what exactly you are measuring, the SCI Ontology project gives you a way to describe that." - Asim Hussain, Exec Director, Green Software Foundation

To learn more, please visit https://sci-ontology.greensoftware.foundation


