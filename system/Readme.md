## How does the internet work?

- The internet is a global network of connected devices that communicate with each other using unique numerical identifiers called IP addresses. When a user enters a website address in their web browser, their device sends a request to a web server, which then sends the website content back to the user's device over the internet. The content is then displayed in the user's web browser. The process is facilitated by a variety of protocols and technologies.


## How do Browsers work?

- Web browsers are software applications that allow users to access and interact with web pages and other online resources on the internet. Here's a simplified overview of how web browsers work:
    - The user enters a website address or clicks on a link in the browser's address bar.
    - The browser sends a request to the web server associated with the website address, requesting the content associated with the website.
    - The web server receives the request and sends the website content back to the user's browser.
    - The browser receives the website content, which is typically in the form of HTML, CSS, and JavaScript files.
    - The browser interprets the HTML and CSS files to render the website content in the user's web browser. This includes displaying text, images, videos, and other multimedia content, as well as applying styles and layouts to the content.
    - he browser executes any JavaScript code embedded in the website, which allows for dynamic and interactive content such as animations, pop-ups, and form submissions.
    - The user can interact with the website by clicking links, filling out forms, and performing other actions, which are then sent back to the web server through the browser.
    - The web server processes the user's actions and sends back any new content or updates, which the browser renders and displays to the user.
- This process of sending and receiving website content and user actions is facilitated by a variety of protocols and technologies, including HTTP, TCP/IP, HTML, CSS, JavaScript, and others.


## What is HTTP protocol?

- HTTP stands for Hypertext Transfer Protocol, which is a communication protocol used for transmitting data over the internet. It is the foundation of data communication for the World Wide Web.
- HTTP is a client-server protocol, which means that requests are sent by clients, such as web browsers, to servers, which then respond with the requested data. The data is typically in the form of HTML, CSS, JavaScript, images, and other types of files.
- HTTP uses a request-response model, where clients send requests to servers, and servers respond with the requested data. Each HTTP request and response consists of a set of headers, which contain information about the request or response, and a message body, which contains the data being transmitted.


## What is TCP Protocol?

- TCP (Transmission Control Protocol) is a transport layer protocol that is used to establish and maintain a reliable, end-to-end connection between applications running on different hosts over the internet. It provides a reliable, ordered, and error-checked delivery of data between applications.
- TCP is a connection-oriented protocol, which means that before data is sent, a connection is established between the sender and receiver. This connection is managed by a three-way handshake process, in which the client sends a SYN (synchronize) message to the server, the server responds with a SYN-ACK (synchronize-acknowledge) message, and the client sends an ACK (acknowledge) message to confirm the connection.
- Once the connection is established, TCP ensures that data is transmitted in the correct order, without errors, and without loss of data. It does this by dividing the data into segments, adding a sequence number to each segment, and retransmitting any segments that are lost or corrupted during transmission.
- TCP also includes flow control and congestion control mechanisms to ensure that data is transmitted at an appropriate rate and that the network is not overloaded with traffic.
- CP is used by many internet applications, including web browsing, email, file transfer, and remote login. It is one of the most widely used protocols in the Internet Protocol (IP) suite and forms the basis of many higher-level protocols such as HTTP, FTP, and SMTP.



## What are HTTP headers?

- HTTP headers are additional pieces of information that are sent along with an HTTP request or response between a client and a server. They provide metadata about the request or response, such as the content type, encoding, cache control, and more.
- HTTP headers are divided into two types: request headers and response headers.
    - Request headers: These headers are sent by the client to the server as part of an HTTP request. They provide additional information about the request being made, such as the user agent, the method being used (GET, POST, etc.), and the content type of the request body.
    - Response headers: These headers are sent by the server to the client as part of an HTTP response. They provide additional information about the response being returned, such as the content type, the cache control directives, and the server software being used.
- Some common HTTP headers include:
    - Content-Type: Indicates the MIME type of the response body
    - Content-Length: Indicates the length of the response body in bytes
    - Cache-Control: Specifies how the response should be cached by the client or intermediate proxies
    - User-Agent: Identifies the client software (such as a web browser) making the request
    - Set-Cookie: Sets a cookie in the client's browser



## What are some HTTP response codes? what does it mean? 2xx, 3xx, 4xx, 5xx

- 2xx (Successful): These codes indicate that the request was successful and the server was able to return the requested resource. Some examples include:
    - 200 OK: The request was successful and the server has returned the requested data
    - 201 Created: The request was successful and a new resource was created on the server
    - 204 No Content: The request was successful but there is no content to send back

- 3xx (Redirection): These codes indicate that the client must take additional action to complete the request. Some examples include:   
    - 301 Moved Permanently: The requested resource has been permanently moved to a new location
    - 302 Found: The requested resource has been temporarily moved to a new location
    - 304 Not Modified: The requested resource has not been modified since the last time it was accessed

- 4xx (Client Error): These codes indicate that the request was unsuccessful due to an error on the client side. Some examples include:
    - 400 Bad Request: The server could not understand the request due to invalid syntax
    - 403 Forbidden: The client does not have permission to access the requested resource
    - 404 Not Found: The requested resource could not be found on the server

- 5xx (Server Error): These codes indicate that the request was unsuccessful due to an error on the server side. Some examples include:
    - 500 Internal Server Error: The server encountered an unexpected condition that prevented it from fulfilling the request
    - 502 Bad Gateway: The server received an invalid response from an upstream server
    - 503 Service Unavailable: The server is currently unable to handle the request due to maintenance or overload




