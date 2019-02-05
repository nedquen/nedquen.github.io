{:title "Microservices according to the academia"
  :layout :post
  :tags ["microservices"]}


During the last ten years, Cloud Computing and the relatively low cost of 
server renting services like Microsoft Azure,
Amazon and Google Cloud have opened the opportunity to build businesses around cloud computing
such as SaaS at a competitive cost.

This opportunity also brings new challenges to scale, maintain and extend those systems. A promising
style of architecting software emerges by the hand of cloud computing and as the second iteration of Service Oriented Architecture, namely,  Microservices.

While Microservices is becoming more relevant in the industry, theoretical and scientific coverage of this subject is still in a very early stage. 

## What is the  Microservices definition based on the literature? 

Our data collection strategy consisted in search for the keywords: Microservice and microservices with a particular interest in literature studies, mapping studies and surveys. Secondly, we focus mainly on three sources: the ACM Digital Library, IEEE Explore and Springer Verlags’ digital library, SpringerLink. 

## So you had a method?
yes, Indeed.

## Ok, tell me more

We extract definitions from the selected papers and identify similarities between them.

### Microservices Science and Engineering
The following corresponds to the definition extracted from the article "Microservices Science and Engineering" from 2017.

According to Mazzara et al. [12] Microservices are not just small services, but an architectural style originated from Service-Oriented Architectures. A service
is a building block that communicates exclusively by message passing. The difference from monolithic architectures and SOA is the emphasis in scalability, independence, and semantic cohesiveness of each unit.

Maintainability and evolvability are issues recognised by the authors
when talking about monolithic architectures, but coming back to the definition of microservices, another distinction from this architectural style
is that each service owns a dedicated persistence tool. The independence
of services implies that the complexity is moved to the coordination of services often called orchestration. The distributed nature of this approach involves additional problems like trust and certification. Another
interesting point mentioned in this definition is how small the service
has to be, the author's answer is a single business capability. Furthermore, a small team is fully responsible for a service which should lead to an efficient communication on a team and within the whole organisation and at the same time improving modularity to the system.

### Microservices: yesterday, today and tomorrow

From the article "Microservices: yesterday, today and tomorrow" [6] from 2017,  we extract three definitions necessaries to understand Microservices.  

The first one is the concept of Monolith. A monolith is a software application whose
modules cannot execute independently.

The authors also present six issues related to the monolithic architecture:

1. maintainability is challenging due to their complexity
2. suffer from dependency hell
3. change in one module requires rebooting the whole application, and therefore long downtimes are expected for large systems.
4. when deploying, the developer must compromise with a one-size-fits-all configuration which is either sub-optimal and or expensive concerning individual modules.
5. monoliths limit scalability. In a monolithic application, the strategy
for scaling consists of creating new instances of the same application
and split the load among instances.
6. technology lock-in. The developer cannot use other language or framework

The microservices architectural style has been proposed to cope with such problems, and this is the definition we find in [6]: A microservice is a cohesive, independent process interacting via messages.

An essential part of this definition is the concept of cohesiveness, which
is used in this case to indicate that the functionality of a service is
strongly related to the problem it was modelled to solve.
From a technical standpoint, a microservice should be an independent component deployed in isolation and equipped with dedicated
memory persistence tools.

Finally, we encounter the definition of Microservice Architecture. A microservice architecture is a distributed application where all its modules are microservices.

The authors give an example of Microservice architecture. Let us consider a functionality that consists of plotting the graph of a function.
Let us consider two microservices: Calculator and Displayer and in order to fulfil the task we introduce a third service, we called plotter, which orchestrates the services mentioned earlier.
To illustrate how this architecture scales, the calculator function can be extended by calling two other microservices: one service that handles elementary mathematical functions and special functions.
The problem I see here is that if for any reason, for instance, elementary function service is unavailable, the plotter service has to wait
depending on the failure recovery strategy implemented by the architecture.
Let us continue with the content of the paper. The microservice architectural style does not impose any particular programming paradigm; it only provides guidelines to partition components of a distributed application into independent specialised entities that solves one concern of
the overall application.
In this style of architecture, the flexibility of technology agnosticism
is given by the use of message passing.
Finally, the authors present solutions for each of the problems presented previously solely by implementing a Microservice Architecture.


