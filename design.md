


# VTS (Design & Analysis)

## Index

- [**Vision**](#vision)
- [**Domain**](#domain)
- [**Actors**](#actors)
- [**Use Cases**](#use-cases) 
- [**Flowcharts**](#flowcharts)
- [**Requirements**](#requirements)
    - [Function Requirements](#function-requirements)
    - [Non-Function Requirements](#non-function-requirements)
    - [Constraints ](#constraints)
 - [**Entities & Data Model**](#entities)
 - [**Sequence Diagrams**](#sequence-diagrams)
##  Vision
The **Vacation Tracking System (VTS)** aims to manage the process of requesting vacations, managing the status of vacation requests, and handling approvals. The system also enforces necessary restrictions on new requests, ensuring compliance with company policies and enhancing efficiency in vacation management removing the complexity and delays of the manual process.

## Domain
The Domain is centered around managment of employee vacation time.
As the problem revolves around the **complexity and inefficiencies** in the manual process of managing employee vacations. This manual approach creates challenges in ensuring compliance with company policies and employee-specific regulations. Additionally, coordinating vacation approvals without disrupting the business flow is difficult, as manual tracking can lead to workforce shortages in critical locations or positions. These issues can result in delays, miscommunication, and operational inefficiencies.

## Actors & Use cases
<p align=center>
<img src="Design%26Analysis/use-cases/Use%20cases%20%26%20Actors-VTS.jpg" width="60%"/>
</p> 

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
8. **Back up System Logs**  

### Flowcharts

- **Use case:** Manage Time 
- **Actor:** Employee
   - **Make Request (Main Flow):**
	<p align=center>
	<img src="Design%26Analysis/flowcharts/Flowchart-RequestVacationTime-VTS.jpg" width="60%"/>
	</p>

   - **Withdraw Request (Alt Flow):**
	<p align=center>
	<img src="Design%26Analysis/flowcharts/Flowchart-WithdrawRequest-VTS.jpg" width="50%"/>
	</p>

  - **Cancel Request (Alt Flow):**
	<p align=center>
	<img src="Design%26Analysis/flowcharts/Flowchart-CancelRequest-VTS.jpg" width="65%"/>
	</p>

## Requirements

### Function Requirements 
1. **Common Functions**
	*user can:*
    1. SSO Login
3. **Manage Time**
	*employee can:*
    1. view his vacation requests
    2. make new vacation requests
    3. withdraw pending requests
    4. get notified on manager approval
    5. cancel approved requests 
 3. **Approve Requests** 
   *manager can:*
    1. get email notification on subordinates' requests
    2. approve/disapprove subordinates' requests
  4. **Award Time**
	*manager can:*
       1. grant vacation time to employee 

     ***other function requirements will be added later.***
     ___ 
   ### Non Function Requirements 
1. **security:** system ensures both authentication and authorization of clients  
2. **reliability:** system has high availability and expected functionality
3. **usability:** system is user-friendly and doesn't need having a programmatic background
   ___
### Constraints
1. integration with company's existing systems as HR system.
2. single-sign-on
3. user experience
    ___

## Sequence Diagrams
#### Authentication Seq Diagram

 > the diagram illustrates the sequence of Authenticating a VTS visitor through the main protal using the SSO approach.

 1. User inputs his credentials
 2. Portal Verifies the user credentials through the auth server
 3. Auth Server verfies a visitor is an authorized user and provides an access token
 4. Portal redirects user to VTS and includes the token 
 5. VTS uses the access token to verify that the user is authenticated
 6. VTS Returns Home page to user or redirects him to portal login

 

   ```mermaid
   sequenceDiagram

   title Authentication Sequence Diagram

   Actor User
   participant Portal
   participant VTS
   participant Auth Server

   activate User
   User->>Portal:Login
   activate Portal
   Portal->>Auth Server:Request Authentication
   activate Auth Server
   Auth Server-->>Portal:Access Token(Authenticated)
   deactivate Auth Server

   Portal-->>User:Systems links & token
   User->>Portal:Chooses VTS 
   Portal->>VTS:Redirect to VTS & Includes the token
   activate VTS
   deactivate Portal
   VTS->>Auth Server:Verify token
   activate Auth Server
   Auth Server-->>VTS:Authenticated (ok)| UnAuthorized
   deactivate Auth Server
   alt Authenticated
   activate VTS
   VTS->>VTS:Generate HTML
   deactivate VTS
   VTS -->> User:HTML(ex:VTS HOME PAGE)
   else UnAuthorized

   VTS-->>User: Redirect to portal(Login)
   Deactivate VTS
   end
   Deactivate User
   ```
   

## Entities