## Explain in brief what is node js?

- Node.js is an open-source, cross-platform, server-side runtime environment built on the V8 JavaScript engine. It allows developers to use JavaScript on the server-side to build high-performance, scalable, and event-driven applications.
- Node.js uses an event-driven, non-blocking I/O model that makes it highly efficient and suitable for building applications that handle a large number of simultaneous connections. It can be used for a wide range of applications, from small command-line tools to large-scale web applications.
- One of the main advantages of Node.js is its rich ecosystem of third-party modules, which can be easily installed and used in Node.js applications. It also has a built-in package manager called npm, which makes it easy to manage dependencies and share code between projects.
- Node.js has become a popular choice for building real-time applications such as chat applications, real-time collaboration tools, and gaming applications, as well as APIs, microservices, and serverless applications.


## what is V8 JavaScript engine

- The V8 JavaScript engine is an open-source JavaScript engine developed by Google. It is used to run JavaScript code outside of a web browser, for example, in server-side environments like Node.js.
- The engine is written in C++, and its main purpose is to translate JavaScript code into machine code that can be executed by the computer's processor. This process is called Just-In-Time (JIT) compilation and it makes JavaScript code run much faster than it would with interpreted execution.
- In addition to its speed, V8 is known for its efficient memory management, which allows it to handle large amounts of data without slowing down. It also supports many of the latest JavaScript features and is updated regularly to keep up with new language specifications.



## How is node js non-blocking?

-Node.js uses an event-driven, asynchronous I/O model, which allows it to handle multiple tasks simultaneously without blocking the main thread of execution. When a task that requires I/O is encountered, Node.js delegates the task to a background thread and continues executing other code. When the I/O operation completes, Node.js triggers a callback function to handle the result, while the main thread of execution continues processing other code. This non-blocking I/O model makes Node.js highly efficient and well-suited for building scalable, real-time applications.
- For example, imagine a Node.js application that needs to read a file from disk and then send it over the network. With a blocking I/O model, the application would have to wait for the file to be read before it could start sending the data over the network. However, with Node.js' non-blocking model, the application can start reading the file and then immediately start sending the data over the network, without waiting for the file to be fully read.



## What is throughput?

- Throughput is a measure of the amount of work that can be processed by a system within a given time period. It is usually expressed in terms of units of work per unit of time, such as requests per second, transactions per second, or data transfer rate in 
- For example, in a web server, throughput could be measured in requests per second, which is the number of HTTP requests the server can handle in a given time period. In a database system, throughput could be measured in transactions per second, which is the number of database transactions the system can handle in a given time period.
- Throughput can be influenced by various factors, such as hardware resources, network bandwidth, software design, and optimization techniques. In order to improve throughput, system designers and developers may need to optimize various components of the system, such as the database schema, network architecture, or application code.


## How is Node js having high IO throughput?

- Node.js is designed to have high I/O throughput, mainly because of its non-blocking, event-driven architecture. This architecture allows Node.js to handle a large number of concurrent connections and I/O operations without being blocked by slow I/O operations.
- When a Node.js application needs to perform an I/O operation, it delegates the task to a background thread and continues processing other requests. When the I/O operation is completed, Node.js triggers a callback function to handle the result, allowing the application to continue processing other requests without waiting for the I/O operation to complete.
- This non-blocking I/O model, combined with Node.js' efficient event loop and asynchronous I/O APIs, enables Node.js to handle high levels of concurrency and I/O throughput. For example, Node.js can handle thousands of concurrent connections in real-time web applications or perform high-speed I/O operations in streaming applications without blocking or slowing down.
- Additionally, Node.js provides various tools and modules for optimizing I/O performance, such as the cluster module, which enables applications to take advantage of multiple CPU cores to process requests in parallel. There are also various community-maintained libraries and tools, such as the Node.js built-in "stream" module, which provide optimized and efficient ways to handle I/O operations in Node.js applications.


## What are CPU intensive tasks?

- CPU intensive tasks are tasks that require a significant amount of processing power from the CPU. These tasks typically involve complex calculations, data manipulation, or computational algorithms that require the CPU to perform multiple operations to complete the task.
- Some examples of CPU intensive tasks include:
    - Video encoding/decoding: Converting a video file from one format to another or decoding a video stream in real-time requires significant computational power.
    - Image processing: Editing, resizing, or filtering high-resolution images can be very CPU intensive, especially for large images.
    - Simulation and modeling: Computational simulations and modeling of complex systems, such as weather forecasting, scientific simulations, or financial analysis, require high amounts of processing power.
    - Data analysis: Analyzing large datasets or running complex machine learning algorithms can be very CPU intensive.
    - Cryptography: Encryption and decryption of data require complex mathematical operations that can be very CPU intensive.


## How can you end up blocking your main thread in node.js?

- The main thread in Node.js is responsible for executing the application's JavaScript code. If the main thread becomes blocked, it means that it is unable to execute new JavaScript code, which can cause the application to become unresponsive or slow.
- Here are some ways that the main thread in Node.js can become blocked:
    - Long-running synchronous operations: If a function performs a long-running synchronous operation, such as a blocking I/O operation or a heavy computation, the main thread will be blocked until the operation completes, preventing other code from executing.
    - Nested callbacks: When a function has nested callbacks, it can create a callback hell scenario, where the main thread is blocked waiting for each callback to complete before moving on to the next one.
    - Tight loops: If a loop is not properly optimized, it can cause the main thread to get stuck in the loop, preventing other code from executing.
    - Memory leaks: If the application has memory leaks, it can cause the main thread to become blocked as the application runs out of available memory.
- To avoid blocking the main thread in Node.js, it is important to use non-blocking APIs for I/O operations, avoid nested callbacks, optimize loops, and fix any memory leaks in the application. Additionally, using worker threads or a cluster module can help distribute the workload and avoid blocking the main thread.




