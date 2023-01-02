# ACME Bank - API design exercise

These exercises are part of the [Anypoint Platform Development API Design](https://training.mulesoft.com/instructor-led-training/apdev-api-design) and [Anypoint Platform Architecture Solution Design](https://training.mulesoft.com/instructor-led-training/aparch-solution-design) training courses.

The goal is to design an API based on a set of requirements. Your task is to translate the requirements into an API design and document the design using the [RAML](http://raml.org) language.

**API Design Requirements for Individual Customers**  
"As a bank employee, supporting individual customers, I want to..."
```
[FR-001] Update bank account information
[FR-002] Replace a customer's information
[FR-003] Retrieve details on a particular incoming transfer
[FR-004] Retrieve a list of all transfers, both incoming and outgoing.
[FR-005] Retrieve a full list of customers
[FR-006] Add an account to a customer
[FR-007] Remove an account from a customer
[FR-008] Retrieve a list of a customer’s outgoing transfers
[FR-009] Create an outgoing transfer from a customer’s account to another account
[FR-010] Add a new customer
[FR-011] Retrieve a detailed account report
[FR-012] Get a list of accounts belonging to a particular customer
[FR-013] Retrieve a list of incoming transfers for a particular bank account
[FR-014] Retrieve details on a particular outgoing transfer
[FR-015] Retrieve details on a particular customer
```
**API Design Requirements for Companies**  
"As a bank employee, supporting companies (corporate accounts), I want to..."
```
[FR-101] Update bank account information for a corporate account
[FR-102] Replace a corporate accounts's information, including the primary contact within the company
[FR-103] Retrieve details on a particular incoming transfer
[FR-104] Retrieve a list of all transfers, both incoming and outgoing.
[FR-105] Retrieve a full list of corporate accounts
[FR-106] Add an account for a company
[FR-107] Remove an account for a company
[FR-108] Retrieve a list of a company’s outgoing transfers
[FR-109] Create an outgoing transfer from a company’s account to another account (individual, company, or government)
[FR-110] Add a new company
[FR-111] Retrieve a detailed account report for a pariticular company account
[FR-112] Get a list of accounts belonging to a particular company
[FR-113] Retrieve a list of incoming transfers for a particular company bank account
[FR-114] Retrieve details on a particular outgoing transfer
[FR-115] Retrieve details on a particular company
```

**API Design Requirements for Companies**  
"As a bank supporting companies (corporate accounts) and their accounts receivables systems, our automated systems want to..."
```
[FR-116] Orgininate a payment to a receiver - Get payment information from the buyer company's accounts payable system
[FR-117] Originate a payment to a recevier - Format data into an EDI standard ANSI 820 transaction set
[FR-117] Originate a payment to a receiver - Receive an EDI ANSI 820 file from the buying company's accounts payable system
[FR-118] Originate a payment to a receiver - Post ACH transaction to the Automated Clearninghouse Network 
[FR-119] Receive a payment from a buyer - Receive a payment and data from the ACH network on behalf of the receiving company
[FR-120] Receive a payment from a buyer - Credit the seller's account with a received and validated payment
[FR-121] Receive a payment from a buyer - Transmit the payment-related information in the ANSI 820 format to the seller's accounts receivable system (where the payment is automatically posted)
```

**Exercise 1: API basics**  
Start white-boarding the basics of the API. 
* Focus only on identifying *resources* and *methods*.
  * Remember: Resources = nouns, methods = HTTP verbs.
  * Distinguish resources between collections and members
* Do not use any modeling or definition language yet, just plain English.
* Remain at a high­ level (just resources and methodes)

Examples:
```
Resource: cars
    GET #Retrieve all cars in collection
    POST #Add a new car to the collection of cars

Resource: car
    GET #Get details of a specific car
    PUT #Update details of a specific car
    DELETE #Delete car from collection of cars
```

**Exercise 2: API definition with RAML**  
Based on the identified resources and operations, start working on a [RAML](http://raml.org) based API definition.  
* Create an actual API definition in the [Anypoint API Designer](https://www.mulesoft.com/platform/api/anypoint-designer), [API Workbench](http://apiworkbench.com/), or any other text editor of choice.
* For now, only add resources and methods.

**Exercise 3: API refinement**  
Use the identified resources and operations as a starting point and add the following elements:
* Documentation/API descriptions
* Media types
* HTTP response types
* Sample [responses](http://raml.org/developers/raml-100-tutorial#enter-responses). Assume all data will be in JSON format.

**Exercise 4: further API refinement**  
This exercise consists of refactoring the API design you created in the previous steps into a full ­fledged [RAML](http://raml.org) API:
* Identify possible [traits](http://raml.org/developers/raml-200-tutorial#traits) (reusable behavioral elements). Think of applying paging to large sets of data or searching options.
* Provide [schemas](http://raml.org/developers/raml-200-tutorial#extract-schemas) for data elements, such as API responses and request bodies. Hint: schemas can be [generated](http://jsonschema.net/#/) from your sample data.
* Review the structure and hierarchy of your API. Apply design recommendations and best practices.
* Extract all defined traits, samples and schemas into external files, which can be referenced using the [include](http://raml.org/developers/raml-200-tutorial#includes) keyword.

**Exercise 5: API refactoring**  
After completing exercise 4, which focused on extracting code duplicates to traits and external examples and schemas, make another pass of your API. Without the "clutter" of examples etc, see if you can refactor the new API by finding repetitions.
* Try to refactor code duplicates/repetitions into reusable elements, such as [resource types](http://raml.org/developers/raml-200-tutorial#resource-types).
* Try to minimize the amount of code in the main RAML file. How much can be extracted into separate resource types, preferably stored in external files?
