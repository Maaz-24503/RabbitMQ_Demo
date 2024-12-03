# RabbitMQ Messaging Tutorial

This repository contains two simple console applications written in C# to demonstrate how to send and receive messages using **RabbitMQ**.

## Prerequisites

1. **RabbitMQ Server**  
   Ensure RabbitMQ is installed and running on your system. By default, RabbitMQ listens on `localhost` (port `5672`).
   - [Install RabbitMQ](https://www.rabbitmq.com/download.html)
   - Start the RabbitMQ server (if not running automatically).

2. **.NET 6.0 or Higher**  
   Make sure the .NET SDK is installed on your system. You can download it from the [.NET Downloads Page](https://dotnet.microsoft.com/en-us/download).
   Verify installation:
   ```bash
   dotnet --version
   ```
**How to Run**
1. **Clone the Repository**
  ```bash
  git clone https://github.com/your-repo/rabbitmq-tutorial.git
  cd rabbitmq-tutorial
  ```
2. **Build teh Applications**
  Navigate into each project directory and build the applications:
  ```bash
  cd Send
  dotnet build
  cd ../Receive
  dotnet build
  ```
3. **Run the Receiver (Receive)**
  Navigate to the Receive project directory and execute the following command:
  ```bash
  dotnet run
  ```
4. **Run the Sender (Send)**
  Navigate to the Send project directory and execute the following command:
  ```bash
  dotnet run
  ```
## How it Works

### Sender (Send):
- Declares a queue named `testQueue`.
- Publishes a message (`"This is a conversation"`) to the queue.
- Uses `BasicPublishAsync` for message delivery.

### Receiver (Receive):
- Declares the same queue (`testQueue`) to ensure it exists.
- Listens for messages using an `AsyncEventingBasicConsumer`.
- Prints each received message to the console.