## cluster in nodejs

- In Node.js, a cluster is a module that allows an application to take advantage of multi-core CPUs by creating child processes that can share the same server port and handle incoming requests in parallel.
- When an application is running on a single core, it can only process one request at a time. However, by creating a cluster of worker processes, an application can process multiple requests in parallel, increasing the overall performance and scalability of the application.
- The Node.js cluster module provides an easy way to create a cluster of worker processes that can share the same server port and handle incoming requests. The cluster module creates a master process that manages the worker processes, and each worker process runs independently and can handle incoming requests.
- When a request comes in, the master process distributes the request to an available worker process, and the worker process processes the request and sends the response back to the client. By using a cluster of worker processes, an application can handle a large number of concurrent requests in parallel, improving the overall throughput and performance.
- The cluster module also provides various features for managing worker processes, such as automatic restart on failure, load balancing, and communication between worker processes.



## What is the event loop?

- In Node.js, the event loop is a mechanism that allows for non-blocking I/O operations. It is a single-threaded loop that runs continuously, waiting for events to occur, and executing callbacks when those events happen.
- The event loop is responsible for managing all the asynchronous operations that occur in a Node.js application, such as reading and writing to files or making network requests. When an asynchronous operation is initiated, Node.js will register a callback function to be executed once the operation is complete. The event loop will then continue to run, allowing the main thread to perform other tasks.
- When an asynchronous operation completes, the event loop will push the associated callback function onto a queue. This queue of callback functions is known as the event queue. The event loop will then pick up the first callback function from the event queue and execute it.
- By using the event loop, Node.js is able to handle many concurrent connections without requiring additional threads or processes. This allows Node.js to be highly scalable and efficient, making it a popular choice for building high-performance web applications.



## What are different phases in event loop?

- In Node.js, the event loop is divided into several phases, each of which corresponds to a particular type of event that needs to be processed. These phases are:
    - **Timer**: The first phase of the event loop is the Timer phase. During this phase, any timers that have reached their specified time will have their associated callback functions added to the callback queue.
    - **I/O callbacks**: The next phase is the I/O callbacks phase. In this phase, any I/O events that have completed their operations (such as file I/O or network I/O) will have their associated callback functions added to the callback queue.
    - **Idle, Prepare**: These phases are internal and rarely used, and we can skip them for simplicity.
    - **Poll**: The Poll phase is where the event loop spends most of its time. In this phase, the event loop will check for new I/O events and execute their associated callback functions immediately. If there are no new I/O events, it will wait for events to occur.
    - **Check**: The Check phase is used to execute callbacks that are scheduled by setImmediate().
    - **Close callbacks**: The final phase is the Close callbacks phase, where all close events are processed, such as when a socket or handle is closed.
- After completing all the phases, the event loop will check if it has been stopped by the process.exit() method, and if not, it will start again from the Timer phase.
-  the event loop in Node.js is a crucial part of its architecture, allowing it to handle I/O operations efficiently and avoid blocking the main thread. By executing callbacks in a non-blocking way, Node.js can achieve high throughput and low latency, making it ideal for building scalable and high-performance applications.



## What is process.tick?

- process.nextTick() is a Node.js method that allows a function to be executed right after the current function is completed, but before the next function in the event loop is executed. This method is often used to avoid blocking the event loop and to make sure that certain operations are performed as soon as possible. When a function is passed to process.nextTick(), it will be executed at the end of the current iteration of the event loop, before any I/O events are processed.
- The process.nextTick() method is different from setImmediate() and setTimeout() in that it does not use the event loop. Instead, it uses a special queue that is processed at the end of each tick of the event loop.



## What is the difference between setTimeout and setInterval?

- While process.nextTick() is a useful tool in Node.js for scheduling a callback to be executed at the next iteration of the event loop, it can potentially starve the event loop if used improperly. This can happen if too many functions are queued using process.nextTick() without giving the event loop a chance to execute other tasks.
- While process.nextTick() is a useful tool in Node.js for scheduling a callback to be executed at the next iteration of the event loop, it can potentially starve the event loop if used improperly. This can happen if too many functions are queued using process.nextTick() without giving the event loop a chance to execute other tasks.
- For example, consider the following code:
    ```javascript
            function doSomething() {
                console.log('doing something');
                process.nextTick(doSomething);
                }
                doSomething();
- In this code, doSomething() is scheduled to be executed at the end of each iteration of the event loop, effectively creating an infinite loop. While this code may work for a small number of iterations, it can quickly starve the event loop if left unchecked, as the event loop will not have a chance to execute other tasks.
- To avoid this problem, it's important to use process.nextTick() sparingly and to ensure that other types of tasks, such as I/O events, have a chance to be processed by the event loop. It's also a good practice to use other scheduling methods, such as setImmediate() or setTimeout(), in combination with process.nextTick() to ensure that the event loop is not starved.



## What is the difference between setTimeout and setInterval?

- setTimeout() and setInterval() are both JavaScript methods used to schedule the execution of a function after a certain amount of time has passed. The key difference between them is how they handle the repetition of the scheduled function.
- setTimeout() is used to execute a function after a specified delay, specified in milliseconds. Once the delay has elapsed, the function is executed once and then the timer is cleared. If you want to execute the function repeatedly, you need to call setTimeout() again after the function has executed.


## How can you make a network request with http module from the backend?

- In Node.js, you can use the built-in http module to make HTTP requests from the backend. Here's an example of how to make a GET request to a URL using the http module:
    ```javascript
    - const http = require('http');
    - const options = {
        hostname: 'example.com',
        port: 80,
        path: '/api',
        method: 'GET'
        }
    - const req = http.request(options, (res) => {
        console.log(`statusCode: ${res.statusCode}`);

    - res.on('data', (data) => {
        console.log(data.toString());
        });
        });

    - req.on('error', (error) => {
        console.error(error);
        });

    - req.end();