## What does cache control on http response mean?

- Cache-Control is an HTTP response header that specifies how the client, proxy, or browser should handle caching of the web content. It can be used by the server to control how long a particular resource should be cached and whether or not it should be cached at all.
- The Cache-Control header can contain several directives, which control the caching behavior of the client, proxy, or browser. Some of the most common directives are:

    - max-age: specifies the maximum amount of time in seconds that the resource can be cached before it is considered stale and must be revalidated with the server.
    - no-cache: specifies that the client, proxy, or browser must revalidate the resource with the server before using it, even if it is in the cache.
    - no-store: specifies that the client, proxy, or browser must not store the resource in the cache.
    - must-revalidate: specifies that the client, proxy, or browser must revalidate the resource with the server before using it, even if it is in the cache and has not expired.



## What is polling?

- Polling is a computer networking technique used to continuously check for the availability of new data or information from a remote server or device. In this technique, a client sends requests to the server at regular intervals to check for updates or changes in the data.
- The client repeatedly sends a request to the server and waits for a response, even if there is no new data available. This approach is often used in situations where the server does not have the ability to push new data to the client, such as in a client-server architecture.
- For example, polling is commonly used in web applications to check for updates to web pages or feeds. In this case, the client sends a request to the server at regular intervals to check for any changes in the content of the web page or feed.
- Polling can be resource-intensive and may lead to increased network traffic and slower response times. To address this, other techniques such as long polling and server-sent events (SSE) have been developed to improve efficiency and reduce resource consumption.




## What is long polling?

- In this approach, the client sends a request to the server, but the server does not immediately respond with the current state of the requested resource. Instead, the server waits until new data is available or a timeout occurs before sending a response to the client.
- This technique allows the server to push new data to the client as soon as it becomes available, reducing the amount of unnecessary network traffic and improving response times. Long polling is often used in situations where the data is not updated frequently, but the client needs to be notified immediately when new data becomes available.
- For example, long polling is commonly used in chat applications or online gaming, where real-time updates are required. The client sends a request to the server to check for new messages or game updates. If there is no new data, the server waits for a specified period of time before responding. If new data becomes available during this time, the server immediately sends a response with the new data to the client.
- Long polling can be more efficient than traditional polling because it reduces the number of requests sent to the server and allows for real-time updates without the need for constant client requests. However, it can also be more complex to implement and may require additional server-side infrastructure.




## Explain briefly what happens when you hit a url? explain DNS lookup

- When you hit a URL (Uniform Resource Locator), your web browser sends a request to the server that hosts the website. The server responds by sending back the HTML, CSS, and JavaScript files that make up the webpage, which are then rendered by the browser.
- The process of requesting a webpage involves several steps, including:
    - DNS lookup: The first step in loading a webpage is translating the URL into an IP address that the browser can use to locate the server hosting the website. This process is called DNS (Domain Name System) lookup, and it involves querying a DNS server to resolve the domain name in the URL to an IP address.

    - HTTP request: Once the browser has resolved the IP address, it sends an HTTP (Hypertext Transfer Protocol) request to the server. This request includes information such as the type of request (e.g. GET, POST), the URL of the requested resource, and any additional headers or data.

    - Server processing: The server receives the HTTP request and processes it, using server-side technologies such as PHP, Node.js, or Ruby on Rails to generate a response.

    - HTTP response: The server sends an HTTP response back to the browser, which includes the requested resource (e.g. HTML, CSS, JavaScript files), as well as any additional headers or data.

    - Rendering: The browser receives the HTTP response and begins rendering the webpage. This involves parsing the HTML, applying the CSS styles, and executing any JavaScript code.

    - Display: Once the webpage has been rendered, the browser displays it to the user.



## What is a URLs full form? Explain what a url is and the four parts it consists of The protocol in use The hostname of the server The location of the file The arguments to the file

- URL stands for Uniform Resource Locator. It is a string of characters that provides a way to locate a resource on the internet. A URL typically consists of four parts:

- The protocol in use: The protocol is the method used to retrieve the resource. Common protocols include HTTP (Hypertext Transfer Protocol) and HTTPS (HTTP Secure) for webpages, FTP (File Transfer Protocol) for file downloads, and SMTP (Simple Mail Transfer Protocol) for email.

- The hostname of the server: This is the domain name or IP address of the server that hosts the resource. For example, the hostname for the Google homepage is "www.google.com".

- The location of the file: This is the path to the specific file or resource on the server. For example, the path to the Google homepage is "/".

- The arguments to the file: These are optional parameters that are passed to the server along with the request. They are typically used to provide additional information or context to the resource being requested. For example, a search query might be passed as an argument in a URL.




## What is clickjacking? How do you fix it?

- Clickjacking is a type of web attack in which an attacker tricks a user into clicking on a hidden or disguised link or button on a web page, often by overlaying the page with a transparent layer or iframe. This allows the attacker to perform actions on behalf of the user, such as posting messages or stealing sensitive information.
- To fix clickjacking, there are several measures that can be taken:
    - Frame busting: One common technique is to use frame-busting code to prevent a page from being displayed within an iframe. This code detects if the page is being displayed within an iframe and if so, redirects the browser to the original page, breaking the attacker's overlay.

    - X-Frame-Options header: The X-Frame-Options header is another solution that can be used to prevent a page from being displayed within an iframe. This header is set by the server and specifies whether a page can be displayed within an iframe or not.

    - Content Security Policy (CSP): CSP is a security standard that can be used to prevent clickjacking attacks by allowing a web page to specify which domains are allowed to embed the page in an iframe. If an attacker tries to embed the page in an iframe from a domain that is not specified, the browser will block it.

    - User education: Another important measure is to educate users about the dangers of clicking on links or buttons on unfamiliar or suspicious web pages, especially if they are asked to provide sensitive information.




