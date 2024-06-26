
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

    - strong consistency: all reads see same up to date data
    - weak consistency: some reads might see stale data
    - eventual consistency: a specific form of weak consistency, within certain time, all reads eventually will see same up to date data

Q4: what is optimistic lock and pessimistic lock?

??? success "A4"
    Optimistic lock does not acquire locks on data resources until the transaction is ready to commit. Pessimistic lock acquires locks as soon as data resources are accessed.

Q5: what is database index?

??? success "A5"
    A data structure that provides quick lookup of one or multiple columns in a table. There are two types of index:
    
    - unique vs non-unique index: whether identical key values are allowed
    - clustered vs non-clustered index: wheter order of index is the same as order of rows
        - one table can only have one clustered index but could have multiple non-clustered index
        - query with non-clusterd index is slower than clustered index
        - non-clustered index is a separate entity referencing original table

### reference

- [Top 50 DBMS Interview Questions and Answers in 2024](https://www.simplilearn.com/dbms-interview-questions-and-answers-article)
- [SQL Interview Questions](https://www.interviewbit.com/sql-interview-questions/)