## How can you create your own events?

- In Node.js, an EventEmitter is a class provided by the built-in events module that allows you to create and emit custom events.
- The EventEmitter class provides methods for emitting events, registering event listeners, and managing event subscriptions. You can create your own EventEmitter instance and register event listeners on it, or use one of the many built-in objects that already inherit from EventEmitter, such as http.Server, fs.ReadStream, and process.
 - Here's an example of how to create and emit your own custom events:
    ```javascript
     const EventEmitter = require('events');
    // Create a new event emitter instance
    const myEmitter = new EventEmitter();
    // Listen for a custom event
    myEmitter.on('myEvent', (data) => {
    console.log('Received data:', data);
    });
    // Emit a custom event with some data
    myEmitter.emit('myEvent', { message: 'Hello, world!' })

- You can create as many custom events as you need by calling the emit() method on the event emitter instance and passing it an event name and any data you want to include with the event. You can also listen for custom events using the on() method and define your own custom callback functions to handle the events as needed.


## How does your Node.js application handle scale? Elaborate?

- Scaling a Node.js application can be achieved through various approaches, some of which are:
    - **Vertical Scaling**: Vertical scaling refers to adding more resources to your existing server. For example, upgrading your server with a higher CPU, more memory, or faster storage. This approach can be useful for small-scale applications or when you experience a sudden increase in traffic, but it has a limit to how much it can scale.
    - **Horizontal Scaling**: Horizontal scaling refers to adding more servers to your application, also known as "scaling out". This approach involves distributing your application load across multiple servers. You can use a load balancer to distribute incoming requests to different servers, ensuring that no single server is overloaded. This approach provides better scalability and is widely used in large-scale applications.
    - **Cluster Mode: Node**.js provides a built-in cluster module that allows you to run multiple instances of your Node.js application on the same server, also known as "scaling up". The cluster module provides a simple API for creating a cluster of worker processes that share the same server resources, allowing your application to take advantage of multi-core CPUs. Each worker process can handle incoming requests, and the master process manages the distribution of requests among the workers. This approach can provide significant performance improvements for CPU-intensive tasks.
    - **Microservices**: Microservices architecture involves breaking down your application into smaller, independent services that can communicate with each other. Each microservice can be developed and deployed independently, allowing for better scalability and flexibility. You can use Node.js to develop and deploy microservices, and use a message broker or an API gateway to manage communication between the services.
    - **Serverless Architecture**: Serverless architecture is an approach where your application is broken down into smaller functions that can be deployed and run on a cloud provider's infrastructure. The cloud provider manages the underlying server resources, and you only pay for the actual usage of the functions. This approach can provide high scalability and cost-effectiveness, but it may require changes to your application architecture.
- there are various approaches to scale a Node.js application, and the choice depends on the specific requirements of your application. Horizontal scaling and cluster mode are commonly used for larger applications, while vertical scaling can be useful for smaller applications. Microservices and serverless architecture can provide better scalability and cost-effectiveness, but may require changes to your application architecture.




## What are CORS? How do you configure them? Why do you need them?

- CORS stands for Cross-Origin Resource Sharing, which is a security feature implemented by web browsers to prevent unauthorized access to resources on a website. It allows web servers to control which domains or origins can access their resources by specifying a set of response headers.
- By default, web browsers enforce a policy called the "same-origin policy," which prevents JavaScript code from making requests to a different domain or port than the one that served the original page. This policy is designed to protect users from malicious websites that could exploit their trust in a legitimate site by making unauthorized requests.
- However, there are some legitimate use cases where a website may need to make cross-origin requests, such as when making API requests to a different server. CORS provides a mechanism for web servers to relax the same-origin policy and allow cross-origin requests from trusted domains or origins.
- To configure CORS, the web server needs to set the appropriate response headers when serving the requested resource. The most common response headers used for CORS are:
    - **Access-Control-Allow-Origin**: Specifies the domains or origins that are allowed to access the resource. This header can be set to a specific domain or "*" to allow any domain to access the resource.
    - **Access-Control-Allow-Methods**: Specifies the HTTP methods that are allowed for the resource.
    - **Access-Control-Allow-Headers**: Specifies the HTTP headers that are allowed for the resource.
    - **Access-Control-Allow-Credentials**: Indicates whether cookies or other credentials are allowed for the request.
- To enable CORS on a Node.js server, you can use the cors middleware package or set the appropriate response headers manually in your server code.
- ORS is a security feature implemented by web browsers to prevent unauthorized access to resources on a website. It allows web servers to control which domains or origins can access their resources by specifying a set of response headers, and it is necessary when making cross-origin requests from a website to a different domain or port.



## What is rate limiting?

- Rate limiting is a technique used to limit the number of requests that a user or an IP address can make to a website or an API within a given time frame. It is commonly used by web developers to prevent abuse, protect against denial-of-service attacks, and maintain the performance and stability of their applications.
- The basic idea behind rate limiting is to set a threshold for the number of requests that can be made within a certain time period, such as one request per second. If a user or an IP address exceeds this limit, the server will respond with an error or a warning message, indicating that the request has been rejected or delayed.
- Rate limiting can be implemented in different ways, depending on the specific requirements of the application. Some common techniques include:
    - **Token bucket algorithm**: This algorithm maintains a fixed number of tokens that are added to a bucket at a fixed rate. Each request consumes one token from the bucket, and if the bucket is empty, the request is rejected or delayed.
    - **Rolling window algorithm**: This algorithm uses a sliding time window to track the number of requests made within a given time period. If the number of requests exceeds the limit, the server responds with an error or a warning message.
    - **Distributed rate limiting**: This technique uses multiple servers to distribute the load and limit the number of requests made to a specific resource. This can be useful for applications that require high availability and scalability.
- rate limiting is an effective way to prevent abuse and maintain the performance and stability of web applications and APIs.



## What is the difference between Encryption and Hashing?

- Encryption and hashing are two techniques used for protecting data, but they serve different purposes.

| . |  Encryption   | hashing | 
| :---:|    :----:   | :--------: | 
| Purpose | Confidentiality | Integrity |
| Input | Plain text | any data |
| Output | cipher text | hash value |
| Reversibility	| Can be reversed with correct key or algorithm | Cannot be reversed |
| Security | Depends on the strength of the encryption algorithm and key | Depends on the strength of the hashing algorithm |
| Usage | Used to protect the confidentiality of data | Used to verify the integrity of data | 
| Examples | SSL, AES, RSA | SHA-256, MD5, bcrypt |

- Encryption is a process of transforming plaintext (unencrypted) data into ciphertext (encrypted) data using a key or algorithm. The ciphertext can be decrypted back into plaintext with the correct key or algorithm. The goal of encryption is to protect the confidentiality of data, so that only authorized users can access it.
- Hashing, on the other hand, is a process of converting data into a fixed-length, unique string of characters called a hash value, using a hashing algorithm. The hash value is a one-way function that cannot be reversed back into the original data. The goal of hashing is to protect the integrity of data, by verifying that the data has not been modified or tampered with.



## What is the difference between https and http?

- HTTP (Hypertext Transfer Protocol) and HTTPS (Hypertext Transfer Protocol Secure) are both protocols used for transferring data over the internet, but they differ in the way they secure data.
- HTTP is an unencrypted protocol, which means that any data that is transmitted over an HTTP connection is in plain text and can be intercepted and read by anyone who can access the data.
- HTTPS, on the other hand, is a secure version of HTTP that uses encryption to protect data. HTTPS uses SSL/TLS (Secure Sockets Layer/Transport Layer Security) protocol to encrypt the data that is transmitted over the internet. This makes it more difficult for anyone to intercept and read the data.
- In summary, the main difference between HTTP and HTTPS is that HTTPS provides encryption to protect data transmitted over the internet, while HTTP does not. This makes HTTPS a more secure protocol for transmitting sensitive data such as passwords, credit card numbers, and other personal information.


## What is TLS?

- TLS stands for Transport Layer Security, which is a cryptographic protocol used to provide secure communication over the internet. TLS is the successor of SSL (Secure Sockets Layer) protocol, which is now deprecated.
- TLS uses a combination of symmetric and asymmetric encryption to protect the data that is transmitted over the internet. When two systems establish a TLS connection, they negotiate a shared secret key that is used to encrypt and decrypt the data. This ensures that the data remains confidential and cannot be intercepted and read by anyone who does not have the secret key.
- TLS also provides integrity and authentication to the data transmitted over the internet. It verifies that the data has not been tampered with during transmission and that the sender is who they claim to be.
- TLS is commonly used to secure web traffic, email, messaging, and other types of internet communication. It is implemented in web browsers, email clients, and other applications that require secure communication over the internet.


## What is AES?

- AES stands for Advanced Encryption Standard, which is a symmetric-key encryption algorithm used to protect data. It is a widely-used and trusted encryption standard, and is considered to be very secure when used with a strong key.
- AES operates on fixed-length blocks of data, and can encrypt and decrypt data in blocks of 128 bits using a key size of 128, 192, or 256 bits. The same key is used for both encryption and decryption, hence it is called symmetric-key encryption.
- AES has several advantages over other encryption algorithms. It is computationally efficient and can be implemented in software or hardware. It is also resistant to attacks such as linear and differential cryptanalysis.
- AES is used in a wide range of applications such as securing data in transit over the internet, encrypting data stored on a hard drive, and securing communication between devices on a network.



## What is JWT Token? Why do we need to use JWT? What are some pros and cons?

 - JWT stands for JSON Web Token, which is an open standard for securely transmitting information between parties as a JSON object. JWTs are often used for authentication and authorization in web applications.
 - JWTs are composed of three parts: a header, a payload, and a signature. The header contains information about the algorithm used to sign the token, the payload contains the claims (information about the user or session), and the signature is used to verify that the token has not been tampered with.
  - JWTs are commonly used for authentication because they allow a user to prove their identity without the need for server-side sessions or cookies. This makes JWTs more scalable and easier to implement in a distributed system. JWTs can also be used for authorization, by including the user's role or permissions in the payload.
- Some pros of using JWTs include:
    - Stateless: Since the token contains all the necessary information, there is no need to store session data on the server, making the system more scalable and easier to implement.
    - Portable: JWTs can be used across different domains and platforms, making them very flexible.
    - Decentralized: JWTs can be verified without the need for a centralized authority, making them suitable for use in a distributed system.
- Some cons of using JWTs include:
    - Security: If the token is intercepted or stolen, the attacker can gain access to the user's account. It is therefore important to use strong encryption and signing algorithms, and to keep the token secret.
    - Size: JWTs can be quite large, especially if they contain a lot of claims, which can increase the size of HTTP requests.
    - Payload: The payload is encoded, not encrypted, so sensitive information should not be included in the payload.


## What is salting? Where do we store salt?

- Salting is the process of adding a random string of characters to a password before hashing it to make it more difficult to crack through brute force or dictionary attacks. The salt value is a unique string that is added to the password before hashing. The salt value should be unique for each password, which makes it much harder for an attacker to pre-compute a list of hash values.
- In general, the salt value is stored in the same database as the password hash, but in a separate field. This ensures that the salt is always available when the password hash needs to be verified. It is important to note that the salt value does not need to be kept secret, as it is only used to make the hashing process more difficult to crack.



## What is the difference between authorisation and Authentication?

- Authentication and authorization are two different concepts in information security that are often used together. Authentication is the process of verifying the identity of a user or system entity, typically through the use of login credentials such as a username and password. Authentication answers the question "Who are you?"
- Authorization, on the other hand, is the process of determining whether a user or system entity has the necessary permissions to perform a particular action or access a particular resource. Authorization is typically based on the authenticated identity of the user or entity. Authorization answers the question "What are you allowed to do?"
- To summarize, authentication is the process of verifying a user's identity, while authorization is the process of determining what actions or resources a user is allowed to access based on their authenticated identity.


## What is the difference between JS on the browser and node?

- JavaScript on the browser and Node.js are both implementations of the JavaScript programming language, but they have some fundamental differences in terms of their environment, capabilities, and use cases.
- Browser-based JavaScript typically runs in a web browser and is used to enhance the interactivity of web pages by allowing the creation of dynamic and interactive web content. It can manipulate the Document Object Model (DOM) of the web page, handle user interactions like mouse clicks and keyboard input, and make asynchronous network requests to fetch data from servers.
- Node.js, on the other hand, is a server-side runtime environment for JavaScript, which enables developers to build network applications such as web servers, command-line tools, and APIs. Unlike browser-based JavaScript, Node.js provides access to the underlying operating system's resources such as file system, network sockets, and operating system processes, making it possible to build powerful and scalable server-side applications.
- Some other key differences between JavaScript on the browser and Node.js are:
    - Environment: Browser-based JavaScript runs in the context of a web browser, while Node.js runs on a server or a local machine.
    - API: Browser-based JavaScript provides APIs for interacting with the DOM and the browser environment, while Node.js provides APIs for interacting with the file system, network, and other system resources.
    - Modules: In browser-based JavaScript, modules are loaded through script tags or other browser-specific mechanisms, while Node.js uses the CommonJS module system to load modules.
    - Concurrency: Browser-based JavaScript is inherently single-threaded and runs in the event loop, while Node.js supports both single-threaded and multi-threaded programming models using the event loop and worker threads.
- Overall, while both browser-based JavaScript and Node.js are based on the same language, their different environments and APIs make them suitable for different types of applications and use cases.



## what is the difference between readFile and readFileSync

- In Node.js, readFile and readFileSync are two functions that can be used to read the contents of a file. The main difference between them is that readFile is an asynchronous function, while readFileSync is a synchronous function.

- **readFile** function reads the contents of the file asynchronously, which means that it does not block the execution of the program while the file is being read. Instead, it uses a callback function to return the contents of the file once it has been read. This makes it more suitable for handling large files or when the program needs to perform other tasks while the file is being read.
    - Example:
    ```javascript
     // Using readFile
     const fs = require('fs');
     fs.readFile('myfile.txt', (err, data) => {
        if (err) throw err;
        console.log(data.toString());
        });

