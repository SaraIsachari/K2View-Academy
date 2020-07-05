# Graphit Overview

A Fabric tool, Graphit is used create dynamic CSV, XML and JSON documents and is very useful for generating Fabric [Web Service](/articles/15_web_services/01_web_services_overview.md) responses. The content of a response is defined during its execution, either according to specific parameters relevant to the specific Web Service call and the employed [LUI](/articles/01_fabric_overview/02_fabric_glossary.md#lui), or by retrieving dynamic information from other databases or interfaces.

### Graphit Main Features

Graphit has the following main features: 
- Supports the creation of dynamic CSV, XML and JSON documents. 
- Accepts external input as variables. 
- Usage of variables in queries.
- Executes queries on an LUDB, iterates over the results and uses the returned values to create the response document.
- Executes queries on interfaces other than Fabric.
- Supports prepared statements.
- Supports XML and JSON hierarchy, including queries in inner hierarchy levels. Usage of outer level query result as an argument. 
- Recursively generates nested tags and structures.
- Enables tailoring the format of a value and efining whether to generate a tag when the values are null or empty
 



[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/15_web_services/Graphit/02_create_and_edit_a_graphit_file.md)