## What are some performance metrics for your website?

- Page load time: This is the time it takes for a web page to fully load in the user's browser. A slow page load time can result in a poor user experience and negatively impact search engine rankings.

- Time to first byte (TTFB): This is the time it takes for the server to start sending data back to the browser after a request is made. A high TTFB can indicate server performance issues.

- Render time: This is the time it takes for the browser to display the content on the screen after receiving the HTML, CSS, and JavaScript files. A slow render time can result in a poor user experience.

- Number of requests: This is the total number of requests made by the browser to load a web page. Reducing the number of requests can improve page load time and overall performance.

- Page size: This is the size of the web page in bytes. Large page sizes can result in longer load times and negatively impact user experience.

- Time to interactive (TTI): This is the time it takes for a web page to become fully interactive, meaning that all the necessary content has loaded and the user can interact with the page. A slow TTI can negatively impact user experience and increase bounce rates.

- Bounce rate: This is the percentage of users who leave the website after viewing only one page. A high bounce rate can indicate poor user experience, which may be due to slow page load times, poor content, or other issues.

In summary, there are several performance metrics that can be used to measure the speed and efficiency of a website, including page load time, time to first byte, render time, number of requests, page size, time to interactive, and bounce rate. Monitoring and optimizing these metrics can help improve the user experience and overall performance of a website.



## What do CDN or Content Delivery Networks do? When do you need a CDN?

- A CDN (Content Delivery Network) is a network of servers located around the world that are designed to deliver content, such as images, videos, and other static files, to users quickly and efficiently. When a user requests content from a website, the CDN will serve the content from the server that is closest to the user, reducing the distance the content has to travel and improving the website's performance and speed.
- Here are some situations where a CDN may be necessary:
    - High traffic websites
    - Global audience
    - Large file sizes
    - Security




## What is the difference between Client Side Renderring and Server Side Renderring?

- Client-side rendering involves sending a minimal HTML file to the client's web browser, which then loads the page and any required assets (such as JavaScript, CSS, and images) and renders the page on the client's device. This approach puts more of the burden of rendering on the client, which can result in faster page loads and a more responsive user interface. However, it can also be less SEO-friendly and may result in slower initial rendering of the page, particularly on slower devices or networks.
- Server-side rendering involves rendering the page on the server and then sending the fully rendered HTML file to the client's browser. This approach puts more of the burden on the server, which can result in slower page loads and a less responsive user interface. However, it can also be more SEO-friendly and can result in faster initial rendering of the page, particularly on slower devices or networks.



## What is Progressive Renderring

- Progressive rendering is a technique to show the most important parts of a web page to the user first, even before the entire page has loaded, in order to provide a faster and better user experience. This involves prioritizing the loading of critical content and deferring the loading of non-critical content until later, and can also include lazy loading and code splitting.



## What is the difference between Preloading and Prefetching resources? 

- Preloading refers to loading resources that will be used on the current page, such as images or scripts, before they are actually needed. This ensures that they are ready and available when they are needed, which can reduce page load times and improve the user experience.
- Prefetching, on the other hand, involves loading resources that will be needed on subsequent pages, such as links or images, in advance. This is done in the background while the user is still browsing the current page, so that the resources will be available and ready to be displayed quickly when the user navigates to the next page.



## What are service workers?

- Service workers are scripts that run in the background of a web application or website and are designed to improve the performance and offline functionality of the site. They can intercept network requests and cache resources such as images and JavaScript files, which can then be served quickly and efficiently from the cache instead of being downloaded over the network every time the site is accessed. This can lead to faster load times and a better user experience, especially on slower connections.
- Service workers can also provide offline functionality by allowing a website or application to work even when there is no network connection. When the user goes offline, the service worker can use the cached resources to continue serving the site or application, and then sync any changes with the server once the network connection is restored.
- Overall, service workers are a powerful tool for improving the performance and offline functionality of web applications and websites, and are an essential part of modern web development.


## What is a stateless backend?

- A stateless backend is a server-side application or service that does not store any state or session information between requests. In other words, each request to the backend is treated as an independent transaction, and the backend does not maintain any knowledge of previous requests.
- Instead of storing state information, a stateless backend relies on the client to provide any necessary context or state information with each request. This can be achieved using various techniques such as passing parameters in the URL, using cookies or tokens to store information in the client's browser, or using stateless authentication mechanisms such as JSON Web Tokens (JWTs).
- Stateless backends are often used in modern web applications and microservices architectures because they can be more scalable, resilient, and easier to maintain than stateful backends. Stateless backends can also be more easily distributed across multiple servers or instances, and can support load balancing and failover without requiring complex synchronization or data replication mechanisms.



## What is the client server model?

- In the client-server model, the client sends requests to the server, which processes the request and sends a response back to the client. The server may be responsible for performing complex computations or database operations, managing shared resources such as files or printers, or providing access to web applications or services.
- The client-server model is widely used in various industries, including web development, gaming, finance, and healthcare. It enables scalable, flexible, and secure distribution of resources and services across multiple clients, allowing organizations to improve efficiency, reduce costs, and enhance the user experience.
- The client-server model is a computing architecture in which a client machine requests and receives resources or services from a server machine. The client is typically a user-facing device such as a personal computer, smartphone, or tablet, while the server is a powerful computer or cluster of computers that provides centralized resources or services to clients over a network or the Internet.