- **readFileSync** function reads the contents of the file synchronously, which means that it blocks the execution of the program until the file is read completely. This makes it simpler to use as the contents of the file are returned immediately, but it is not recommended for large files or for cases when the program needs to perform other tasks while the file is being read.
    - Example :
    ```javascript
    // Using readFileSync
     const fs = require('fs');
     const data = fs.readFileSync('myfile.txt');
     console.log(data.toString());





## How to create a web server without express?
    
- To create a web server without express, we can use the built-in Node.js 'http' module:
  ```javascript  
    const http = require('http');
    const server = http.createServer((req, res) => {
    res.writeHead(200, { 'Content-Type': 'text/plain' });
    res.write('Hello, World!');
    res.end();
    });

    server.listen(8000, () => {
    console.log(`Server running at port ${port}`);
    });

- This will create a simple web server that listens on port 3000 and sends back a 'Hello, World!' response to any incoming requests.




##  What is libuv?

- the C library that implements the Node.js event loop and all of the asynchronous behaviors of the platform
- libuv is a multi-platform support library with a focus on asynchronous I/O.It is primarily used for creating high-performance networking and server-side applications.
- The library handles various commonly required functionalities such as TCP and UDP socket communication, DNS resolution, child processes, file system operations, and other system-level events. It also provides an event loop that enables you to manage and handle asynchronous operations without blocking the execution of your main program.
-  With the event loop, developers can build high-performance applications that can scale to handle millions of concurrent connections.
- Libuv simplifies the process of building fast and scalable network-centric applications by providing a set of low-level tools to manage I/O operations.




