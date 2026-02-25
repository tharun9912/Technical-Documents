# Model Context Protocol

## What is communication Protocol?

- A set of rules that tell devices how to talk to each other.
  
- Protocols are rules.

  **Examples :-** HTTP, HTTPS, SMTP, TCP.

- HTTP used when you open a website or application.

- HTTPS is the secure version of HTTP, it encrypts data .

-  Simple Mail Transfer Protocol (SMTP) is used to send emails.

- Transfer Control Protocol(TCP),it is the transport layer protocol.

## What is MCP?

- Model context protocol(MCP) is a communication protocol that defines how AI models communicate with external systems.
  
- It acts as a bridge between 
  
  - AI models (like LLMs)
  
  - External tools such as databases, APIs, apps and files.

- MCP helps in
   
  - Tool Integration.
  
  - Secure communication.
  
  - Extending model capabilities. 

## Architecture of MCP

- It follows a **client-server architecture**.
  
                     ┌──────────────────┐
                   │      User        │
                   └─────────┬────────┘
                             │
                             ▼
                   ┌──────────────────┐
                   │   AI Model (LLM) │
                   │  (Generates Tool │
                   │      Calls)      │
                   └─────────┬────────┘
                             │
                             ▼
                   ┌──────────────────┐
                   │    MCP Client    │
                   │ (Handles Protocol│
                   │   Communication) │
                   └─────────┬────────┘
                             │
               ┌─────────────┼─────────────┐
               ▼             ▼             ▼
      ┌──────────────┐ ┌──────────────┐ ┌──────────────┐
      │ MCP Server 1 │ │ MCP Server 2 │ │ MCP Server 3 │
      │  (Database)  │ │ (File System)│ │   (Web API)  │
      └──────┬───────┘ └──────┬───────┘ └──────┬───────┘
             │                  │                 │
             ▼                  ▼                 ▼
      ┌──────────────┐ ┌──────────────┐ ┌──────────────┐
      │ PostgreSQL   │ │ Local Files  │ │ External API │
      │   Database   │ │              │ │  (Weather)   │
      └──────────────┘ └──────────────┘ └──────────────┘ 


## Architecture Flow

 **User → AI Model → MCP Client → MCP Server → Tool → Response → AI Model → User**

### Tools
- **Tools** are the functions that AI models can call.
  
- **Example :-**  get_weather(), execute_sql_query().
  
### MCP Client
- Takes the models tool request.
  
- Converts it into MCP format.
  
- Sends it to the correct MCP server.

- Handles authentication.
  
### MCP Server
- Each server provides specific functionality.
  
- MCP server can be different types such as database server, file server, API server.

-  Each server exposes specific tools.

- It also checks permission control.
### External tools/Resources

- These are the real systems.

   **Example:-**  PostgreSQL database, Weather API etc.


## Summary

- Model Context Protocol (MCP) helps AI models to safely connect with external tools 
  like databases, files, and APIs.

- It uses client-server architecture to manage communication between the AI model and external tools.

- It helps AI get real data and do real tasks.

- MCP makes AI applications more powerful and secure.