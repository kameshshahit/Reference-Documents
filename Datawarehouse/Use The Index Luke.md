## Preface  
## Anatomy of an Index 
## The Where Clause
## Performance and Scalability
>### Performance Impacts of Data Volume
>### Performance Impacts of System Load
>### Response Time, Throughput and Horizontal Scalability
>**Note:**
> - Performance has two dimensions: response time and throughput.
> - More hardware will typically not improve query response time.
> - Proper indexing is the best way to improve query response time.
## The Join Operaitons
>### Nested Loops
> - Complexity: O(NlogM)
> - Used usually when one table is significantly small
> - The larger table has an index which allows seeking it using the join key
>### Hash Join
> - Complexity: O(N*hc+M*hm+J)
> - Last-resort join type
> - Uses a hash table and a dynamic hash match function to match rows
> - Hash joins do not need indexes on the join predicates. They use the hash table instead.
> - A hash join uses indexes only if the index supports the independent predicates.
> - Reduce the hash table size to improve performance; either horizontally (less rows) or vertically (less columns).
> - Hash joins cannot perform joins that have range conditions in the join predicates (theta joins).
>### Sort Merge
> - Complexity: O(N+M)
> - Both inputs are sorted on the join key
> - An equality operator is used
> - Excellent for very large tables

markdown [editor](https://stackedit.io/editor)
>**Summary:**
> - Usage of bind parameters in Query optimize the query execution as Query does not create new execution plan each time and try to utilize the existing one
> - 
