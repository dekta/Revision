## Run time vs Compile time?

Run time and compile time are programming terms that refer to different stages of software program development. After a developer writes ***a source code, this code must be compiled into machine code in order to become an executable program***. This is referred to as **compile time**.

***A compiled program can be opened and run by a user. When the application is running, it is called run time.***



## What is Interpreted language?

*‘What static and dynamic typing are?’, also ‘What static and dynamic binding is?’*
Static indicates that resolution takes place at the time a program is constructed — **compile time**. Dynamic indicates that resolution takes place at the time a program is run — **run time**.



## What static and dynamic typing is?

Static typing means that the executable form of a program generated at compile time will vary depending upon the types of data values found in the program. Dynamic typing means that the generated code will always be the same irrespective of the type — any differences in execution will be determined at run time.

In dynamic typing, value can change from its first declarations type to another type at any time for example int to string, but in statically typing value cannot be changed from one type to another easily. You have to convert them.


## What static and dynamic binding is?

Binding refers to the association of names in program text to the storage locations to which they refer. In static binding, this association is predetermined at compile time. With dynamic binding, this association is not determined until run time.

Example:

If someone attempts to invoke a method like MyClass.foo(), a static binding system will verify at build time that there is a class called MyClass and that class has a method called foo. A dynamic binding system will wait until run time to see whether either exists.



## What is Interpreted language?. 

With a compiled language, the code you enter is reduced to a set of machine-specific instructions before being saved as an executable file — at compile time. With an Interpreted language, most of its implementations execute instructions directly and freely, without previously compiling a program into machine language instructions. Interpreted languages must be reduced to machine instructions.— at run time. You can write dynamically typed interpreted language. 




## What is OWASP?
- OWASP stands for the Open Web Application Security Project. It is an open community that focuses on improving the security of software applications, particularly web applications. OWASP provides resources and tools to help developers, security professionals, and organizations better understand and mitigate the risks associated with web application security.
- OWASP maintains a list of the top 10 web application security risks, which is updated regularly to reflect the latest threats and vulnerabilities. This list serves as a guide for developers and security professionals to help them prioritize and address the most critical security risks when developing or testing web applications.
- In addition to the top 10 list, OWASP provides a variety of resources and tools, including security guidelines, testing frameworks, and educational materials. The organization also hosts conferences and events around the world to promote the importance of web application security and share knowledge and best practices among the community.



## What is gRPC?

- gRPC is a way for different computer programs to communicate with each other, even if they are written in different programming languages or run on different computers. It's like a telephone that lets programs talk to each other, using a special language to understand each other's messages. gRPC is very fast and efficient, and it's used in many different types of applications that need to exchange information over a network.
- gRPC builds on top of traditional RPC frameworks by providing features such as:
    - Bi-directional streaming: Both the client and server can send and receive data at the same time, which allows for more efficient communication.
    - Multi-language support: gRPC supports multiple programming languages, including C++, Java, Python, and Go,JavaScrip, among others.
    - Code generation: Protocol Buffers enable code generation in multiple programming languages, which simplifies development and reduces the risk of errors.
    - Flow control: gRPC provides flow control mechanisms to prevent overwhelming the network and ensure that data is transferred efficiently.
    - Authentication and encryption: gRPC includes built-in support for authentication and encryption, which enhances security and privacy.
- gRPC is commonly used in microservices architectures, where small, independently deployable services communicate with each other over the network. It is also used in cloud-native applications, IoT devices, and other distributed systems that require efficient and reliable communication between different components.



## What is GraphQL?
- GraphQL is an open-source query language and runtime for APIs that was developed by Facebook. It provides a more efficient, powerful, and flexible alternative to RESTful APIs by enabling clients to specify exactly what data they need and receive only that data in response.
- With GraphQL, clients can make a single request to the server to fetch data from multiple resources, as opposed to RESTful APIs, where clients may need to make multiple requests to retrieve related data. The client sends a GraphQL query to the server, which processes the query and returns only the data that the client requested.
- Key features of GraphQL include:
    - Strong typing: GraphQL schemas define the types of data that can be queried, which enables type checking and reduces errors.
    - Hierarchical: GraphQL queries are hierarchical, which means that clients can specify complex data relationships and nested data structures.
    - Client-specified queries: The client specifies exactly what data it needs, which improves performance by reducing the amount of data sent over the network.
    - Language-agnostic: GraphQL is not tied to any specific programming language or database, which means it can be used with a variety of backend technologies.
    - Real-time subscriptions: GraphQL supports real-time subscriptions, which enables clients to receive data updates in real-time.
- GraphQL is commonly used in web and mobile applications that require a flexible and efficient way to retrieve data from servers. It has gained popularity in recent years, and many major companies, including Facebook, GitHub, and Shopify, have adopted it for their APIs





## How can we implement caching on frontend?
- Implementing caching on the frontend is a common technique to improve the performance of web applications by reducing the number of requests to the server. Here are some ways to implement caching on the frontend:
    - Browser caching: Browsers can cache static assets such as images, stylesheets, and JavaScript files, reducing the amount of time it takes to load pages. By setting the appropriate HTTP headers, developers can control how long these assets are cached and when they should be invalidated.
    - Service Worker caching: Service Workers are a client-side technology that enables web applications to cache data and assets on the user's device. This allows the application to load and run even when the user is offline or has a poor internet connection. Service Workers can cache content in a variety of ways, including network-first, cache-first, and stale-while-revalidate strategies.
    - In-memory caching: JavaScript frameworks such as React and Angular provide mechanisms for in-memory caching of components and application state. By storing frequently used data in memory, these frameworks can reduce the amount of time it takes to render components and improve the performance of the application.
    - Local Storage: Local Storage is a browser-based mechanism for storing data on the user's device. By storing frequently used data in Local Storage, web applications can reduce the number of requests to the server and improve the performance of the application.