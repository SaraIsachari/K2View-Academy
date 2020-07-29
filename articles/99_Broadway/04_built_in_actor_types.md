# Built-In Actor Types

Broadway has a large list of built-in [Actors](03_broadway_actor.md#actor-overview) that can be added to a flow in order to create various types of activities. Broadway's built-in Actors are split into categories, where each category includes several Actor types.

The below tables presents a list of Actor's categories with examples per each category. This is not an exhaustive list of Actors.

<table width="900pxl">
<tbody>
<tr>
<td width="80pxl">
<h3><strong>Category</strong></h3>
</td>
<td width="100pxl">
<h3><a id="user-content-category-description" class="anchor" href="04_built_in_actor_types.md#category-description" aria-hidden="true"></a><strong>Category Description</strong></h3>
</td>
<td width="720pxl">
<h3><a id="user-content-example-of-actors-per-category" class="anchor" href="04_built_in_actor_types.md#example-of-actors-per-category" aria-hidden="true"></a><strong>Example of Actors per Category</strong></h3>
</td>
</tr>
<tr>
<td style="vertical-align: top;" width="210">
<h4><a id="user-content-favorites" class="anchor" href="04_built_in_actor_types.md#favorites" aria-hidden="true"></a><strong>Favorites</strong></h4>
</td>
<td style="vertical-align: top;" width="433">
<p>Most commonly used Actors. Each Actor in the Favorites category also belongs to another category.</p>
</td>
<td style="vertical-align: top;" width="600">
<p><strong>Const</strong> Actor, copies the input value argument to the output value argument. A Const Actor can:</p>
<ul>
<li>Pass a constant value to the next Actor.</li>
<li>Receive its input from the output of a previous Actor and transfer it to the next Actor.</li>
<li>Receive an external flow argument and transfer it to the next Actor.</li>
</ul>
<strong>Concat</strong> Actor, concatenates an array of strings and joins them with the given delimiter. <strong><br /></strong><strong>JavaScript</strong> Actor, executes the Javascript provided in the script parameter. The script returns the value of the last line.</td>
</tr>
<tr>
<td style="vertical-align: top;" width="210">
<h4><a id="user-content-basic" class="anchor" href="04_built_in_actor_types.md#basic" aria-hidden="true"></a><strong>basic</strong></h4>
</td>
<td style="vertical-align: top;" width="433">
<p>Actors serving as the basic building blocks for creating the Broadway flow.</p>
</td>
<td style="vertical-align: top;" width="600">
<p><strong>ForLoop</strong> Actor, iterates over a range of numbers.</p>
<p><strong>Logger</strong> Actor, writes a message to the log file referencing entries from params and Actor inputs.</p>
<p><strong>InnerFlow</strong> Actor, executes a Broadway flow.</p>
<p><strong>LuFunction</strong> Actor, executes Studio function logic. Parameters for the function's execution are taken from input arguments or from the params input argument.</p>
<p><strong>Email</strong> Actor, sends an email using a given SMTP interface.</p>
</td>
</tr>
<tr>
<td style="vertical-align: top;" width="210">
<h4><a id="user-content-datetime" class="anchor" href="04_built_in_actor_types.md#datetime" aria-hidden="true"></a><strong>date/time</strong></h4>
</td>
<td style="vertical-align: top;" width="433">
<p>Various Date and Time manipulation functions, such as DateAdd, DateFormat or Now.</p>
</td>
<td width="600">
<p><strong>DateFormat</strong> Actor, formats a date into a string.</p>
<ul>
<li>Input values: Date, Output Format (following a predefined pattern) and Time Zone.</li>
<li>Initial format: yyyy-MM-dd HH:mm:ss.SSS.</li>
<li>Initial value of the time zone: UTC.</li>
<li>Output: a string.</li>
</ul>
<p>For example:</p>
<ul>
<li>To display a day of a year in the output, add <strong>D</strong> to the format.</li>
<li>To display a day of the week in the output, add<strong> E</strong> to the format.</li>
</ul>
</td>
</tr>
<tr>
<td style="vertical-align: top;" width="210">
<h4><a id="user-content-db" class="anchor" href="04_built_in_actor_types.md#db" aria-hidden="true"></a><strong>db</strong></h4>
</td>
<td style="vertical-align: top;" width="433">Actions to be performed on a DB interface, such as creating a new table, loading data or executing a DB command.</td>
<td style="width: 600px; vertical-align: top;" width="600">
<p><strong>DbCommand</strong> Actor, performs database commands on a DB command interface. The interface used as input can be:</p>
<ul>
<li>A JDBC URL.</li>
<li>Reference to a predefined interface.</li>
<li>Others, like the Schema, table name, fields definition, SQL dialect to use and append text appended to the CREATE command.</li>
</ul>
<p>The DbCommand can be used to create the WITH section where required.</p>
</td>
</tr>
<tr>
<td style="vertical-align: top;" width="210">
<h4><a id="user-content-logic" class="anchor" href="04_built_in_actor_types.md#logic" aria-hidden="true"></a><strong>logic</strong></h4>
</td>
<td style="vertical-align: top;" width="433">Logical operation on Actors<strong> A</strong> and <strong>B</strong> which returns a <strong>True</strong> or <strong>False</strong> boolean result.
<p>Broadway converts the following types of input parameters to booleans:</p>
<ul>
<li>Null/no input, False.</li>
<li>Integer/double, True if not 0.</li>
<li>String, True if not empty/0/False.</li>
<li>Array/Map, True if not empty.</li>
</ul>
</td>
<td style="width: 600px; vertical-align: top;" width="600">
<p><strong>And</strong> Actor, returns&nbsp;True&nbsp;if and only&nbsp;if both A and B&nbsp;are&nbsp;True. Both A and B must be boolean values or a value that can be converted to a boolean.&nbsp;&nbsp;</p>
<p><strong>Elvis</strong> Actor, returns&nbsp;A&nbsp;if converted to boolean is&nbsp;True. Otherwise returns B.</p>
<p><strong>IfElse</strong> Actor, includes the&nbsp;test&nbsp;input to be validated as either True or False.&nbsp;If test is True, return&nbsp;A, else return&nbsp;B.&nbsp;</p>
</td>
</tr>
<tr>
<td style="width: 210px; vertical-align: top;" width="210">
<h4><a id="user-content-math" class="anchor" href="04_built_in_actor_types.md#math" aria-hidden="true"></a><strong>math</strong></h4>
</td>
<td style="width: 433px; vertical-align: top;" width="433">Various mathematical functions, such as MathMax, MathMin, Aggregate.</td>
<td width="600">
<p><strong>Aggregate</strong> Actor, aggregates values.&nbsp;It receives a number or collection of numbers and calculates the Sum, Count, Average, Min and Max values of this collection. This Actor maintains its state across multiple loop iterations.&nbsp;&nbsp;</p>
<p><strong>MathDivMod</strong> Actor, returns the divisor and modulo factor of&nbsp;A&nbsp;and&nbsp;B.&nbsp;For example, if A=10 and B=3 then div=3 and mod=1.&nbsp;</p>
</td>
</tr>
<tr>
<td width="210">
<h4><a id="user-content-parsers" class="anchor" href="04_built_in_actor_types.md#parsers" aria-hidden="true"></a><strong>parsers</strong></h4>
</td>
<td width="433">Various parsers which can be received as input stream in different types of formats, for example, CSV, JSON or XML.</td>
<td width="600">
<p><strong>XmlParser</strong> Actor, receives an input stream represented via an iterable collection of blobs or strings. The parser runs until the end of the stream is detected. It returns a collection of parsed objects or a single object if Single is set to True.</p>
</td>
</tr>
<tr>
<td width="210">
<h4><a id="user-content-queue" class="anchor" href="04_built_in_actor_types.md#queue" aria-hidden="true"></a><strong>queue</strong></h4>
</td>
<td width="433">Publish / subscribe messages to the queue.</td>
<td style="width: 600px; vertical-align: top;" width="600">
<p><strong>Publish</strong> Actor, publlishes messages using a message broker.&nbsp;The inputs are:</p>
<ul>
<li>Broker interface to use.</li>
<li>Topic to publish to.</li>
<li>Message.&nbsp;</li>
</ul>
</td>
</tr>
<tr>
<td width="210">
<h4><a id="user-content-streams" class="anchor" href="04_built_in_actor_types.md#streams" aria-hidden="true"></a><strong>streams</strong></h4>
</td>
<td width="433">Various stream manipulation functions, such as Compress, FileRead or Http.</td>
<td width="600">
<p><strong>FileRead</strong> Actor, reads data from a file given an interface and path. The file is opened lazily when an Actor reads the output stream. Once the file has been fully read, it is closed. If the file is not fully read, it is closed at the end of the flow.</p>
<p><strong>Http</strong> Actor, sends a request to a Web Server. Supports streaming payload and results and sending and receiving header parameters.</p>
</td>
</tr>
<tr>
<td style="vertical-align: top;" width="210">
<h4><a id="user-content-strings" class="anchor" href="04_built_in_actor_types.md#strings" aria-hidden="true"></a><strong>strings</strong></h4>
</td>
<td style="vertical-align: top;" width="433">
<p>Various string manipulation functions, such as Concat, Split or Trim.</p>
<p>Graphit and JsonStringify Actors are also included in this category.</p>
</td>
<td width="600">
<p><strong>Regex</strong> Actor, finds sub-strings in an input string using a regular expression. The Actor tries to find all matches of the pattern within the input string and return them. When using matching groups, the result is the content of the matching group instead of the full match. For example, in the ABCDEF string, the C.E pattern returns [CDE], whereas C(.)E returns [D].</p>
<p><strong>Graphit</strong> Actor, executes Graphit logic for data serialization. Parameters for the Graphit execution are taken from input arguments or from the params input argument. The inputs are:</p>
<ul>
<li>LU containing the Graphit file (initial value = k2_ws).</li>
<li>Graphit filename.</li>
<li>Required output format (inital value = JSON).</li>
<li>Parameters for Graphit execution.</li>
</ul>
<p>The Actor first looks at the input parameters (first level) and, if it is not found there, looks at the params input argument.</p>
</td>
</tr>
<tr>
<td style="vertical-align: top;" width="210">
<h4><a id="user-content-system" class="anchor" href="04_built_in_actor_types.md#system" aria-hidden="true"></a><strong>system</strong></h4>
</td>
<td style="vertical-align: top;" w idth="433">System processes and commands to be performed in the file system. For example: Sych as copy, List or Remove.&nbsp;</td>
<td width="600">
<p><strong>cp</strong> Actor, copies a file. The interface used as input can be:</p>
<ul>
<li>JDBC URL.</li>
<li>Reference to a predefined interface.</li>
<li>Path of the sourcefile (from).</li>
<li>Destination (to).</li>
</ul>
<p>The output is a number of affected files.</p>
</td>
</tr>
</tbody>
</table>

[![Previous](/articles/images/Previous.png)](03_broadway_actor_window.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](05_data_types.md)