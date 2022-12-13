# Microservices

Microservices is an architectural style, where the system is composed of multiple processes, rather than a single application image.

One could say that enterprise systems have never been built out of a single software, it has always been composed out of modules which got integrated _anyhow_... like crm, cms, identity service, and so on.
The word microservice is in general used when even the usual components are broken up to smaller pieces, which communicate with each other... anyhow, but mostly through REST.

That already introduces some complexity, because there are a lot more things to decide about a remote call, than a simple in-application method call to a service object.
You can of course manage the complexity, but when you break up an application to microservices, the overall complexity will grow. And therefore also the workhours spent, and also the budget burned will grow.

Practically, there will be no way back. There are many people who can convert your pig to pork, but no one will make a pig out of it again.
This is because as soon as you fotked out varios services, they start an independent life, they have various dependencies, they run in their own special settings.

The resource consumption will grow. When the services were all in single image, calling a method was ultra-cheap. Now you need network for the same, the cpu will have to spend extra time with ssl handshake, data serialization, maybe even compression.
The memory consumption too will grow. So far you loaded the libraries and their datastructures into memory only once. Now with each microservice once.

Yes you have gained modularity, the death of a microservice doesn't necessarily mean all micrservices are dead. Not necessarily, but still usually. The identity service dead, all dead.