## What are the different phases involved in event loop?

- The event loop is what allows Node.js to perform non-blocking I/O operations — despite the fact that JavaScript is single-threaded.
- The Node.js event loop is the mechanism that Node.js uses to handle incoming requests, execute callbacks, and return responses. It consists of different phases, such as timers, pending callbacks, poll, check, and close callbacks. Each phase has its own tasks to complete. 

- **timers**: Timers execute callbacks scheduled by setTimeout() and setInterval().A timer specifies the threshold after which a provided callback may be executed rather than the exact time a person wants it to be executed. Timers callbacks will run as early as they can be scheduled after the specified amount of time has passed; however, Operating System scheduling or the running of other callbacks may delay them.

- **pending callbacks**: executes I/O callbacks deferred to the next loop iteration.This phase executes callbacks for some system operations such as types of TCP errors. For example if a TCP socket receives ECONNREFUSED when attempting to connect, some *nix systems want to wait to report the error. This will be queued to execute in the pending callbacks phase.

- **idle, prepare**: only used internally.

- **poll**: The poll phase has two main functions:
- 1 - Calculating how long it should block and poll for I/O, then
- 2 - Processing events in the poll queue.
- When the event loop enters the poll phase and there are no timers scheduled, one of two things will happen:
- If the poll queue is not empty, the event loop will iterate through its queue of callbacks executing them synchronously until either the queue has been exhausted, or the system-dependent hard limit is reached.
- If the poll queue is empty, one of two more things will happen:
    - If scripts have been scheduled by setImmediate(), the event loop will end the poll phase and continue to the check phase to execute those scheduled scripts.
    - If scripts have not been scheduled by setImmediate(), the event loop will wait for callbacks to be added to the queue, then execute them immediately.
