# Broadway High Level Components


In the Overview we saw the main Broadway concepts that make it a unique solution:
Stages as way to model work flow, Actors to model data flow and data inspection to
discover and manipulate complex data types.

There are a few other core capabilities that are important to the high level understanding of the Broadway system.


## Actor Input/Output Arguments

<table border="0" cellspacing="0" cellpadding="0">
<tr>
<td valign="top">
  <div>
    <p>Actors can get their input from three different sources:</p>
    <ul>
      <li>The output of a previous actor: the connecting lines between actors.</li>
      <li>A Constant value supplied by the user.</li>
      <li>An input argument to the flow (external).</li>

<p>When the actor executes, it is completely unaware to the source of its data.</p>
<p>Output arguments can also be exposed (external) as results of the flow execution. This makes the data available to the module that executed the Broadway flow.</p>
<p>In the image we can see the JavaScript actor obtaining the *script* input as a constant input, *a* is supplied by connecting to a previous actor, *b* is supplied as input to the entire flow (named externalNumber) and the result is exposed as *flowResult*.</p>
</div>
</td>
<td width="400">
<img src="images/input-output-arguments.png" width="400" />
</td>
</tr>
</table>

## Type System

Broadway actors pass data between them as Java objects. Virtually any data type can be passed between Actors but in practice most actors pass a subset of types that are supported by Broadway.  Supported Broadway types can be described by the Broadway Schema engine, can be displayed clearly by the Data Inspector and can be converted automatically to other supported types.
Broadway supports Arrays, Maps and Primitives such as String, Long, Real, Date, Boolean and Byte Array (binary data).
In addition Broadway has a robust type conversion system that automatically converts between types where possible, relieving the user of the burden of type conversion.

## Data Schema

The Broadway UI uses JSON Schemas to describe the data and enable designing data flows that leverage the known data structure.
Broadway can learn the schema by example. Just run the flow, and the meta data is automatically derived from the data. If you do have available JSON schemas to describe, it can be easily imported and edited.

<div align="center"><img src="images/overview_schema.png" height=400px/></div>

## Iterations

A common pattern of execution is to perform an iterative operation on a data set. For instance, performing some data transformation on a database result-set or traversing a JSON array obtained from a REST API.
The way Broadway deals with such cases is with the *Iterate* line (double dotted line below). This signals Broadway to perform the operation for every entry in the data set.

<div align="center"><img src="images/overview_iterate.png"></div>

## Stage Conditions

When stages, are split, an Actor can be designated to decide if a specific fork in the flow will be performed. The Actor can be a simple logical operator or an entire flow. Based on the result, Broadway will decide if the flow should be executed.
The *else* fork will will be executed if none of the other splits were executed.
<div align="center"><img src="images/overview_condition.png" height="350"></div>


## Actor Inheritance

Actors have an inheritance hierarchy. This enables activities such as pinning a constant value and reusing it across multiple flows, reusing some Actor logic such as JavaScript or SQL and even overriding the Actor Java implementation and tailoring it to a specific use case.  

## Transactions

Broadway has a builtin transaction management mechanism. Stages can be marked as part of a transaction. Any transactional resource the actors in these stages use, automatically becomes part of a transaction. Once the transactional stages are complete, the transaction is committed. In case of failure the transactions will be rolled back.
Transactions also take into account inner Broadway flows. If a transactional stage executes an inner Broadway flow, the flow automatically becomes part of the outer transaction.

## Error Handling

Every stage can be assigned an error handler. The error handler is an actor that can hold the logic to perform in case an error occurs as well as the decision whether the flow should continue or stop on that error. The error actor can be a simple logical check or an entire flow. The error handler has access to the

<div align="center"><img src="images/overview_error.png" height="200"></div>




[![Previous](/articles/images/Previous.png)](/articles/99_Broadway/01_broadway_overview.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/99_Broadway/03_broadway_actor.md)