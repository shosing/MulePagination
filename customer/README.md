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

API is implemented taking use of APIKIT which utilises the raml file developed to share the contract between the source and target.
APIKit helps in creating the routes for the flow based in the request query. This also helps in defining the global exception mapping defined in the raml file. 
Source of data in this API is an H2 database to which it retries to connect 3 times before raising an exception. Transformation of the message is achieved using Mule provided Transformer(Transform Message).

A Cache facility is available if the consumer wants to pull the data from the cache, this is achieved over /customer/{ID} resource which uses in memory store object to store the data with key as customerID. The data is only picked from cache if the request.header.cache-control ='only-if-cached'.

Pagination is allowed over /customer resource allowing prcoessing of large chunk of data processesing in chunks of records at a time instead of trying to process all the records in memory at the same time. 

Exception :
Error handling is done to catch the the exception and provide with the meaningful error message with http status codes for different types of errors. Error have been categorised in three different categories:
-Techincal: Any excpetion occuring while processing the request.
-Application: Error related to backend services.
-Validation: Error returned for validation on the input request.

Documentation

Studio includes a feature that enables you to easily export all the documentation you have recorded for your project. Whenever you want to share your project with others outside the Studio environment, you can export the project's documentation to print, email or share online. Studio's auto-generated documentation includes:

A visual diagram of the flows in your application
The XML configuration which corresponds to each flow in your application
The text you entered in the Notes tab of any building block in your flow
Follow the procedure to export auto-generated Studio documentation.

