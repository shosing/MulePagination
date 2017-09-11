# MulePagination

#Customer API - Implememting Caching and Pagination

This application demonstrate pagination and cache capability(requester based) applied on rest api.
Mule responds to end user calls submitted via Web browser on the below resources:

- /customers : retrieves list of customers.
- /customers?postcde=2135 : retrieves list of customers with postcode 2135
- /customer/1 : gets a single customer from database with ID equal to 1.
                this process allows customer to retrieves cached customer details based on the 'cache-control' passed in header request.

Assumptions

This document assumes that you are familiar with Mule 101 and the Anypoint™ Studio interface. Basic understanding of caching and pagination with Mule.

Implementation




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