- Once the poll queue is empty the event loop will check for timers whose time thresholds have been reached. If one or more timers are ready, the event loop will wrap back to the timers phase to execute those timers' callbacks.

- **check**: setImmediate() callbacks are invoked here. 
    - This phase allows a person to execute callbacks immediately after the poll phase has completed. If the poll phase becomes idle and scripts have been queued with setImmediate(), the event loop may continue to the check phase rather than waiting.
    - setImmediate() is actually a special timer that runs in a separate phase of the event loop. It uses a libuv API that schedules callbacks to execute after the poll phase has completed.
    - Generally, as the code is executed, the event loop will eventually hit the poll phase where it will wait for an incoming connection, request, etc. However, if a callback has been scheduled with setImmediate() and the poll phase becomes idle, it will end and continue to the check phase rather than waiting for poll events.

- **close callbacks**: some close callbacks, e.g. socket.on('close', ...).
    - If a socket or handle is closed abruptly (e.g. socket.destroy()), the 'close' event will be emitted in this phase. Otherwise it will be emitted via process.nextTick().




## What are timers in Node.js?

- The Timers module in Node.js contains functions that execute code after a set period of time. Timers do not need to be imported via require(), since all the methods are available globally to emulate the browser JavaScript API. They are useful for many purposes, including scheduling events, tracking time intervals, and managing application state.

- **setTimeout**: can be used to schedule code execution after a designated amount of milliseconds. setTimeout() accepts a function to execute as its first argument and the millisecond delay defined as a number as the second argument. Additional arguments may also be included and these will be passed on to the function.
    - Example
        ```javascript
        function myFunc(arg) {
            console.log(`arg was => ${arg}`);
            }
        setTimeout(myFunc, 1500, 'funky');
    - The timeout interval that is set cannot be relied upon to execute after that exact number of milliseconds. This is because other executing code that blocks or holds onto the event loop will push the execution of the timeout back. The only guarantee is that the timeout will not execute sooner than the declared timeout interval.
    - setTimeout() returns a Timeout object that can be used to reference the timeout that was set. This returned object can be used to cancel the timeout ( clearTimeout() below) as well as change the execution behavior.

- **setImmediate()** : will execute code at the end of the current event loop cycle. This code will execute after any I/O operations in the current event loop and before any timers scheduled for the next event loop. This code execution could be thought of as happening "right after this", meaning any code following the setImmediate() function call will execute before the setImmediate() function argument.
    - Example
        ```javascript
         console.log('before immediate');
         setImmediate((arg) => {
            console.log(`executing immediate: ${arg}`);
            }, 'so immediate');
         console.log('after immediate');

- output : before immediate,after immediate,executing immediate: so immediate
- setImmediate() returns an Immediate object, which can be used to cancel the scheduled immediate.
- Don't get setImmediate() confused with process.nextTick(). There are some major ways they differ. The first is that process.nextTick() will run before any Immediates that are set as well as before any scheduled I/O. The second is that process.nextTick() is non-clearable, meaning once code has been scheduled to execute with process.nextTick(), the execution cannot be stopped, just like with a normal function.

- **setInterval()** : If there is a block of code that should execute multiple times, setInterval() can be used to execute that code. setInterval() takes a function argument that will run an infinite number of times with a given millisecond delay as the second argument. Just like setTimeout(), additional arguments can be added beyond the delay, and these will be passed on to the function call. Also like setTimeout(), the delay cannot be guaranteed because of operations that may hold on to the event loop, and therefore should be treated as an approximate delay.
- Just like setTimeout(), setInterval() also returns a Timeout object which can be used to reference and modify the interval that was set.

-  setTimeout(), setImmediate(), and setInterval() return a timer object that can be used to reference the set Timeout or Immediate object. By passing said object into the respective clear function, execution of that object will be halted completely. The respective functions are clearTimeout(), clearImmediate(), and clearInterval(). 




## What is NVM? how do you use it?