1. The developer has to implement only a limited amount of functionality, which results in a small codebase and inherently limits the scope of a bug. The developer can directly test and investigate their functionalities in
isolation concerning the rest of the system.
2. The developer can plan a gradual transition to a new service which promotes continuous integration easing software maintenance.
3. Due to the previous point, it is no longer require the reboot of the
whole system when changing a module.
4. Microservices naturally fit containerisation which translate into a  high degree of freedom in configuration and deployment
environment that best suits their needs.
6. Scaling a Microservice does not imply duplication of all its components. The developer can conveniently dispose of instances of services to their load.

### Exploration of Academic and Industrial Evidence about Architectural Tactics and Patterns in Microservices

A service [13] is a well-defined function, self-contained that does not depend on the context of the state of other services, whereas the Microservices architectural style [13] is defined as an approach to developing an application as a suite of small services, each running in its process and communicating with a lightweight mechanism. In this definition we
infer that the authors are talking about operative system processes and
what they intend to describe is the memory isolation of processes.
Another characteristic mentioned in this definition is that services correspond to a business capability and that is deployed independently by a fully automated deployment mechanism. As described as well in the definitions given by J.Lewis and M. Fowlers, in the extraordinarily popular article about Microservices and by S. Newman in
the book "Building microservices: designing fine-grained systems" from
Oŕeilly media 2015; It is difficult to ignore the Microservices definition given by Cockcroft, one of the software engineers responsible for the current Netflix’ architecture: "Loosely coupled service-oriented architecture with
bounded contexts"

### Automatically Measuring the Maintainability of Service- and Microservice-based Systems – a Literature Review

The authors of this article, Bogner-Wagner and Zimmermann [3] define Service-based System (SBS) in line with M.P. Papazoglou’s definition from the paper from 2003 Service-oriented computing: concepts, characteristics and directions. An SBS [3] is a software system that leverages services as the essential computational element shares the following characteristics: they are self-contained, composable, technology-neutral, loosely coupled and allow for location transparency.
Later, microservices are defined; a Microservice-based System (μSBS)
[3] is a specialisation of an SBS that is constituted by fine-grained independent services and focuses on decentralisation of control management, lightweight communication mechanisms and technological heterogeny. The definition continues describing the organisation and coincides with characteristics we found in [13], namely, the presence of "automated deployment machinery" and a strong DevOps culture.
The definition continues mentioning that a single microservice represent a small unit of functionality, characteristic that is also present in
all previous descriptions. The authors call this characteristic "the bounded context" which increases application resiliency, efficient scalability as well as fast and independent deployment.
The paper proceeds with the analysis of the study of maintainability
of this architectures and automation of methods to measure maintainability of μSBS.

## Interesting
yes, very interesting, but there is much more. I tell you soon.


## References

[3] Justus Bogner, Stefan Wagner, and Alfred Zimmermann. “Auto-
matically Measuring the Maintainability of Service- and Microservice-
based Systems: A Literature Review.” In: Proceedings of the 27th International Workshop on Software Measurement and 12th International
Conference on Software Process and Product Measurement. IWSM Mensura ’17. Gothenburg: ACM, 2017, pp. 107–115. isbn: 978-1-4503-
4853-9. doi: 10.1145/3143434.3143443 . url: http://doi.acm.org/
10.1145/3143434.3143443 .

[6] Nicola Dragoni et al. “Microservices: Yesterday, Today, and Tomor
row.” In: Present and Ulterior Software Engineering. Ed. by Manuel
Mazzara and Bertrand Meyer. Cham: Springer International Publishing, 2017, pp. 195–216. isbn: 978-3-319-67425-4. doi: 10.1007/
978-3-319-67425-4_12 . url: https://doi.org/10.1007/978-3-319-67425-4_12 .


[12] Manuel Mazzara et al. “Microservices Science and Engineering.”
In: Proceedings of 5th International Conference in Software Engineering for Defence Applications. Ed. by Paolo Ciancarini et al. Cham:
Springer International Publishing, 2018, pp. 11–20. isbn: 978-3-
319-70578-1.

[13] Felipe Osses, Gastón Márquez, and Hernán Astudillo. “Explo-
ration of Academic and Industrial Evidence About Architectural
Tactics and Patterns in Microservices.” In: Proceedings of the 40th International Conference on Software Engineering: Companion Proceeedings. ICSE ’18. Gothenburg, Sweden: ACM, 2018, pp. 256–257. isbn:
978-1-4503-5663-3. doi: 10 . 1145 / 3183440 . 3194958 . url: http://doi.acm.org/10.1145/3183440.3194958 . 