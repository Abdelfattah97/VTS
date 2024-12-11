
# VTS (Design & Analysis)

## Index
- [**Vision**](#Vision)
- [**Domain**](#domain)
- [**Actors**](#actors)
- [**Use Cases**](#use-cases) 
- [**Requirements**](#requirements)
    - [Function Requirements](function-requirements)
    - [Non-Function Requirements](#non-function-requirements)
    - [Constraints ](#constraints)
   
##  Vision
The **Vacation Tracking System (VTS)** aims to manage the process of requesting vacations, managing the status of vacation requests, and handling approvals. The system also enforces necessary restrictions on new requests, ensuring compliance with company policies and enhancing efficiency in vacation management removing the complexity and delays of the manual process.

## Domain
The core problem revolves around the **complexity and inefficiencies** in the manual process of managing employee vacations. This manual approach creates challenges in ensuring compliance with company policies and employee-specific regulations. Additionally, coordinating vacation approvals without disrupting the business flow is difficult, as manual tracking can lead to workforce shortages in critical locations or positions. These issues can result in delays, miscommunication, and operational inefficiencies.


## Actors & Use cases
  [use-cases diagram](Design%26Analysis/use-cases/Use%20cases%20%26%20Actors-VTS.jpg)  
#### Actors
1. **Employee**: Makes and manages vacation time requests.    
2. **Manager**: Approves requests and award time.
3. **HR Clerk**: Manages Employee info & compliance to company policies.
4. **System Admin**: Backup System logs.

#### Use Cases
1. **Manage Time:** create, view , edit , withdraw or cancel vacation time requests. 
2. **Approve Requests:** Approves employees' pending requests. 
3. **Award Time:** Grants vacation time to employees.
4. **Edit Employee Record:** Managing and updating employees' information.
5. **Manage Location: Manage:** and update work locations and their restrictions.
6. **Manage Leave Categories:** Manage and update vacation categories and restrictions.
7. **Override Leave Records:** Changes any approved requests state.
8. **Back up System Logs:**  

## Requirements

### Function Requirements 
1. **Common**
	*user can:*
    1. login to the system 
3. **Manage Time**
	*employee can:*
    1. view his vacation requests
    2. make new vacation requests
    3. withdraw pending requests
    4. get notified on manager approval
    5. cancel approved requests  
 3. **Approve Requests** 
   *manager can:*
    1. get notified on subordinates' requests
    2. approve/disapprove subordinates' requests
  4. **Award Time**
	*manager can:*
       1. grant vacation time to employee 

     `other function requirements will be added later.`
   ___
### Non Function Requirements 
1. **security:** system ensures both authentication and authorization of clients  
2. **reliability:** system has high availability and expected functionality
3. **usability:** system is user-friendly and doesn't need having a programmatic background
   ___
### Constraints
1. integration with company's existing systems as HR system and employee database
    ___
## Entities