##  What is HTTP vs HTTPS?

- HTTP (Hypertext Transfer Protocol) and HTTPS (HTTP Secure) are both protocols used for transferring data between a client (such as a web browser) and a server (such as a web server).
- HTTP is the basic protocol used by web browsers to request and receive web pages, but it's not secure because the data exchanged between the client and the server is not encrypted. HTTPS, on the other hand, adds an extra layer of security through the use of encryption, which protects the data exchanged between the client and the server from being intercepted by third parties. HTTPS is recommended for websites that deal with sensitive information like passwords or financial data, as it provides an important layer of protection against various cyber attacks.




## What is throughput?

- Throughput refers to the amount of data or information that can be processed or transmitted in a given amount of time. It is often used as a measure of the performance of computer systems, networks, or other communication channels.
- For example, in computer networks, throughput refers to the amount of data that can be transmitted over the network in a given time period, usually measured in bits per second (bps) or bytes per second (Bps). The higher the throughput, the more data can be transmitted in a given time period, and the faster the network is considered to be.
- Similarly, in storage systems, throughput refers to the rate at which data can be read from or written to a storage device, such as a hard disk or solid-state drive (SSD). The higher the throughput, the faster data can be accessed or transferred, and the better the performance of the storage system.
- Throughput can also be affected by various factors, such as the processing power of the system, the bandwidth of the network, the amount of data being transmitted or processed, and the efficiency of the underlying hardware and software components. Therefore, measuring and optimizing throughput is an important task in many areas of computer science and engineering.


## What are microservices?

- Microservices are a way of building software systems by breaking them down into smaller, independent services that can be developed, deployed, and scaled independently of each other. Each service performs a specific task and communicates with other services through well-defined interfaces. The goal is to create a more flexible, scalable, and maintainable system by breaking it down into smaller, more manageable pieces. This approach allows teams to work on individual services without affecting the rest of the system and enables faster development, deployment, and updates.
- The goal of microservices is to improve the scalability, flexibility, and maintainability of complex software systems. By breaking down a large application into smaller, loosely coupled services, teams can work on individual services without affecting the rest of the system. This allows for faster development and deployment of new features and updates, as well as easier maintenance and scaling of the system as a whole.
- Microservices are often implemented using containerization technologies such as Docker, which allow for individual services to be packaged and deployed as independent units. This enables services to be deployed and scaled independently of each other, making it easier to manage large and complex software systems.




##  What is testing?

- Testing is the process of evaluating a software product or system to determine whether it meets its specified requirements and works as intended. The purpose of testing is to identify defects or errors in the software so that they can be fixed before the software is released to end-users.
- There are many different types of testing, including functional testing, performance testing, security testing, and more. The type of testing that is performed depends on the specific requirements of the software and the goals of the testing process.
- Testing can be performed at various stages of the software development lifecycle, including unit testing, integration testing, system testing, and acceptance testing. Each stage of testing builds upon the previous stage and helps to ensure that the software is working correctly and meets its requirements.
- There are also many different testing techniques and tools that can be used to automate and streamline the testing process. For example, automated testing tools can be used to run a suite of tests automatically, saving time and effort compared to manual testing. Additionally, techniques like continuous integration and continuous delivery can be used to automate the testing and deployment of software updates, making the testing process more efficient and effective.



## What is unit testing?

- Unit testing is a type of testing in software development where individual units or components of the software are tested in isolation from the rest of the system. The purpose of unit testing is to ensure that each unit of code performs as expected and meets its specifications.
- In unit testing, a unit of code is typically a function or a method. The unit is tested by providing it with inputs and verifying that the output it produces matches the expected result. Unit tests are typically automated and run as part of a continuous integration and delivery process.
- Unit testing helps to identify defects or errors in the code early in the software development lifecycle, when they are easier and cheaper to fix. By testing each unit of code in isolation, developers can quickly identify and fix issues before they impact the rest of the system.
- Unit testing can also improve the quality of the software by ensuring that each unit of code meets its specifications and performs as intended. By testing each unit of code in isolation, developers can have greater confidence that the code will work correctly when it is integrated with the rest of the system.



## What is functional testing?

- Functional testing helps to ensure that the system meets its functional requirements and performs as intended. By testing the system against different scenarios and use cases, testers can identify defects or errors in the system and ensure that they are corrected before the system is released to end-users. Functional testing is an important part of software development and is typically performed throughout the software development lifecycle.
- Functional testing is typically black-box testing, meaning that the tester is not concerned with the internal workings of the system, but rather with the input and output of the system. Test cases are designed to cover different scenarios and use cases, and the tester verifies that the system produces the expected output for each test case.
- Functional testing can include a range of testing techniques, including:
 - 1)Smoke testing: A basic test that ensures that the system is functional and can perform the most critical functions.
  - 2)Integration testing: Testing the interfaces and interactions between different modules or components of the system.
 - 3)System testing: Testing the system as a whole, including all its components, to verify that it meets its functional requirements.
 - 4)Acceptance testing: Testing the system against the business requirements and specifications to ensure that it meets the needs of the end-users.





 ## What is CAP theorem?

