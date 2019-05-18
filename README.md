# Inventory-Data-Warehouse
This repository provides background on inventory transaction concepts, details about the snowflake schema to support inventory transaction cycles, and a data dictionary about the table design for the data warehouse. It also includes ETL process to integrate data using Pentaho Data Integration tool.

<h3>Basic ETL Process:</h3>
<p><b>ETL</b> stands for <b>Extract, Transform and Load</b>. An ETL tool extracts the data from different RDBMS source systems, transforms the data like applying calculations, concatenate, etc. and then load the data to Data Warehouse system. The data is loaded in the DW system in the form of dimension and fact tables.</p>

<div align="center">
    <img src="https://imgur.com/3CtbZtY.png" width="800px"</img> 
</div>

<h4>Extract</h4>
<p>A staging area is required during ETL load. There are various reasons why staging area is required.</p>
<p>The source systems are only available for specific period of time to extract data. This period of time is less than the total data-load time. Therefore, staging area allows you to extract the data from the source system and keeps it in the staging area before the time slot ends.</p>
<p>Staging area is required when you want to get the data from multiple data sources together or if you want to join two or more systems together. For example, you will not be able to perform a SQL query joining two tables from two physically different databases.</p>
<p>Data extractions’ time slot for different systems vary as per the time zone and operational hours.</p>
<p>Data extracted from source systems can be used in multiple data warehouse system, Operation Data stores, etc.</p>
<p>ETL allows you to perform complex transformations and requires extra area to store the data.</p>

<h4>Transform</h4>
<p>In data transformation, you apply a set of functions on extracted data to load it into the target system. Data, which does not require any transformation is known as direct move or pass through data.</p>
<p>You can apply different transformations on extracted data from the source system. For example, you can perform customized calculations. If you want sum-of-sales revenue and this is not in database, you can apply the SUM formula during transformation and load the data.</p>
<p>For example, if you have the first name and the last name in a table in different columns, you can use concatenate before loading.</p>

<h4>Load</h4>
<p>During Load phase, data is loaded into the end-target system and it can be a flat file or a Data Warehouse system.</p>

<h3>Pentaho Data Integration(PDI)</h3>
<p>Pentaho Data Integration (PDI) is a part of the Pentaho Open Source Business intelligence suite. It includes software for all aspects of supporting business decision making: the data warehouse managing utilities, data integration and analysis tools, software for managers, and data mining tools.</p>

<p>Pentaho Data Integration is well known for its ease of use and quick learning curve. PDI implements a metadata-driven approach which means that the development is based on specifying what to do, not how to do it.</p>

<p>Pentaho lets administrators and ETL developers create their own data manipulation jobs with a user-friendly graphical creator, and without entering a single line of code.</p>

<p>PDI uses a common, shared repository which enables remote <b>ETL</b> execution, facilitates teamwork, and simplifies the development process.</p>

<div align="center">
    <img src="https://imgur.com/KpUxPF5.png", width="100px", height="50px"></img> 
</div>

<h4>PDI components</h4>
<p>There are a few development tools for implementing ETL processes in Pentaho:<br>
  1.<b>Spoon</b>- a data modeling and development tool for ETL developers. Use it to create transformations (elementary data flows) and jobs (execution sequences of transformations and other jobs).<br>
  2.<b>Pan</b> - executes transformations modeled in Spoon.<br>
  3.<b>Kitchen</b> - executes jobs designed in Spoon.<br>
  4.<b>Carte</b> - a simple web server used for running and monitoring data integration tasks.
</p>

<h3>Steps to follow along this repository:</h3>

<b>1></b> Read <b>InventoryDW_project.doc</b> file. This files provides background on inventory transaction concepts, details about the snowflake schema to support inventory transaction cycles, and a data dictionary abou the table design for the data warehouse.

<b>2></b> Read <b>PentahoSetupExercise.docx</b> file. This file gives a basic idea of Pentaho Data Integration Tool and how to use it to create transformations with step by step instructions.
  
<b>3></b> Read <b>ETLWithPentaho.doc</b> file. This file provides ETL process experience with data integration tasks using Pentaho Data Integration Tool. There are tasks to perform some data cleaning operations on two data sources and then load the data into the fact table of the inventory data warehouse.

<b>4></b> Follow <b>DataIntegration.docx</b> file. This file gives a snapshot of this project in Pentaho Data Integration Tool with both Excel and Access data sources. 
