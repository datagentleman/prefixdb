# PrefixDB

PrefixDB is a high-performance Key/Value database optimized for data locality,<br/> 
storing related data together in the same file to improve read and write performance.<br/>
It will be optimized for fixed-size data, making it especially suitable for financial<br/> 
and crypto applications.


# Supported Data Structures

* **Bucket** – store key/value pairs
* **Hashe** – store nested key/value data
* **Array** – simple fixed-size data structures


# Transactions
 
Transaction are designed to be simple and consit of two parts:

* **Conditions**
* **Operations**

Within each transaction, conditions are only allowed to operate on keys from the<br/>
same file. If all conditions succeed, operations can add or modify keys across<br/>
all collections.

This simplicity is sufficient for most real-world scenarios.


# Batches

The database supports executing batches of operations, ensuring that all operations<br/>
in a batch are eventually applied.


# Endianess

For simplicity, the database stores all data as-is, without any conversion.<br/>
The endianness of your system determines the endianness of the database.  

Since almost all modern servers and desktops are little-endian, the database<br/>
does not support big-endian systems. When moving data to another system, ensure<br/>
it uses the same endianness.


# OS

The database is designed to run on Linux and macOS systems.<br/>
Windows and other operating systems are not supported at this time.<br/>  

It is intended for server environments, which are typically Linux-based.<br/>
You will be able to run it on Windows using tools like Docker.