- The CAP theorem, also known as Brewer's theorem, is a concept in distributed computing that states that it is impossible for a distributed system to simultaneously provide all three of the following guarantees:
   - **Consistency**: All nodes in the system see the same data at the same time.
   - **Availability**: Every request receives a response, without guarantee that it contains the most recent version of the information.
   - **Partition tolerance**: The system continues to function even when network partitions occur, meaning that communication between nodes is lost or delayed.

- According to the CAP theorem, a distributed system can only satisfy two of these guarantees at any given time. In other words, when a network partition occurs, the system administrator must choose whether to prioritize consistency or availability.
- The CAP theorem is often used as a framework for designing distributed systems, and it highlights the trade-offs that must be made when building such systems. For example, a system that prioritizes consistency over availability may use a locking mechanism to ensure that all nodes see the same data, but this may lead to slower response times or even system failure if a node fails to respond. On the other hand, a system that prioritizes availability over consistency may return stale or inconsistent data, but it can continue to function even during network partitions.
- It's important to note that the CAP theorem applies specifically to distributed systems, and not to all types of systems. In addition, some systems, such as those that use eventual consistency, may be able to provide a reasonable balance of all three guarantees. However, the CAP theorem remains an important concept in distributed computing and a useful tool for understanding the trade-offs involved in designing and implementing distributed systems.




## What is PACELC?

- PACELC is a theorem related to distributed computing that explains the trade-offs between consistency, availability, and partition tolerance. These three concepts are fundamental to designing and operating distributed systems, such as databases or cloud computing services.
- According to the PACELC theorem, in the presence of a network partition (P), a distributed system must choose between either Consistency (C) or Availability (A) or to sacrifice both to ensure Partition Tolerance (E).
    - If the system chooses to prioritize Consistency over Availability, it means that all nodes will have the same view of the data at all times, even in the presence of updates, but during a network partition, the system may be unavailable or only partially available. This is known as the CP (Consistency-Partition Tolerance) model.
    - If the system chooses to prioritize Availability over Consistency, it means that all nodes can access the data at all times, but different nodes may have different views of the data, leading to eventual consistency. During a network partition, the system remains available but with a risk of inconsistent data. This is known as the AP (Availability-Partition Tolerance) model.
    - If the system chooses to prioritize Partition Tolerance over both Consistency and Availability, it means that the system can still operate during a network partition, but the data may be inconsistent and the system may experience both latency and unavailability. This is known as the EP (Eventual consistency-Partition Tolerance) model.
- the PACELC theorem provides a framework for understanding the trade-offs and design decisions involved in building distributed systems, particularly in situations where network partitions are likely to occur.



## What is Normalization / Denormalization?

- Normalization and denormalization are techniques used in database design to optimize the structure of a database for performance, scalability, and data integrity.
- Normalization is the process of organizing data in a database so that it is structured in a logical and consistent way. This involves breaking down large tables into smaller, more specialized tables, and creating relationships between them using foreign keys. By doing this, data redundancy is reduced, and data integrity is improved.
- Denormalization, on the other hand, is the process of intentionally introducing redundancy into a database to improve performance. This involves adding duplicate data to a table, which can help to reduce the need for joins between tables, and speed up query performance. However, denormalization can also increase the risk of data inconsistency and can make updates to the database more complex.
-  normalization is about reducing redundancy and improving consistency, while denormalization is about improving performance by introducing redundancy. Both techniques have their own advantages and disadvantages, and their use depends on the specific requirements and characteristics of the database and the application that uses it.




## What is Entity Relationship Model? ( ER Model )

- The Entity-Relationship (ER) model is a conceptual data model used in database design to represent the relationships between entities in a database. It helps to identify the entities, attributes, and relationships between entities, and provides a graphical representation of the database structure.
- In an ER model, an entity represents a real-world object or concept, such as a person, place, or thing. Each entity has one or more attributes, which are characteristics or properties of the entity, such as name, age, or address. Relationships between entities are represented by lines connecting them, and can be of different types, such as one-to-one, one-to-many, or many-to-many.
- The ER model is useful for visualizing the structure of a database and understanding how different entities are related to each other. It can also help to identify potential problems with the database design, such as redundancy or inconsistency. The model can be used as a blueprint for implementing a database, and can help to guide the development process by providing a clear understanding of the data structure and relationships.




## What is a CDN?

- A CDN, or Content Delivery Network, is a distributed network of servers located in different geographic regions around the world. The purpose of a CDN is to deliver content, such as images, videos, stylesheets, and JavaScript files, to users from the server that is closest to them. This reduces the time it takes for the content to be delivered, which in turn improves the performance and user experience of web applications.
- When a user requests content from a website that uses a CDN, the request is routed to the closest server in the CDN. The server then delivers the content to the user, typically over a high-speed network connection. This reduces the distance that the content has to travel and improves the response time, which can have a significant impact on the user experience.
- In addition to improving performance, CDNs can also improve the scalability and availability of web applications. By distributing content across multiple servers, CDNs can handle large volumes of traffic without overloading individual servers. They can also provide redundancy and failover capabilities, ensuring that content is still delivered even if one or more servers go offline.
- CDNs are commonly used by large websites and web applications that serve a global audience, as well as by e-commerce sites and media companies that need to deliver large amounts of content to users. Some popular CDN providers include Cloudflare, Akamai, Amazon CloudFront, and Google Cloud CDN.




##  What is DNS?

