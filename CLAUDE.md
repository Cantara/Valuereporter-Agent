# Valuereporter-Agent

## Purpose
A Java agent (javaagent) that monitors all calls to public methods in your application. When a method is called, start-time and end-time are forwarded to the Valuereporter service. Attaches to any JVM application via the -javaagent flag.

## Tech Stack
- Language: Java 8+
- Framework: Java Instrumentation API (javaagent)
- Build: Maven
- Key dependencies: Java Instrumentation API, ASM (bytecode manipulation)

## Architecture
Java agent that uses bytecode instrumentation to intercept method calls at runtime. Configured via command-line parameters specifying the base package to scan, Valuereporter host/port, and service name. Batches observations and periodically forwards them to the Valuereporter server via HTTP.

## Key Entry Points
- Agent JAR: valuereporter-agent-jar-with-dependencies.jar
- Configuration via -javaagent parameters: base.package, valuereporter.host, valuereporter.port, serviceName

## Development
```bash
# Build
mvn clean install
```

## Domain Context
Production method-level observability. Collects fine-grained usage data from running Java applications and forwards it to Valuereporter for analysis.
