[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=11454047&assignment_repo_type=AssignmentRepo)
# DNS Cache using Hash Table

This README file is for a significant school project that I have worked on. While the project's full codebase isn't included here due to specific requirements, this README serves as an essential guide to understanding the project's objectives, methodology, and outcomes.

## Description:

This project implements a DNS (Domain Name System) cache using a hash table data structure in C++. The DNS cache is a crucial component of networking systems as it stores recently resolved domain names and their corresponding IP addresses, enabling faster future lookups.

The project consists of the following components:

    Hash Table: The hash table is the core data structure used to store the DNS cache. It is implemented as an array of linked lists. Each bucket in the hash table represents a linked list of key-value pairs, where the key is the domain name, and the value is the associated IP address and expiration time.

    DNSRecord: The DNSRecord class represents a record in the DNS cache. It contains the IP address and expiration time of the record. The expiration time is set based on the TTL (Time-to-Live) value received from the DNS server. The DNSRecord class also provides a method to check if a record has expired.

    Node: The Node class represents a node in the linked list within each bucket of the hash table. Each node holds a key-value pair, where the key is the domain name, and the value is a DNSRecord object.

    Hash Function: A hash function is used to map the domain name keys to an index in the hash table. In this project, a custom hash function based on the std::hash is employed.

The project allows the following functionalities:

    Insertion: The project enables the insertion of domain name and IP address pairs into the DNS cache. Each entry includes an expiration time (TTL) received from the DNS server.

    Lookup: The project supports looking up IP addresses based on the domain name. If a requested domain name is found in the DNS cache and has not expired, the corresponding IP address is returned. Otherwise, if the entry has expired or is not present, "None" is returned.

    Expiration: The project automatically removes expired entries from the DNS cache when they are looked up or accessed. This ensures that only valid and up-to-date entries are stored in the cache.

    Display: The project provides a display function to show the contents of the hash table, including the linked list within each bucket. This facilitates understanding and monitoring the DNS cache.

The project is organized into multiple files, including main.cpp, HashTable.h, HashTable.cpp, DNSRecord.h, DNSRecord.cpp, Node.h, and Node.cpp. The Makefile is also provided to compile the project.

By implementing this DNS cache using a hash table, the project demonstrates an efficient approach to store and retrieve frequently accessed domain names and their corresponding IP addresses, reducing the need for frequent DNS lookups.

The DNS Cache project is a C++ program that implements a simple DNS cache using a hash table. It provides functionalities for storing DNS records, which map domain names to IP addresses, and managing their expiration times.

The program consists of the following classes:

DNSRecord: Represents a DNS record with an IP address and an expiration time (TTL). The DNSRecord class allows checking if a record has expired and retrieving its IP address.

HashTable: Implements the hash table data structure to store DNS records. It uses hash function to calculate hash codes for domain name keys and handles collisions with linked lists. The HashTable class provides functionalities for inserting, getting, and removing DNS records, as well as displaying the contents of the hash table.

Node: Represents a node in the linked list used for handling collisions in the hash table. Each node holds a domain name key and a corresponding DNSRecord.

## Challenges Faced:
During the development of this program, the following challenges were encountered:
* Handling of collisions in the hash table when inserting DNS records with the same hash value.
* Implementing the expiration logic for DNS records and managing the removal of expired records from the hash table.

## How to Run the Program:
To run the DNS program, follow these steps:
1. Ensure you have a C++ compiler installed on your system.
2. Download the program source code files (DNSRecord.h, DNSRecord.cpp, HashTable.h, HashTable.cpp, Node.h, Node.cpp, main.cpp, test.h, test.cpp) and place them in the same directory.
3. Compile the program using the makefile: ```make dns```
4. Run the compiled executable: ```./dns```
5. The program will execute various tests to verify its functionality. The test results will be displayed in the console, indicating whether each test passed or failed.

## Overview/Workflow of the Code and its Functionality:
The workflow of the DNS program is as follows:
1. The HashTable is initialized with a specified size, creating an empty hash table with linked list buckets.
2. DNS records are inserted into the cache, where the custom hash function determines their appropriate bucket.
3. The program retriuves IP addresses based on domain names from the cache. If a record has expired, it is removed from the cache.
4. The contents of the hash table are displayed, showing the stored records in each bucket.
5. The test file provides comprehensive testing of its functionalities in the DNS cache implementation.
