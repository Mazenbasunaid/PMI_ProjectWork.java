# Economics — Bank Client Manager

A small Java console application for managing bank clients: add, list, edit, and delete client records, with all data persisted to an XML file between runs.

## Features

- List all clients with their name, age, balance, and unique index
- Add a new client (auto-assigned a random index)
- Modify an existing client's details by index
- Delete a client by index
- Reads and writes client data to `clients.xml` using Java's built-in XML DOM API — no external dependencies

## Tech

- Java 17+ (uses switch expressions)
- No third-party libraries — only the standard JDK (`javax.xml.*`, `java.util.*`)

## Running it

```
javac src/economics/*.java -d out
cd out
java economics.Economics
```

Make sure a `clients.xml` file (matching the format below) is present in the working directory before running, or create one with the sample below.

On exit (option `0`), all changes are written back to `clients.xml`. Closing the program any other way discards unsaved changes.

## Data format

```xml
<clients>
    <student>
        <name>Jeremy</name>
        <index>0</index>
        <birthDate>1972</birthDate>
        <balance>350.0</balance>
    </student>
</clients>
```

## Project structure

```
src/economics/
├── Client.java       # Client data model
├── Economics.java     # CLI entry point and menu logic
└── XmlScanner.java    # XML read/write helpers
```

## Background

Originally built as a university project (data structures / file I/O exercise) during my BSc in Computer Science Engineering. Verified working on Java 21.