- DNS stands for Domain Name System, and it is a system used to translate human-readable domain names, such as www.example.com, into IP addresses, which are the numerical addresses used by computers to identify each other on the internet.
- When you enter a domain name into your web browser, your computer sends a DNS query to a DNS server, which is responsible for translating the domain name into an IP address. The DNS server checks its cache to see if it already has a record of the IP address for the domain name. If it doesn't, it sends a query to another DNS server, and this process continues until a DNS server is found that has the IP address for the domain name.
- DNS is a critical component of the internet infrastructure, as it enables users to access websites and other online resources using human-readable domain names rather than having to remember numerical IP addresses. Without DNS, users would need to memorize numerical IP addresses for every website they wanted to visit, which would be impractical and inconvenient.



## What is availability?

- In computing, availability refers to the ability of a system or application to be operational and accessible when it is needed by its users. It is a measure of the reliability and uptime of a system, and is typically expressed as a percentage of time that the system is available over a given period.
- Availability can be affected by various factors, including hardware and software failures, network outages, power disruptions, and maintenance activities. A high availability indicates that a system or application is able to provide uninterrupted service to its users, while a low availability indicates that it may experience frequent outages or downtime.
- Achieving high availability is important in many applications and systems, particularly those that involve critical operations, such as financial transactions, healthcare services, or emergency response systems. Ensuring high availability typically involves implementing redundancy and failover mechanisms, monitoring and alerting tools, and performing regular maintenance and updates to prevent downtime and minimize the impact of any failures.




## What is latency?

- In computing, latency refers to the amount of time it takes for a data packet or signal to travel from one point to another in a system or network. It is a measure of the delay or lag between the sender and receiver of the data, and is typically expressed in units of time, such as milliseconds (ms).
- Latency can be affected by various factors, including network congestion, distance between devices, processing time, and transmission medium. A high latency can result in slow response times, delays in data transmission, and reduced system performance, while a low latency indicates that data is being transmitted quickly and efficiently.
- Latency is an important metric in many applications and systems, particularly those that require real-time or interactive responses, such as online gaming, video streaming, or virtual meetings. Reducing latency typically involves optimizing network infrastructure, reducing data packet sizes, and using caching and compression techniques to speed up data transmission.




## What is rate-limiting?

- In computing, rate-limiting refers to the practice of limiting the number of requests or actions that a user or application can make within a given period of time. It is a way to prevent abuse or overloading of a system or network, and to ensure fair and efficient use of resources.
- Rate-limiting can be implemented at various levels in a system or network, including at the application level, the server level, or the network level. It typically involves setting thresholds for the number of requests or actions that can be made within a certain time period, and blocking or throttling users or applications that exceed those limits.
- Rate-limiting is commonly used in web applications, APIs, and network infrastructure to prevent spamming, brute-force attacks, and other forms of abuse. It can also be used to ensure that critical systems and resources are not overwhelmed by excessive traffic or requests. Properly configuring and tuning rate-limiting policies is an important aspect of ensuring the security and availability of systems and networks.




## What are the different ways to do rate limits?

- **Token Bucket**: In this method, tokens are added to a "bucket" at a constant rate, and each request or action consumes a certain number of tokens. If the bucket is empty, requests are blocked until more tokens are added. This approach allows bursts of traffic to be handled, as long as the overall rate does not exceed the token rate.
- **Leaky Bucket**: Similar to the token bucket method, in this approach a "leaky bucket" accumulates requests over time, and releases them at a fixed rate. If requests are added faster than they are released, the bucket eventually overflows, and requests are blocked.
- **Fixed Window**: In this method, a fixed window of time (e.g., one minute) is used to count the number of requests or actions. If the limit for that window is exceeded, requests are blocked until the next window begins.
- **Rolling Window**: This method is similar to the fixed window approach, but instead of using a fixed time window, a rolling window of time is used to count requests over a certain period. For example, if the rolling window is set to 5 minutes, the limit is checked over the last 5 minutes, and requests are blocked if the limit is exceeded.
- **Adaptive Limits**: In this method, the rate limit is adjusted dynamically based on system or application conditions. For example, the limit may be increased during periods of low load, and decreased during periods of high load.





## What is a load balancer?

- A load balancer is a device or software component that distributes incoming network traffic across multiple servers or resources in a way that optimizes performance, increases availability, and ensures scalability.
- Load balancers work by sitting in front of a cluster of servers, and directing traffic to the most available or least loaded server at any given time. This helps to distribute the workload evenly across the servers, preventing any single server from becoming overwhelmed and causing performance problems or downtime.
- Load balancing can be implemented at various levels in a system or application architecture, including at the network level, the transport level, or the application level. Depending on the specific requirements and constraints of a system, load balancing may be achieved through hardware-based load balancers, software-based load balancers, or cloud-based load balancers.
- There are several algorithms that can be used by load balancers to distribute traffic among servers or resources. for example
  - Round Robin: This algorithm distributes traffic evenly among servers in a cyclical manner, without considering the current server load or capacity.





## Describe how you design an API?

- Designing an API requires careful planning and consideration of the needs and requirements of both the users and the system. Here are some steps that can be taken to design an API:
    - Identify the goals and requirements of the API
    - Choose an appropriate architecture: There are several architectural styles that can be used to design an API, such as REST, RPC, GraphQL, and SOAP
    - Define the API endpoints
    - Determine the request and response formats
    - Decide on authentication and authorization
    - Implement rate limiting and throttling
    - Document the API
- designing an API requires a balance between simplicity, flexibility, and functionality. The API should be easy to use, but also powerful and extensible enough to meet the needs of a wide range of users and systems.





## What is a horizontal and vertical scaling?

