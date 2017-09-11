#Customer API - Implememting Caching and Pagination

This application demonstrate pagination and cache capability(requester based) applied on rest api.
Mule responds to end user calls submitted via Web browser on the below resources:

- /customers : retrieves list of customers.
- /customers?postcde=2135 : retrieves list of customers with postcode 2135
- /customer/1 - gets a sinfle customer from database with ID equal to 1.

This application allows customer to retrieves cached customer details based on the 'cache-control' passed in header request

Assumptions

This document assumes that you are familiar with Mule 101 and the Anypoint™ Studio interface. Basic understanding of cachin and pagination with Mule.

Set Up and Run the Example

Complete the following procedure to create, then run this example in your own instance of Anypoint Studio.

Open the customer application in Anypoint Studio from Anypoint Exchange. Do not run the application.

Run a H2 embedded database and change the credentials in the configuration.xml file.


In your application in Studio, click the Global Elements tab.

Double-click the NetSuite global element to open its Global Element Properties panel. Configure it as follows:

 



Hit your web browser with the following url: http://localhost:8081/customers?lastName=a to retrive a list of all customers having a last name starting with a. The data is stored in the HTML table.

Stop the Mule application by clicking the square, red terminate button in the Console.

How it Works

Using a single flow, this application accepts incoming HTTP requests, performs a query in NetSuite and delivers results to the end user.

The HTTP connector listens at http://localhost:8081/customers to incoming HTTP Get requests. The dynamic part of the NetSuite customer query is extracted from the url under lastName parameter key using Mule Expression Language. Next, the MEL Expression block iterates over the returned collection and prepares an HTML table body that is sent to a Parse Template component that injects it into the HTML template.

Documentation

Studio includes a feature that enables you to easily export all the documentation you have recorded for your project. Whenever you want to share your project with others outside the Studio environment, you can export the project's documentation to print, email or share online. Studio's auto-generated documentation includes:

A visual diagram of the flows in your application
The XML configuration which corresponds to each flow in your application
The text you entered in the Notes tab of any building block in your flow
Follow the procedure to export auto-generated Studio documentation.

Go Further

Learn more about Connection Testing.
Learn more about NetSuite Connector
Learn more about Anypoint DataWeave.
