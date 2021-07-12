# Chapter 25 Stored Objects

Table of Contents

- 25.1 Defining Stored Programs
- 25.2 Using Stored Routines
- 25.3 Using Triggers
- 25.4 Using the Event Scheduler
- 25.5 Using Views
- 25.6 Stored Object Access Control
- 25.7 Stored Program Binary Logging
- 25.8 Restrictions on Stored Programs
- 25.9 Restrictions on Views

> This chapter discusses stored database objects that are defined in terms of SQL code that is stored on the server for later execution.

> Stored objects include these object types:

存储对象包括这些对象类型：

> Stored procedure: An object created with [CREATE PROCEDURE](https://dev.mysql.com/doc/refman/8.0/en/create-procedure.html) and invoked using the [CALL](https://dev.mysql.com/doc/refman/8.0/en/call.html) statement. A procedure does not have a return value but can modify its parameters for later inspection by the caller. It can also generate result sets to be returned to the client program.

- Stored procedure:

> Stored function: An object created with [CREATE FUNCTION](https://dev.mysql.com/doc/refman/8.0/en/create-function.html) and used much like a built-in function. You invoke it in an expression and it returns a value during expression evaluation.

- Stored function: 

> Trigger: An object created with [CREATE TRIGGER](https://dev.mysql.com/doc/refman/8.0/en/create-trigger.html) that is associated with a table. A trigger is activated when a particular event occurs for the table, such as an insert or update.

- Trigger: 

> Event: An object created with [CREATE EVENT](https://dev.mysql.com/doc/refman/8.0/en/create-event.html) and invoked by the server according to schedule.

- Event: 

> View: An object created with [CREATE VIEW](https://dev.mysql.com/doc/refman/8.0/en/create-view.html) that when referenced produces a result set. A view acts as a virtual table.

- View: 

> Terminology used in this document reflects the stored object hierarchy:

本文档中使用的术语反映了存储对象的层次结构:

> Stored routines include stored procedures and functions.

- 存储例程包含存储过程和函数

> Stored programs include stored routines, triggers, and events.

- 存储程序包含存储例程、触发器和事件

> Stored objects include stored programs and views.

- 存储对象包含存储程序和视图

> This chapter describes how to use stored objects. The following sections provide additional information about SQL syntax for statements related to these objects, and about object processing:

介绍如何使用存储对象。

以下部分提供了关于与这些对象相关的语句的 SQL 语法以及关于对象处理的附加信息:

> For each object type, there are CREATE, ALTER, and DROP statements that control which objects exist and how they are defined. See [Section 13.1, “Data Definition Statements”](https://dev.mysql.com/doc/refman/8.0/en/sql-data-definition-statements.html).

- 

> The CALL statement is used to invoke stored procedures. See [Section 13.2.1, “CALL Statement”](https://dev.mysql.com/doc/refman/8.0/en/call.html).

- 

> Stored program definitions include a body that may use compound statements, loops, conditionals, and declared variables. See [Section 13.6, “Compound Statement Syntax”](https://dev.mysql.com/doc/refman/8.0/en/sql-compound-statements.html).

- 

> Metadata changes to objects referred to by stored programs are detected and cause automatic reparsing of the affected statements when the program is next executed. For more information, see [Section 8.10.3, “Caching of Prepared Statements and Stored Programs”](https://dev.mysql.com/doc/refman/8.0/en/statement-caching.html).

- 