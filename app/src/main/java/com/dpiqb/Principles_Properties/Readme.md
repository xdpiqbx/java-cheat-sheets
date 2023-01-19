# SOLID

## Single Responsibility Principle
a class should do one thing and therefore it should have only a single reason to change

## Open-Closed Principle
classes should be open for extension and closed to modification

## Liskov Substitution Principle
subclasses should be substitutable for their base classes

## Interface Segregation Principle
is about separating the interfaces

## Dependency Inversion Principle
classes should depend upon interfaces or abstract classes instead of concrete classes and functions

---
## Rule of three ("Three strikes and you refactor")

---
## KISS
Keep It Simple Stupid

---
## DRY
Don't Repeat Yourself

---
## AHA
Avoid Hasty Abstractions

---
## SSOT / SPOT

Single Source Of Truth / Single Point Of Truth

_every data element is mastered (or edited) in only one place_

---
## Composition Over Inheritance

objects with complex behaviors should contain instances of objects with individual behaviors

---
## Avoid Premature Optimization

---
## Law of Demeter (principle of least knowledge)

---
## Separation of Concerns (SoC)

is an abstract version of single responsibility. Program should be designed with different containers, which should not have access to each other. Each piece of code is completely independent.

---
## YAGNI

You Aren't Going to Need It

you should never code for functionality on the off chance that you may need something in the future (you shouldn't try to solve a problem that doesn't exist)

---
## Minimize coupling

---
## Document Your Code

---
# Transactions

## ACID properties of transactions

### Atomicity
**All changes to data are performed as if they are a single operation. That is, all the changes are performed, or none of them are.**

For example, in an application that transfers funds from one account to another, the atomicity property ensures that, if a debit is made successfully from one account, the corresponding credit is made to the other account.

### Consistency (Послідовність, Постійність, Узгодженість)
**Data is in a consistent state when a transaction starts and when it ends.**

For example, in an application that transfers funds from one account to another, the consistency property ensures that the total value of funds in both the accounts is the same at the start and end of each transaction.

### Isolation
**The intermediate state of a transaction is invisible to other transactions. As a result, transactions that run concurrently appear to be serialized.**

For example, in an application that transfers funds from one account to another, the isolation property ensures that another transaction sees the transferred funds in one account or the other, but not in both, nor in neither.

### Durability (Довговічність)
**After a transaction successfully completes, changes to data persist and are not undone, even in the event of a system failure.**

For example, in an application that transfers funds from one account to another, the durability property ensures that the changes made to each account will not be reversed.

---

# Transaction Isolation Level 

    1. Dirty reads
    2. Non-repeatable reads
    3. Phantom reads
    4. Serialization anomaly

 - `read-uncommitted` - Dirty reads, non-repeatable reads, and phantom reads can occur.
 - `read-committed` - Dirty reads are prevented; non-repeatable reads and phantom reads can occur.
 - `repeatable-read` - Dirty reads and non-repeatable reads are prevented; phantom reads can occur.
 - `serializable` - Dirty reads, non-repeatable reads and phantom reads are prevented.