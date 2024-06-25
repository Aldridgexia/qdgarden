
Q1: What is ACID?

??? success "A1"
    atomicity, consistency, isolation, durability.

Q2: What is CAP theorem?

??? success "A2"
    For consistency, availability and partition tolerance, only 2 out of 3 can be satisfied at the same time.

    CP sacrifices availability, AP sacrifices consistency, and CA is not possible in real life because network error is inevitable.

Q3: What is consistency model?

??? success "A3"
    Consistency model states that there are 3 types of consistency:

    - strong consistency: all reads have same update to date view
    - weak consistency: some reads might see stale view
    - eventual consistency: a specific form of weak consistency, with certain time, all reads eventually will have same update to date view

Q4: what is optimistic lock and pessimistic lock?

??? success "A4"
    Optimistic lock does not acquire locks on data resources until the transaction is ready to commit. pessimistic lock acquires locks as soon as data resources are accessed.

### reference

- [Top 50 DBMS Interview Questions and Answers in 2024](https://www.simplilearn.com/dbms-interview-questions-and-answers-article)
- [SQL Interview Questions](https://www.interviewbit.com/sql-interview-questions/)