- **Horizontal scaling**: This involves adding more machines or instances to the existing system, thereby distributing the load across multiple servers. In this approach, each machine or instance is typically identical, and requests can be routed to any available machine based on the load balancing algorithm. Horizontal scaling is often used to improve the availability and reliability of a system, as well as to increase its capacity to handle more traffic.
    - Horizontal scaling means adding more servers to the system to handle more traffic or requests. Think of it as adding more waiters to a restaurant to serve more customers. Each waiter can handle a limited number of tables, so by adding more waiters, the restaurant can serve more customers.
- **Vertical scaling**: This involves adding more resources, such as CPU, memory, or storage, to a single machine or instance in the existing system. This approach is often used to improve the performance or capacity of a specific machine or instance, rather than to distribute the load across multiple machines. Vertical scaling can be more limited in terms of scalability, as there are practical limits to how much resources can be added to a single machine.
    - vertical scaling means increasing the resources, such as CPU, memory, or storage, of an existing server to handle more traffic or requests. Think of it as giving a waiter a bigger tray to carry more food and drinks to serve more customers. However, there is a limit to how much a waiter can carry, just as there is a limit to how much resources a server can handle.

- horizontal scaling adds more servers to handle more traffic, while vertical scaling adds more resources to an existing server to handle more traffic. Both approaches can be used together to achieve the desired level of scalability and performance for a given system or application.






## How do you build a system which is reliable?

- Building a reliable system involves designing and implementing strategies that ensure the system can handle errors, failures, and unexpected events while continuing to operate effectively. Here are some key principles to keep in mind when building a reliable system:
    - Design for fault tolerance: Assume that things will fail, and plan accordingly. Design your system with redundancy, backups, and failover mechanisms to minimize the impact of failures.
    - Monitor your system: Keep track of your system's performance and health using monitoring tools and metrics. This will help you identify potential issues and take action before they become serious problems.
    - Automate as much as possible: Automate routine tasks such as backups, deployment, and testing to reduce the risk of human error and ensure consistency.
    - Test thoroughly: Test your system thoroughly to ensure that it can handle expected and unexpected scenarios, including peak loads and failures.
    - Use modular and scalable architecture: Design your system in a modular and scalable way to make it easier to maintain and scale as your business grows.
    - Implement security best practices: Ensure that your system is secure by implementing security best practices, such as using encryption, access controls, and threat monitoring.
    - Continuously improve: Continuously improve your system by learning from past failures and successes, and implementing new best practices and technologies as they emerge.
- By following these principles, you can build a reliable system that can handle unexpected events, provide high availability, and meet the needs of your users.




## what are webhooks?

- E-commerce apps need to communicate with payment systems, payment systems need to communicate with banking systems, banking systems need to communicate with customer accounts...The ability of independent online systems to communicate with one another and share data is the core of what makes online services valuable today.
- A webhook is an HTTP request, triggered by an event in a source system and sent to a destination system, often with a payload of data. Webhooks are automated, in other words they are automatically sent out when their event is fired in the source system.
- This provides a way for one system (the source) to "speak" (HTTP request) to another system (the destination) when an event occurs, and share information (request payload) about the event that occurred.


## What are webhooks used for?

- The purpose of webhooks is to facilitate real-time communication and data exchange between two web applications or services. 
- Webhooks only enable one-way communication from the sender to the receiver, 
- for example:
    - The streaming service wants to send you an email at the beginning of each month when it charges your credit card.
    - The streaming service can subscribe to the banking service (the source) to send a webhook when a credit card is charged (event trigger) to their emailing service (the destination). When the event is processed, it will send you a notification each time your card is charged.
    - The banking system webhooks will include information about the charge (event data), which the emailing service uses to construct a suitable message for you, the customer.





## how webhook work?

- Webhooks are synchronous.
- Webhooks are most common in SaaS platforms like GitHub, Shopify, Stripe, Twilio, and Slack because they support different types of events based on the activities that happen within them.
    **A SaaS platform is a software platform that allows businesses to subscribe to and use cloud-based applications over the internet. Instead of having to install and manage software on their own servers, users can access the platform via a web browser and pay for the service on a subscription basis.**

- To receive webhook requests, you have to register for one or more of the events (also known as topics) for which the platform offers a webhook. A webhook request will be sent to a destination endpoint (URL). It can be your application, register the URL as the Webhook URL for that event.
- Once the webhook registration for an event is complete, you will receive webhook requests at the destination URL you provided each time the event occurs.



## Differences between webhooks and pub/sub

- In a pub/sub system, message sources are decoupled from message consumers while in webhooks, the message producer is fully aware of the location of the consumer through the webhook URL.
- Webhooks are a direct form of communication between the producer and consumer while pub/sub is a middle-man framework that routes messages from publishers to subscribers. The communication setup in a webhook is one-to-one, i.e. one producer to one consumer, while in a pub/sub system you can have many producers sending messages to multiple consumers.




## When to use pub/sub

- Use a pub/sub system when you have multiple consumers interested in the same message or more than one message producer.
- Also, use a pub/sub system when you want to asynchronously process messages. Webhooks are synchronous.
- An example of a situation where a pub/sub system is appropriate is in an e-commerce site. When a customer makes a purchase, you need to mail an invoice to the customer, send information to the delivery department, and enter the sale record in your CRM. Let's imagine that a mailing service, delivery service, and records service handle these responsibilities respectively.
- That is three systems interested in the same message. You can publish this message to a pub/sub system, which will then route it to these three subscribed services.



