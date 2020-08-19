# fprt-aug-cse-

Q-1. What is ACID properties and BASE properties? (10 mark) 
Ans-1)A transaction is a set of related changes which is used to achieve some of the ACID properties. Transactions are tools to achieve the ACID properties.
A transaction can be defined as a group of tasks. A single task is the minimum processing unit which cannot be divided further.
A transaction in a database system must maintain Atomicity,Consistency, Isolation, and Durability − commonly known as ACID properties − in order to ensure accuracy, completeness, and data integrity.
Let’s take an example of a simple transaction. Suppose a bank employee transfers Rs 500 from A's account to B's account.
This very simple and small transaction involves several low-level tasks.
A’s Account

Open Account(A)
Old.Balance=A.balance
New.Balance=Old.Balance – 500
A.balance= New.Balance
Close.Account(A).
B’s Account

Open Account(B)
Old.Balance=B.balance
New.Balance=Old.Balance + 500
B.balance= New.Balance
Close.Account(B).
The ACID Properties of a Transaction are as follows:

i. Atomicity :
This property states that a transaction must be treated as an atomic unit, that is, either all of its operations are executed or none.
There must be no state in a database where a transaction is left partially completed.
States should be defined either before the execution of the transaction or after the execution/abortion/failure of the transaction.
When an update occurs to a database, either all or none of the update becomes available to anyone beyond the user or application performing the update.
This update to the database is called a transaction and it either commits or aborts.
This means that only a fragment of the update cannot be placed into the database, should a problem occur with either the hardware or the software involved.

ii. Consistency:
Consistency is the ACID property that ensures that any changes to values in an instance are consistent with changes to other values in the same instance.
The database must remain in a consistent state after any transaction.
No transaction should have any adverse effect on the data residing in the database.
If the database was in a consistent state before the execution of a transaction, it must remain consistent after the execution of the transaction as well.
For example, we may have a table or a record on which two transaction are trying to read or write at the same time.
Careful mechanisms are created in order to prevent mismanagement of these sharable resources, so that there should not be any change in the way a transaction performs.
A transaction which deposits Rs 100/- to account A must deposit the same amount whether it is acting alone or in conjunction with another transaction that may be trying to deposit or withdraw some amount at the same time.

iii. Isolation :
In a database system where more than one transaction are being executed simultaneously and in parallel, the property of isolation states that all the transactions will be carried out and executed as if it is the only transaction in the system.
For example, user A withdraws $$100 and user B withdraws $250 from user Z’s account, which has a balance of $1000.
Since both A and B draw from Z’s account, one of the users is required to wait until the other user transaction is completed, avoiding inconsistent data.
Now, B can withdraw 250 from this $900 balance.

iv. Durability:
The database should be durable enough to hold all its latest updates even if the system fails or restarts.
If a transaction updates a chunk of data in a database and commits, then the database will hold the modified data.
If a transaction commits but the system fails before the data could be written on to the disk, then that data will be updated once the system springs back into action.
Features to consider for durability:
Recovery to the most recent successful commit after a database software failure.
Recovery to the most recent successful commit after an application software failure.
Recovery to the most recent successful commit after a CPU failure.
Recovery to the most recent successful backup after a disk failure.

BASE stands for -

Basic Availability - The database appears to work most of the time.
Soft-state - Stores don't have to be write-consistent, nor do different replicas have to be mutually consistent all the time.
Eventual consistency - Stores exhibit consistency at some later point (e.g., lazily at read time).
Therefore BASE relaxes consistency to allow the system to process request even in an inconsistent state.

ACID and BASE are consistency models for RDBMS and NoSQL respectively. ACID transactions are far more pessimistic i.e. they are more worried about data safety. In the NoSQL database world, ACID transactions are less fashionable as some databases have loosened the requirements for immediate consistency, data freshness and accuracy in order to gain other benefits, like scalability and resiliency.

Q2). What are the differences between paging and segmentation? (10 mark) 
Ans2)Paging & Segmentation are two contrasting approaches to virtual memory management. Virtual memory is when a process is not mapped into the actual physical memory space of a computer but to a virtual imaginary memory space. Every memory request from a process is mapped from the virtual space to physical space by the OS.

There are many reasons for using virtual memory in multitasked operating systems, one of the important ones is that you can have a virtual memory space that is bigger than the physical space by the operating system using disk as an extension of physical memory.

Many people have described this but in a segmented memory space the physical memory is divided into partitions of differing length and the operating system keeps track of what space has been allocated and the size of the segment. In a segmented system since the size of allocated memory is flexible the OS allocates the exact amount of space a process asks for.

In paged systems the physical memory is divided in blocks of equal size and a process is allocated a number of pages that is just larger than what it physically requires. So a little space is wasted at the end of the last page (except for the highly unlikely circumstance where the process requires exactly enough memory to fit into some number of pages).

When a process starts up it is allocated memory and when a process terminates it deallocates the space allocated to it. The OS keeps track of this. As the process runs and accesses memory the OS maps the virtually allocated memory space to the physical memory space. If a process requests access to a piece of virtual memory that is not currently mapped to physical space then one of the allocated chunks (a segment or a page) is written back to disk, freed up and allocated to the requesting process.

Because segmented memory is allocated in non-uniform chunks it has the problem of “fragmentation”. This is a long topic and I won’t describe it all here but in a nutshell if you keep allocating and deallocating memory chunks of different sized then eventually between two adjacent chunks of memory you will start building up small pieces of memory - these pieces are very small and usually not worth allocating on their own but collectively they start occupying a larger and larger amount of the overall memory. If the OS utilizes these small chunks there starts to get a huge number of segments allocated to a process (since each chunk is very small) and this leads to inefficiency. Because the more overall physical segments there are the more work the OS has to do.

Paged memory is free from that high level fragmentation because each chunk of memory is the same size. The only fragmentation is the internal fragmentation at the end of the last page which is unutilized. But that is not a big problem because it does not get bigger over time.


Q3).Which of the following condition is required for a deadlock to be possible? 
 a) mutual exclusion
 b) a process may hold allocated resources while awaiting assignment of other resources 
 c) no resource can be forcibly removed from a process holding it 
 d) all of the mentioned 

Ans3) d)-all of the mentioned.


  Q4).Which one of the following is the deadlock avoidance algorithm? 
   a) banker's algorithm
   b) round-robin algorithm 
   c) elevator algorithm 
   d) karn's algorithm
   
 Ans4) a)-banker's algorithm
 
 Q5) To avoid deadlock ____________ 
    a) there must be a fixed number of resources to allocate 
    b) resource allocation must be done only once
    c) all deadlocked processes must be aborted
    d) inversion technique can be used 
    
 Ans5) a)-there must be a fixed number of resources to allocate 