- NVM stands for Node Version Manager. It is a command-line tool that allows you to easily switch between different versions of Node.js on your computer. This can be particularly useful if you are working on multiple projects that require different versions of Node.js.
    - Steps to use NVM
     - 1) Install NVM: You can download NVM from the official NVM GitHub repository 
     - 2)Install a specific version of Node.js: Once you have installed NVM, you can use it to install a specific version of Node.js. For example, to install version 14.16.0, you would use the following command: 
        ```javascript
        nvm install 14.16.0.
     - 3) Switch between versions of Node.js: After you have installed multiple versions of Node.js, you can switch between them using the nvm use command. For example, to switch to version 14.16.0, you would use the following command:
        ```javascript
        nvm use 14.16.0.
     - 4)Set a default version of Node.js: You can set a default version of Node.js to be used whenever you open a new terminal window using the nvm alias command. For example, to set version 14.16.0 as the default version, you would use the following command:
        ```javascript
            nvm alias default 14.16.0.



## How does the crypto module work?

- The "crypto" module in computer programming refers to cryptography, which is the practice of secure communication in the presence of third parties. The crypto module provides a set of cryptographic primitives and algorithms that can be used to encrypt and decrypt data, generate digital signatures, and perform other related tasks.
- The crypto module typically provides a set of functions and classes that can be used to implement various cryptographic algorithms, such as AES (Advanced Encryption Standard), RSA (Rivest–Shamir–Adleman), SHA (Secure Hash Algorithm), and others. These algorithms are used to perform encryption and decryption of data, generate digital signatures, and perform other cryptographic operations.
- To use the crypto module, one typically needs to first generate a key or a pair of keys using a specific algorithm. The key can then be used to encrypt data, and the same key (or another key in some cases) can be used to decrypt the data. The encryption process typically involves applying a specific algorithm to the data, along with the key, to produce a ciphertext. The decryption process involves applying the same algorithm to the ciphertext, along with the key, to recover the original plaintext.
- Digital signatures can also be generated using the crypto module. This involves applying a specific algorithm to a message, along with a private key, to produce a signature. The same algorithm can then be used to verify the signature using the corresponding public key.
- Overall, the crypto module provides a powerful set of tools for implementing various cryptographic algorithms and ensuring the security of data and communication in computer programs.



## What are web sockets?

- WebSockets are a communication protocol that allows real-time bidirectional data transfer between a client and a server over a single, persistent TCP connection. Unlike traditional HTTP requests, which are stateless and require a new connection to be established for each request, WebSockets allow for a long-lived connection to be established between a client and a server, enabling both the client and the server to send and receive data at any time without the overhead of establishing a new connection.
- WebSockets are particularly useful for applications that require real-time data transfer, such as online gaming, chat applications, financial trading platforms, and other applications that require constant, low-latency communication between a client and a server.
- example how WebSockets work in practice:
    - 1) The client sends an HTTP request to the server requesting to open a WebSocket connection.
    - 2) The server responds with an HTTP response containing an "Upgrade" header that indicates that the connection is being upgraded to a WebSocket connection.
    - 3) The client and server negotiate the WebSocket protocol version and other parameters, and establish a persistent TCP connection between the client and the server.
    - 4) Once the WebSocket connection is established, both the client and the server can send data to each other at any time, without the need to establish a new connection.
    - 5)The data sent over the WebSocket connection is encapsulated in frames, which contain a header and a payload. The header specifies the type of data contained in the frame, such as text or binary data, and whether the frame is the final frame in a sequence of frames. The payload contains the actual data being sent.
    - 6) When the client or server wants to close the WebSocket connection, they send a special close frame to the other end of the connection, indicating that the connection is being closed.



## What is MVC framework?

- MVC stands for Model-View-Controller, which is a software design pattern that separates an application into three interconnected components: the model, the view, and the controller. 
- In the context of Node.js, an MVC (Model-View-Controller) framework is a server-side framework that provides a structured way of building web applications using the MVC architectural pattern. 
- The model component represents the data and the business logic of the application. It is responsible for handling data validation, data storage, and data retrieval. The view component is responsible for rendering the data to the user interface. It receives data from the controller and formats it for display to the user. The controller component acts as an intermediary between the model and view components. It receives user input, updates the model, and then sends updated data to the view for display.
- Node.js has a number of MVC frameworks available, including Express.js, Sails.js, and Loopback. These frameworks provide a set of tools and conventions for building web applications using the Model-View-Controller architecture.
- In an MVC framework for Node.js, the model component might include a database schema and a set of methods for querying and updating data. The view component might include HTML templates and JavaScript code for displaying data in a web browser. The controller component would handle user input, updating the model with new data, and sending data to the view for display.
- Using an MVC framework in Node.js provides a number of benefits, including improved organization, modularity, and maintainability of code. By separating the application into distinct components, developers can work on different components of the application without interfering with each other, making it easier to manage and maintain code over time.




## How do you do validations?

- Validations are an important part of any web application, as they help ensure that data is correct and consistent before it is processed or stored. Here are some common approaches to implementing validations in web applications:
    - 1) **Server-side validations**: This involves validating data on the server-side before processing or storing it. In a Node.js application, you can use a middleware like express-validator to validate data in the request body or query parameters before passing it to the controller.
    - 2) **Client-side validations**: This involves validating data on the client-side before sending it to the server. You can use HTML5 form validation attributes like required and pattern, or JavaScript validation libraries like jQuery Validation to validate form data before submission.
    - 3)**Database constraints**: This involves defining constraints on the database schema to ensure that data is consistent and valid. For example, you can define a unique constraint on a field to prevent duplicate data from being inserted into the database.
    - 4)**Custom validators**: In some cases, you may need to implement custom validators to validate data that doesn't fit into a standard validation pattern. For example, you may need to validate an email address format or a phone number format.
- By doing so, you can prevent errors and improve the overall reliability and user experience of your application.




##  What is HTTPS? what is the difference between HTTP and HTTPS?

- HTTPS stands for Hypertext Transfer Protocol Secure. It is a secure version of the standard HTTP protocol used for sending data between a web server and a web browser.
- The main difference between HTTP and HTTPS is that HTTPS uses encryption to secure the data that is being transmitted. In other words, HTTPS encrypts the data so that it cannot be intercepted or read by unauthorized parties.
- When a user visits a website that uses HTTPS, the web browser and the web server establish a secure connection using an SSL/TLS (Secure Sockets Layer/Transport Layer Security) certificate. This certificate verifies the identity of the website and enables encryption of the data being transmitted between the web browser and the web server.
- In contrast, HTTP does not use encryption to secure the data being transmitted. This means that the data can be intercepted and read by anyone who has access to the network over which the data is being transmitted.
- HTTPS is important for protecting sensitive data, such as passwords, credit card numbers, and personal information, that is transmitted over the internet. By using encryption, HTTPS helps to ensure the confidentiality and integrity of this data and prevents it from being intercepted or read by unauthorized parties.




## What is SSL/TLS?

- SSL/TLS stands for Secure Sockets Layer/Transport Layer Security. It is a protocol used to establish a secure and encrypted connection between a web server and a web browser.
- The SSL/TLS protocol works by using a combination of public key and symmetric key encryption to secure the data being transmitted. When a user visits a website that uses SSL/TLS, the web server and the web browser exchange digital certificates to authenticate each other's identity. Once the authentication is complete, a secure and encrypted connection is established between the two partie.
- SSL/TLS is commonly used for secure online transactions, such as e-commerce, online banking, and other sensitive online activities. It is also used to secure email communications and other types of online communication.
- The SSL/TLS protocol has evolved over time, and newer versions of the protocol provide stronger encryption and better security features. 



## I'm using an arrow function for a virtual, middleware, getter/setter, or method and the value of this is wrong. Why?

- When using an arrow function for a virtual, middleware, getter/setter, or method in Mongoose, the value of **this** may not be what you expect. This is because arrow functions do not have their own **this** context and instead inherit **this** from the context in which they were defined.
- When using an arrow function for a virtual, middleware, getter/setter, or method in Mongoose, the this value inside the arrow function may not be bound to the current document or model instance as expected. This is because arrow functions do not have their own this context and instead inherit this from the context in which they were defined. To fix this issue, you can use a regular function instead of an arrow function, which will have its own this context bound to the current document or model instance when called by Mongoose.

    - **Error code**
        - const schema = new mongoose.Schema({name: String});
        - schema.virtual('fullName').get(() => {return `${this.firstName} ${this.lastName}`;});

    - **correct code**
        - const schema = new mongoose.Schema({firstName: String,lastName: String});
        - schema.virtual('fullName').get(function() {return `${this.firstName} ${this.lastName}`;})



## What is OAuth

- OAuth (Open Authorization) is an open standard protocol that allows third-party applications to access user data from other services, such as social media platforms or cloud storage providers, without the need for the user to share their login credentials.
- OAuth works by allowing the third-party application to request access to a user's account on the service provider's platform. The user is then presented with a login prompt, and if they consent to the request, the service provider generates a temporary access token that is passed to the third-party application. This token grants the application limited access to the user's data, such as their profile information or files.
- OAuth is widely used by social media platforms, such as Facebook and Twitter, to allow users to log in to third-party applications using their social media accounts. It is also used by cloud storage providers, such as Google Drive and Dropbox, to allow third-party applications to access files stored in the user's account.
- One of the key benefits of OAuth is that it allows users to control the access that third-party applications have to their data without sharing their login credentials. It also simplifies the login process for users, as they can use their existing accounts on social media platforms or other services to log in to third-party applications.
- OAuth is a protocol that allows you to give permission to other websites or apps to access your information from another website, without giving them your password or personal details. It's like a security guard that checks who is allowed to access your data and what they can do with it. This makes it easier to use multiple websites or apps without having to remember multiple usernames and passwords, and keeps your personal information more secure.



## What is REST api?

- REST (Representational State Transfer) API is an architectural style for building web services that allows different applications to communicate with each other using HTTP requests and responses. RESTful APIs use the standard HTTP methods (such as GET, POST, PUT, and DELETE) to manipulate resources (such as data, files, or objects) on a server.
- The key features of a RESTful API include:
    - Client-server architecture: The client and server are separated and communicate through a uniform interface, which allows them to evolve independently.
    - Statelessness: Each request from the client to the server contains all the necessary information to process the request, and the server does not store any state information about the client. This simplifies scalability and improves reliability.
    - Cacheability: Responses from the server can be cached by the client to improve performance.
    - Layered system: The architecture can be composed of multiple layers, each of which provides a different service, such as load balancing, security, or caching.
    - Uniform interface: The interface between the client and server is standardized, which simplifies communication and makes it easier for different clients to interact with the same server.
- RESTful APIs are widely used for building web applications and services, as they provide a simple and efficient way to expose data and functionality over the web. They are also flexible and can be used with different programming languages and platforms.



## What is Caching?

- Caching is the process of storing frequently used data or resources in a cache, which is a temporary storage location. The cache can be a separate hardware component or software component, and it is typically faster than the original data source, allowing for quicker access.
- Caching is used to improve performance and reduce network traffic by reducing the number of requests made to the original data source. When a client requests data or resources that are already in the cache, the data can be served from the cache instead of being fetched from the original source. This can significantly reduce the amount of time it takes to retrieve data, especially for data that is accessed frequently.
- Caching can be implemented at different levels of a system, such as the web server, application server, or client-side. For example, a web server can cache frequently accessed web pages or API responses, while a browser can cache images, scripts, and other resources used by a web page.
- Caching can have a significant impact on performance and scalability, especially for web applications that handle large amounts of data or traffic. However, it's important to use caching judiciously, as incorrect caching strategies or settings can lead to stale or inconsistent data, which can cause problems for users and applications.




##  What are ways to cache on the backend?

- Caching on the backend is an important technique to improve the performance and scalability of web applications. Here are some ways to implement caching on the backend:
    - In-memory caching: This involves caching frequently accessed data in memory, which is faster to access than a database or file system. In-memory caching can be implemented using tools like Memcached or Redis.
    - Database caching: This involves storing frequently accessed data in a cache that sits between the application and the database. This can be implemented using tools like Hibernate or Entity Framework.
    - Content Delivery Network (CDN) caching: This involves caching static assets such as images, videos, and other media files on a distributed network of servers closer to the user, reducing latency and improving load times.
    - Application-level caching: This involves caching responses to specific requests that are computationally expensive to process, reducing the response time for subsequent requests.
    - Query caching: This involves caching the results of frequently executed database queries, reducing the time it takes to retrieve data from the database.
    - Full-page caching: This involves caching entire web pages, including HTML, CSS, and JavaScript, reducing the time it takes to generate and serve the page.




## What is LRU cache?

- LRU cache is a caching mechanism that stands for Least Recently Used cache. It is a type of cache that evicts the least recently used items first when the cache becomes full. This ensures that the most frequently used items remain in the cache, while the least frequently used items are removed to make room for new items.
- The LRU cache works by maintaining a doubly linked list of the cached items, ordered by the time they were last accessed. When a new item is added to the cache, it is added to the front of the list. When the cache becomes full, the least recently used item at the end of the list is evicted to make room for the new item.
- LRU cache is a popular caching strategy because it is simple to implement and effective at reducing cache misses. It is commonly used in web applications, databases, and operating systems to speed up access to frequently used data.



