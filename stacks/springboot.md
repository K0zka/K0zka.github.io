# spring boot

Spring boot is the most widely adopted application stack. It has integration with nearly all popular products:
- databases - relational and nosql
- messaging and integration products
- web servers (netty, jetty, tomcat, etc)
- caches

It really only has good support for own service framework: spring web. Standard jax-rs is a though ride with spring boot.

For all supported integrations, spring boot provides a dependency with version. One can try another minor version, but a different major version will likely break something. E.g. you want new ehcache with old spring boot - no that will be kind of difficult, you should upgrade spring boot to a version that supports the new version, or be happy with whatever your spring boot version gives.

When time comes to upgrade, my first thought is always that jee wasn't that bad. Ok yes jee wasn't great but it was in theory possible to develop applications built on standards. And then anyhow vendors and engineers always found ways to make apps dependent on a certain jee product, but the contracts were contracts. You wrote some crazy ejb's on the ejb 1.0 api, silly soap bindings, all that worked on later versions. Also, if you liked e.g. hibernate-x you did not have to switch to upgrade to new version just because spring boot wants it.
That's where the difference with spring is: there aren't a lot of standards.

Unfortunately the defaults just aren't good. One has to do lots of customizations. And then again, this too will have to be ported when you upgrade spring boot.

There is another 'funny' behavior of spring boot. Whatever library lands in your classpath, it activates something in spring. For example if any of your library dependencies brought in solrj, it activates a configuration for spring that is trying to connect to a solr server. Sometimes it comes as a surprise, and rarely as a positive one.

So should I think of spring boot as a library? If it is a library, then really it is the most intrusive one I have ever seen. It is probably easier to think about spring boot as an operating system, a way of life, the ultimate wisdom... yes but I am not really buyer for these.

