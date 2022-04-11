# **Web API with the Scala Play Framework** !!!

Simple CRUD application using Play framework (and Scala) for a REST API and MySQL backend.

## Setup

This project is using a lot of tools. All should be installed before starting to run it.



- [Scala 2.13.8](http://www.scala-lang.org/)
- [Play framework 2.8.15](http://www.playframework.com/)
- [Postman ](https://www.postman.com/)(` for API (JSON)`)
- [MySQL](https://dev.mysql.com/doc/)
- [JDK Version 1.8](https://www.oracle.com/in/java/technologies/javase/javase8-archive-downloads.html) (`use above 1.8 jdk version`)

## Play Framework Setup



We’re going to take a look at the [Play Framework](https://www.playframework.com/) with Scala. We’ll learn how to set up the Play Framework, use the development tools to generate our  project, and how to implement our own features.

## Command-line Tools

- sbt new playframework/play-scala-seed.g8
- name [play-scala-seed]: (`Enter your Project Name`)
- organization [com.example]: (`com.qbrainx`)
- play_version [2.8.15]:   (`Enter your preferred play_version`)
- scala_version [2.13.8]:  (`Enter your preferred scala_version`)

##  Project Structure
**Load the project code into the IDE and look at the directory structure**.

Project directory, we see four directories created by the _sbt_ template: _app/controllers, app/views, conf_, and _public

-   The  _controllers_  directory is where we will store our Scala code
-   The  _views_  directory is where we’ll save our **HTML templates**
-   The  _conf_  directory contains our router configuration which maps a request URL to a specific class and method
-   Finally, the  _public_  directory contains the static content served by the **Play Framework server**

# SBT Setup Dependencies

`libraryDependencies += "com.typesafe.play" %% "play-slick" % "5.0.0"  `

`libraryDependencies += "com.typesafe.play" %% "play-slick-evolutions" % "5.0.0"`

`libraryDependencies += "mysql" % "mysql-connector-java" % "8.0.28"`

# plugins.sbt

`addSbtPlugin("com.typesafe.play" % "sbt-plugin" % "2.8.15")  `

`addSbtPlugin("org.foundweekends.giter8" % "sbt-giter8-scaffold" % "0.13.1")`


# application.conf

slick.dbs.default.profile = "slick.jdbc.MySQLProfile$"  
slick.dbs.default.db.driver = "com.mysql.cj.jdbc.Driver"  
slick.dbs.default.db.url = "jdbc:mysql://localhost/---database name ---"  
slick.dbs.default.db.user = "---username---"  
slick.dbs.default.db.password="---password---"

# controllers mapping



<table>
	<thead>
		<tr>
			<th>API</th>
			<th>Description</th>
			<th>Request body</th>
			<th>Response body</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>GET /api/user      </td>
			<td>Get all  items</td>
			<td>None</td>
			<td>An array of to-do items</td>
		</tr>
		<tr>
			<td>GET /api/user      /:id</td>
			<td>Get an item by ID</td>
			<td>None</td>
			<td>To-do item</td>
		</tr>
		<tr>
			<td>POST /api/user      /add</td>
			<td>Add a new item</td>
			<td>To-do item</td>
			<td>To-do item</td>
		</tr>
		<tr>
			<td>PUT /api/user      /:id</td>
			<td>Update an existing item</td>
			<td>To-do item</td>
			<td>None</td>
		</tr>
		<tr>
			<td>DELETE /api/user      /:id</td>
			<td>Delete an item</td>
			<td>None</td>
			<td>None</td>
		</tr>
	</tbody>
</table>



## **Test CRUD with Postman**

-   Create a new request.
-   Set the HTTP method to POST
-   Select the **Body** tab.
-   Select the **raw** radio button.
-   Set the type to **JSON (application/json)**.
-   In the request body enter JSON for a to-do item:


