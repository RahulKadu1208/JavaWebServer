# JavaWebServer Architectures

This repository showcases three server-side concurrency models implemented in Java: **Single-threaded**, **Multi-threaded**, and **ThreadPool-based**. 
The goal is to demonstrate the impact of threading strategies on performance in client-server communication scenarios.

## 🧱 Project Structure

```
JavaWebServer/ 
    ├── SingleThreaded/ 
    │ ├── Client.java 
    │ └── Server.java 
    ├── MultiThreaded/ 
    │ ├── Client.java 
    │ └── Server.java 
    ├── ThreadPool/ 
    │ └── Server.java
```




## 🔧 Technologies Used

- Java Sockets
- Java Threads & Concurrency APIs
- ExecutorService (FixedThreadPool)
- Apache JMeter for performance testing

## 📈 Performance Testing

All server implementations were tested using [Apache JMeter](https://jmeter.apache.org/) to simulate multiple client requests and measure performance metrics such as:

- Average Response Time
- Requests per Second (Throughput)
- Active Thread Count

### 💡 Key Observations

- **SingleThreaded Server**: Simplest design but blocks on every client, leading to poor performance under load.
- **MultiThreaded Server**: Creates a new thread for each client, improving concurrency but consuming more resources.
- **ThreadPool Server**: Balances performance and resource usage using a fixed-size thread pool, making it the most scalable and efficient design.

## 🚀 How to Run

### Compile and Run (Single-threaded Example)

```bash
    cd SingleThreaded
    javac Server.java Client.java
    java Server      # in one terminal
    java Client      # in another terminal
```

### Run MultiThreaded Server with 100 clients

```bash
    cd MultiThreaded
    javac Server.java Client.java
    java Server      # Start server
    java Client      # Spawns 100 clients in parallel threads
```

### Run ThreadPool Server
```bash
    cd ThreadPool
    javac Server.java
    java Server      # Server uses a thread pool to handle connections
```