## What is Docker? Why do we use it?

- Docker is a platform that enables developers to build, package, and deploy applications as self-contained units called containers. Each container includes everything needed to run the application, including the code, system tools, libraries, and settings.
- Docker is used for several reasons, including:
    - Portability: Docker containers can run on any platform that supports Docker, which means that they can be easily moved between development, testing, and production environments without any changes to the application code.
    - Consistency: Docker ensures that the application runs the same way in any environment. This eliminates the common "it works on my machine" problem that often occurs when developers work in different environments.
    - Isolation: Each Docker container runs in a separate environment, which means that one container cannot interfere with another. This provides greater security and stability for applications.
    - Efficiency: Docker containers are lightweight and use fewer resources than traditional virtual machines. This means that more containers can be run on the same physical machine, leading to greater efficiency and cost savings.


## How to reduce api request
- Reducing API requests can help improve the performance, efficiency, and cost-effectiveness of your application. Here are several techniques you can use to reduce the number of API requests:

1. **Batching and Aggregating:**
   - Instead of making multiple individual requests, combine related requests into a single batch request.
   - Aggregate data from different API endpoints into a single response, reducing the number of round trips.
   - Use bulk operations where available to process multiple items in a single request.

2. **Caching and Cache-Control Headers:**
   - Implement caching mechanisms on the client side or server side to store API responses and serve them without making additional requests.
   - Utilize cache-control headers, such as `Cache-Control` and `Expires`, to specify caching rules for responses.
   - Leverage content delivery networks (CDNs) to cache and serve static API responses closer to end-users.

3. **Pagination and Partial Responses:**
   - Implement pagination techniques to retrieve a specific subset of data rather than fetching the entire dataset in a single request.
   - Use query parameters like `page` and `limit` to control the number of items returned per request.
   - Support partial responses by allowing clients to specify which fields they actually need, reducing the data transferred.

4. **Webhooks and Event-Driven Architecture:**
   - Implement webhooks to push data or notifications to clients instead of relying on them to continuously poll for updates.
   - Adopt an event-driven architecture where clients subscribe to relevant events and receive updates when changes occur.

5. **Data Denormalization and Pre-computation:**
   - Consider denormalizing or pre-computing data on the server-side to reduce the need for frequent API requests.
   - Store frequently accessed or computed data in a format that can be readily served without additional processing.

6. **Local Storage and Caching on the Client-Side:**
   - Leverage local storage or client-side caching mechanisms to store data temporarily on the client-side.
   - Retrieve data from local storage when needed instead of making API requests for the same data.

7. **Smart Synchronization and Differential Updates:**
   - Implement synchronization mechanisms that only update or fetch data that has changed since the last request.
   - Utilize techniques like ETags, timestamps, or versioning to determine if data has been modified and needs to be fetched.

8. **Optimized Data Structures and Algorithms:**
   - Optimize the way data is stored and retrieved to minimize the need for excessive API requests.
   - Utilize efficient data structures and algorithms to process and transform data on the client or server-side.

9. **Data Prefetching and Preloading:**
   - Anticipate user actions and prefetch relevant data in advance to reduce the need for on-demand API requests.
   - Preload data in the background based on user context or navigation patterns.

Remember that reducing API requests should be done thoughtfully, considering the specific requirements and constraints of your application. It's important to strike a balance between reducing requests and ensuring data consistency, freshness, and the overall user experience.

## difference between software design and software architecture

- Software design and software architecture are related but distinct concepts in the field of software development. While they both deal with the structure and organization of software systems, they focus on different aspects and have different scopes. Here's an explanation of the key differences between software design and software architecture:

1. Scope and Abstraction Level:
   - Software Design: Software design primarily focuses on the detailed design decisions and specifications of individual components or modules within a software system. It deals with lower-level design choices, such as algorithms, data structures, and the internal workings of modules.
   - Software Architecture: Software architecture, on the other hand, has a broader scope and deals with the overall structure and organization of the entire software system. It defines the high-level components, their interactions, and the system's overall behavior and properties.

2. Granularity:
   - Software Design: Software design is concerned with the design of individual components or modules within a system. It emphasizes the internal structure, interfaces, and responsibilities of these components, ensuring that they meet functional and non-functional requirements.
   - Software Architecture: Software architecture addresses the larger-scale organization of components and their interactions within the system. It defines the relationships and dependencies between different subsystems and how they collaborate to achieve the system's goals.

3. Time Perspective:
   - Software Design: Software design is typically more concerned with immediate development concerns. It focuses on translating high-level requirements and specifications into detailed design decisions, considering factors like maintainability, reusability, and code-level optimizations.
   - Software Architecture: Software architecture takes a more long-term view. It involves making strategic decisions that affect the system's overall structure, scalability, performance, and evolution over time. Architecture choices can have a significant impact on the system's future flexibility and ability to accommodate change.

4. Stakeholders:
   - Software Design: Software design primarily caters to the needs of developers and programmers who are responsible for implementing the system. It focuses on providing clear specifications and guidelines to facilitate the coding and testing process.
   - Software Architecture: Software architecture addresses the concerns of various stakeholders, including developers, project managers, system administrators, and end-users. It ensures that the system's structure aligns with the business goals, user requirements, and technical constraints.

In summary, while software design deals with the detailed design of individual components, software architecture focuses on the higher-level organization and structure of the entire system. Software design is more granular and concerned with immediate development concerns, while software architecture takes a broader view and focuses on long-term strategic decisions.

