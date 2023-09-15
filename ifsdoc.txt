About EAC Workbench
The EAC Workbench can be used to predict EAC values for a Project Forecast in a structured manner, using system values as well as user entered values. EAC Workbench can be used to calculate both cost and revenue-related EAC, using the Project's defined Base Currency.

To start the calculation, create a Project Forecast, and then use the connected EAC Workbench to calculate EAC and ETC values. Finally, copy the values to the Project Forecast to continue with the Budgeting and Forecasting flow in IFS Cloud.

EAC Workbench uses the Active Budget of the Project when the Project Forecast was created, as the basis for the calculation. Budget Transfers between forecast lines and Estimated Budget Changes provide the flexibility to adjust the budget values for each forecast line by calculating the Adjusted Budget This Forecast value. If there are no Budget Transfers or Estimated Budget Changes, Adjusted Budget This Forecast value will be as same as the Active Budget when the Project Forecast was created.

Adjusted Budget This Forecast is calculated as follows:

Adjusted Budget This Forecast = Active Budget (when the Project Forecast was created) + Budget Transfers + Estimated Budget Changes

Budget Transfer
The Budget Transfer feature allows for the redistribution of the Active Budget amount (the Active Budget at the time of Project Forecast creation) between forecast lines within the same Forecast, while keeping the total Active Budget value for the Project unchanged. This feature only affects the Adjusted Budget This Forecast value of the selected Forecast lines and has no impact on the Active Budget of the Project.

Estimated Budget Change
Estimated Budget Changes can be entered to a Forecast line to provide for future anticipated changes in the Active Budget, thus calculating an accurate Adjusted Budget This Forecast for the selected Forecast line. An Estimated Budget Change can be positive or negative. This has no effect on the Active Budget of the Project, only affects the Adjusted Budget This Forecast value in the EAC workbench.

Estimated Future Commitment
Estimated Future Commitment Adjustments can be entered manually to adjust the EAC according to changes anticipated in future like contingency or an expected rate change. It also can be used to forecast for miscellaneous work, not covered by anything else. An Estimated Future Commitment can be positive or negative.

Estimated Future Commitment is calculated as follows:

Unplanned Cost = Adjusted Budget This Forecast - Planned Cost/ Revenue + CCO Value included in Planned Cost/ Revenue

Estimated Future Commitments (EFC) = Unplanned Cost/ Revenue + Estimated Future Commitment Adjustments

Manage Change Order Connection
Contract Change Order values can be used to predict better values for EAC. Contract Change Orders in any status can be connected to an EAC Workbench created for that particular Project. Contract Change Order values will be displayed based on their status in the Manage Contract Change Order assistant. If the Change Order agreement is already updated into the Sub Contract/ Sales Contract, it would be considered for the calculation via Planned Cost/ Revenue of the Sub Contract/ Sales Contract obtained through a snapshot. If it is not yet updated, then the Contract Change Order values can be retrieved using Manage Change Order Connections.

EAC value on EAC Workbench is calculated as follows:

EAC = Planned Cost/ Revenue + CCO Value not included in Planned Cost/ Revenue + Estimated Future Commitments (EFC)

In return, ETC is calculated using:

EAC = Total Committed Cost + ETC

Where Total Committed Cost is:

Total Committed Cost = Used Cost + Committed Cost

In case of Revenue Forecasting:

EAC = Preliminary Revenue + Posted Revenue + ETC

Once the EAC values are finalized, EAC can be copied to the connected Project Forecast using Copy EAC to Forecast action command.

Pages
EAC Workbench

Activity Diagrams

Milestone Template
Milestone templates are templates created to indicate the progress of a design object. A milestone template can consist of one or more milestones and each milestone will have a pre-defined progress and duration percentage value. The progress value defined on the milestone will represent the progress of development of a design object connected to the particular milestone and the duration value defined on the milestone will represent the percentage of the total hours used by the design object to reach the particular milestone. For a particular milestone on the milestone template, you can also define a design status to update the cumulative progress and duration of a design object connected to this milestone template and number, when the defined design status action is performed. For example, select the Set Completed status for a milestone with a cumulative progress percentage value of 100%.

A milestone template and an appropriate milestone is connected to a design object, at a point in time, to establish its progress at that particular point. Milestone templates can be connected to a design object class or to a design object itself. The progress of a design object can be established either by manually selecting an existing milestone template and a milestone number for the design object or by assigning a default milestone template and an initial milestone to a design object class. As a result, new design objects created with this design object class will automatically receive the milestone template and milestone values, and the progress of the design object is activated.

Inter-Site Address Handling
This document describes the specific use of the following fields within the inter-site order feature. The fields below, are also sometimes referred to as the EAN location number.

Company's Own Address ID
Customer's Own Address ID 
Basic data for the aforesaid fields, must be maintained as follows:

Enter the Company's Own Address ID on the Company/Address tab.
Enter the Customer's Own Address ID on the Customer/Address tab.
When sourcing an external customer order internally, there are two different scenarios depending on the material flow.

Transit delivery: When the internal supply site sends goods to the demand site, and this site in turn sends them further to the end customer.
Direct delivery: When the internal supply site sends goods directly to the end customer.

Internal Purchase Direct
A customer orders goods from site A. Site A does not have available inventory, but places an internal purchase order with a direct delivery of goods. The goods will be sent from site B to the external customer. In this situation, site A is the ordering customer while the external customer is the deliver-to customer. To identify the deliver-to address (the external customer's address) at site B when the internal customer order is being created, the external customer's address must have the Customer's Own Address ID field set in the customer catalogue. This makes it possible for the system to find the correct address even if the two sites operate in different database instances. The address is a known address and will not be selected as a single occurrence.

When the external customer order is released at site A and the internal purchase order is created, the values in the Deliver-to-Customer and the Customer's Own Address ID fields are saved on the purchase order line. These two fields, among other information, are then transferred via message handling to the supply site, site B in the example.

Internal Purchase Transit
A customer orders goods from site A. Site A does not have available inventory but places an internal purchase order with a transit delivery of goods. The goods will be sent from site B to site A, and then from site A to the external customer. In this situation, site A is the ordering customer as well as the deliver-to customer. On the internal purchase order, the ordering customer is a site, and it is the site's delivery address that will be retrieved as the deliver-to address. However, on the internal customer order, the deliver-to address is retrieved from the customer catalogue for site A as the customer. To identify the deliver-to address (the internal customer's address) at site B when the internal customer order is being created, the internal customer's address must have set a value in the Customer's Own Address ID field in the customer catalogue. This must be exactly the same ID as in the Company's Own Address ID field for site A. In this way, it is possible for the system to find a link between the site's address on the purchase order and the internal customer's address on the internal customer order. The address is a known address and will not be selected as a single occurrence.

Note: This link between the two addresses is also important in order to find the correct route between site B and site A (if any). This way, the order promising towards the external customer will be based on the correct route departure date. 

Internal Purchase
An internal purchase order does not necessarily have to originate from a customer order; it can be entered directly as an internal purchase order. However, this scenario works exactly in the same way as the transit scenario described above, but the starting point is the purchase order instead of the customer order.

Inter-Site Profitability
General
Each site within a company can have its own profit center. Use the Inter-site Profitability feature on the Company/Supply Chain Information/Sales tab to perform the profitability analysis on all the sites within a company. By ordering profit center reports, the financial managers or site managers can study profit/loss performance at site level.

The inter-site profitability analysis is based on internal customer orders delivered to the other sites that belong to the same company as the supplying site, If the Inter-Site Profitability option on the Company/Supply Chain Information/Sales tab has been selected, the transactions and posting types dedicated only to inter-site profitability will be triggered when internal customer orders are delivered. Parts moved to another site belonging to the same company using the Transport Task or Move Inventory Part pages will not generate inter-site price postings.

A prerequisite to analyzing sites as profit centers is that internal prices must have been used and controlled on the supplying sites. The normal price search used on customer orders will be used to find an internal price. The sales price on the internal customer order line will be used to post internal revenue on the supply site and the internal revenue received on the demand site. The inventory part value on the supply site will be used when posting internal cost of sale on the supply site and also when posting the internal cost of sale received on the demand site. 
Therefore, it is the delivery of the customer order on the supply site that triggers the inter-site profitability transactions on both the supply site and the demand site. You do not wait for the goods to be received on the demand site for the internal purchase to be registered, i.e., as soon as something is sold, it is also purchased by the other site. This follows how the inventory value is transferred to the demand site as soon as the delivery is made from supply site.

You can indicate whether to use the inter-site profitability feature for a company. By default, it is not used for new companies. Regardless of whether it is used, the inventory valuation is not affected in any way. Inventory valuation and the movement of inventory values between sites are executed in the same way regardless of inter-site profitability usage.

It is important to pay attention as to when the use of this feature is started. Starting it on in the middle of a period does not give the user any valuable information about the inter-site profitability of that period. Preferably it should be started between periods, e.g. at month-end or year-end.

If the Inter-site Profitability function has been selected on the Company/Supply Chain Information/Sales tab, the new transactions will be created automatically. In Posting Control page, posting types must be set up for the postings used by the inter-site profitability transactions. Otherwise, the postings will contain errors. There is no default setup made for the inter-site profitability posting control. Typically control type Site will be used in order to differentiate the inter-site profitability postings.

Example
Scenario:

Site X purchases goods from an external supplier. Inventory value for the part on site X is 3.
Site Y purchases 1 part of the goods from site X. Sales price from site X to site Y is 9. Inventory value for the part on site Y is 5. (Site Y is the demand site and site X is the supply site.)
An external customer purchases 1 part of the goods from site Y. Sales price from site Y to external customer is 10.

None Inventory Parts
Non-inventory parts will not generate any inter-site price postings. The reason for this is that purchase prices for non-inventory parts have no correlation to the non-inventory sales part cost, and no cost differences are booked.

Control Types
All eight inter-site profitability postings occur at the same time (when an internal customer order is delivered), but the transactions and corresponding system events belong to different sites. The INTREV and INTCOS transactions are posted on the supply site. The INTREVR and INTCOSR transactions are posted on the demand site. INTREVR and INTCOSR belong to the demand site, but they are created and marked by an order reference existing on the supply site. The control type is identified by the site on the transaction; and not by the site to which the order reference belongs. 

The following example explains this further:
On the supply site, a CO1 internal customer order will be registered for the demand site of inventory part X. Part X belongs to the product family A on the supply site, and the product family B on the demand site. The inter-site postings should be controlled using the control type Product Family. When the delivery is made for CO1, postings will be made on both the demand and supply sites. The postings on the supply site will get the control type A. The postings on the demand site will get the control type B.

Control types that are not available on both the demand and supply sites cannot be used as control types for the inter-site postings. For example, the Sales Group control type is not available because the sales group can only be found on the supply site and not on the demand site.

Corrective Inter-Site Price Postings
If the price on an internal customer order line was not correct at the time of the delivery, it is possible to adjust the inter-site postings afterwards. By using the Create Corrective Inter-site Postings operation on the customer order line, it is possible to increase or decrease the internal revenue generated for a customer order line.

To create corrective inter-site price postings, a weighted average price is calculated for all previously booked inter-site price postings for the customer order line. The weighted average price is compared with the entered correct price, which gives the price difference to be posted. If the price difference is positive, both the inter-site revenue on the supply site and the internal purchase debts on the demand site will be increased. If the price difference is negative, both the inter-site revenue on the supply site and the internal purchase debts on the demand site will be decreased.

Return for Rework
When return for rework is done on the demand site, those parts are later received on a return material authorization on the supply site. After the parts have been reworked, they can be delivered again to the demand site on a new internal customer order. If corrective inter-site postings are not applied manually, the reworked parts will get inter-site price bookings posted twice (first for the original delivery and second when delivering the reworked parts).

If the rework should be paid for by the supply site or the demand site is often an open discussion. The demand site might have to pay for all the rework because they had not communicated their demands on the part design well enough; or it could be that the supply site should pay for the rework because they have delivered poor quality goods. Therefore, generating internal profit (which is the case if the internal revenue is greater than the internal cost of sale) on returned order lines might not always be considered correct. Therefore, the Create Corrective Inter-site Price Postings function is also available on return material authorization lines. To use this function, the return material authorization line must be credit approved and connected to a customer order line. By using corrective inter-site price postings, it is possible to ensure that each return is considered as appropriate by the profit center analysis. The internal revenue can be adjusted so that the returned order lines give the correct internal profit. The internal cost of sale cannot be adjusted.

Description of Set Up Basic Data Cash Flow Analysis
Description of process
The Description of Set Up Basic Data Cash Flow Analysis process describes BDR (Basic Data Required) for running the Cash Flow Analysis process. Check or/and add information before you start working with the process. Click the action symbols in the process to view detailed activity descriptions. To be able to run the Cash Flow Analysis process the IFS/Cash Flow Analysis module must be installed.

Check and add information as described below:

Check that the company is entered as per the instructions in Define System Basics.

The currencies you are using must be entered in IFS/Accounting Rules before you can start using the Cash Flow Analysis process. Be sure there are currency codes, currency rates, and currency types entered.

Add if preferable Cash Flow Sources, and Cash Flow Types if you need to select on additional search terms when you print cash flow exposure reports. There are a number of predefined Cash Flow Sources that refers to processes within IFS Cloud from where information can be transferred. If IFS Contract Management is installed you can obtain information on customer orders and purchase orders referring to these Cash Flow Sources. IFS/Payment is another predefined Cash Flow Source from where information on outstanding customer and supplier balances can be retrieved. IFS Payment can also contain information on balances at the company's various payment institutes. These balances can also be transferred and included in cash flow analysis.

The predefined Cash Flow Types are created automatically when a company is created. The Cash Flow Types are references used when information is retrieved to the Cash Flow Analysis process from other IFS Cloud. Cash Flow Types are used for defining various cash flows. The predefined Cash Flow Types cannot be deleted nor changed. You can add new Cash Flow Types at any time. It does not necessarily have to be at system start up.

Information concerning the contents of the Cash Flow Analysis process itself is found in the main process Cash Flow Analysis. Click the notes symbol Description of Cash Flow Analysis to view the text. The BDR (Basic Data Required) is also stated as a reminder when you click the requirement symbol.

Description of Set Up Basic Data Mixed Payment
Description of process
The Description of Set Up Basic Data Mixed Payment process describes BDR (Basic Data Required) for running the Mixed Payment process. Check or/and add information before you start working with the process.

If the Mixed Payment process is to be used for entry of customer and supplier payments you should enter and check information according to the Description of Set up Basic Data Accounts Receivable and the Description of Set up Basic Data Accounts Payable. To be able to run the Mixed Payment process, IFS/Invoice and IFS/Payment must be installed.

To use the Mixed Payment process for transactions with no link to the accounts receivable or accounts payable follow the workflow in this process. Click the action symbols in the process to view detailed activity descriptions.

Check and add information as described below:

Check that the company you want to work with is entered as per the instructions in Define System Basics.

Check or modify posting control in IFS/Accounting Rules. The posting control is defined in Set up Basic Data Accounts Receivable. In the posting control you specify which accounts and other code parts are to be used for automatic transactions generated when payments are entered.

Enter Payment Institutes and Cash Accounts to be used. Add, if necessary cash account Posting Control information.

Check and/or modify the Payment Types, Payment Series and Payment Number Series created when the company was created.

Information concerning the contents of the Mixed Payment process itself is found in the main process Mixed Payment. Click the notes symbol Description of Mixed Payment to view the text. The BDR (Basic Data Required) is also stated as a reminder when you click the requirement symbol.

About Automatic Update of Currency Rates
As part of Business process automation, IFS Cloud supports automatic update of currency rates. Using this functionality users can update currency rates of a company or multiple companies. IFS workflow solution is used in the functionality to facilitate the automatic fetching of currency rates from a given external service provider. Further, the solution supports centralized management of currency rates in a group company scenario.

Basic Data Setup
Before using the functionality, it is required to set up the IFS workflow solution.

This needs to be done in the Solution Manager/Workflow Manager/ Workflow.

A reporting period definition should be entered.
Note: For testing purposes, we have used https://currencyapi.com. However, based on the customer requirements and service agreements, it is recommended to select a suitable service provider.

Set up the API Key.
You need to clone the latest version of the existing workflow diagram to perform the above changes.
Save and deploy the modified version of workflow diagram.
Set the "Action Enabled" in the "Projection Action Information" for below workflows.
finCurrencyTypeUpdate
finUpdateCurrencyRatesForCurrencyTask
finCentralCurrencyHandling
More supporting documents related to IFS workflow configuration is available on, Technical Documentation for Workflows.

How to Update Single Currency Rate Type
This functionality supports updating the currency rates defined in a particular currency rate type automatically using an external service provider. Users can use the command Update Currency Rates in Currency Rate Types or Currency Rates pages. When the rates are updated, it will be notified to the user with the updated time stamp. The below flow diagram demonstrates the basic interactions in the process.

Update Multi Company Currency Rate Types using Task for Currency Updates
It is possible to update the multiple currency rate types using a single action. To facilitate that we are using the Task for Currency Update page to set up the currency rate types. To differentiate the set-up from existing external file handling functionality it is required to enable the option Task for Workflow in Task for Currency Update page during the definition. Use the command Update Currency Rates to execute the automatic update of currency rates.

Centralized Currency Rate Handling
This is to support centralized currency management function within a group company scenario. Users can define the source -target company relationship in the Centralized Currency Rate Handling page. The source company rates are updated using IFS workflow, and the currency rates of the target companies are updated using triangulation - based on the updated currency rates of the source company. Use the command Update Currency Rates to execute the automatic update of currency rates.

During the triangulation process below factors are considered.

Inverted Quotation set up for the currency code in source and target companies.
Conversion factor of the currency codes used in the triangulation.
Decimals places defined per each currency code in relevant companies.
Date of Update (only new lines will be added for target company currency rates and no changes will be made if there is an existing rate for the given date).

Manual Update of Source Company Currency Rates
If source company currency rates are manually updated, we have facilitated a process to sync the change to target companies. To support this, a new dialog Update Target Company Currency Rates is triggered when a currency rate is adjusted or added in the Currency Rates page in the source company.

To initiate the process below criteria should be met,

Change/modification should be done in the source company.
An active definition should be in place under the Centralized Currency Rate Handling page.
Execution Options
The update currency rate function using IFS workflow can be performed as an online job or can be scheduled as a background job.

Description of Set Up Basic Data Accounts Receivable
Description of process
The Description of Set Up Basic Data Accounts Receivable process describes BDR (Basic Data Required) for running the main processes Invoicing and Customer Payments. Check or/and add information according to the activities in the set up process before you start to work with the IFS Cloud. To be able to run all sub processes in Invoicing and Customer Payments, IFS/Invoice, IFS/Payment, IFS/Project, Reporting and IFS/Customer Order must be installed. The following set up information contain basic data required for running the processes linked to IFS/Invoice and IFS/Payment.

Click the action symbols in the set up process to view detailed description on each activity.

Check and add information as described below:

Check that the company you want to work with is entered as per the instructions in Define System Basics.

Check the Set up Basic Data Accounts Receivable process. The system creates default data values for a lot of functions when a company is created. These can be left as is or changed manually as required. Check and/or add General Customer Invoice Information. Check and/or add General Customer Payment Information.

Information concerning the sub processes included in the Invoicing and Customer Payments  processes are found in each sub process. Click the notes symbol that appear in each sub process to view the text. The BDR (Basic Data Required) is also stated as a reminder when you click the requirement symbol.
 
About Discovery Manager
The Discovery Manager is where the user can see how the Azure components are configured in order to pass data through the IoT Gateway and being transferred to IFS back-end systems. It is what happens before the business optimization and itâ€™s a step after the devices and communications are connected with for example sensors. As seen in the picture below the customers also can add PowerBI, Azure Machine Learning and Azure Notification Hub to the Discovery environment. The data generated by devices/assets should be gathered and processed somewhere using suitable techniques. The best place for this purpose is the cloud. Given that we choose a global cloud provider (Microsoft Azure), the storage and processing medium will be easily scalable and globally available around the clock. All of the processing in Azure is done within a private Azure subscription. This means that access to and management of these services is shielded. The only end-points open for inbound access from the Internet are the ports needed for IoT Hub. These services expose a REST API which in turn is protected by a shared key, which is held inside the private Azure subscription. Access to the Azure REST API is protected by use of Https and by use of this shared key. No openings are required at the other end of the architecture inside on premise network zone. The IoT Gateway communicates outbound to the Service Bus Queue, located inside the same private Azure subscription, on ports 9350-9353. If those are blocked it will retry on port 443 or 80. You can preset these parameters in the configuration file. During installation of IFS IoT Controller a dedicated user, â€œIFS_IOT_GATEWAYâ€ is created for the purpose of sending data from IoT Gateway to IFS Cloud, and given only those permissions that are needed. The credentials for this user are stored on the same server as the IoT Gateway.

Business Opportunity
General Information

The business opportunity is a pre-step to quotations and orders. At this stage you only know that you have the opportunity to sell something to a specific customer or prospect but it is not mandatory to specify exactly which parts it concerns or from where it should be delivered.

The first step in a new entry is to enter general information about the opportunity. When the opportunity has been saved, it receives the Unconfirmed status. The status can then manually be updated to Confirmed once you get a confirmation from the account. The next step in a new entry is to specify representatives, contacts, part lines, competitors etc.

On the opportunity lines, you specify the parts and quantities that the account might want to order. If the part is not registered as a sales part, it is possible to enter only the description, the quantity and an estimated price and cost. The part must later be entered as a sales part if an order is going to be created from the opportunity.

The status can manually be changed to Canceled, Closed or On Hold. When the status is changed to Closed the closed status will be lost or won. If the opportunity is lost, you can specify which competitor that won the business and the reason for the loss. When an order is created, you can enter the reason why it was won.

The status set for a business opportunity in IFS Cloud is: Confirmed, unconfirmed, cancelled, closed, on hold.


Create Supply Request for Purchase Order Plan


Explanation

	

Use this activity to create supply request for purchase order plans. A recommendation 	is to review material plan warnings before creating the supply request.

	

Prerequisites

	

A purchase order plan should exist. A purchase order plan is created 		during the creation of material plans.
Previously created supply requests should not exist.
Deliverable items must be approved.
Project activity must be released.

Clock IN with Normal Time
Explanation
This activity is used to clock IN normal using the Time Clock terminal. When the IN clocking is created, the employee's identification can either be entered manually or by using a swipe card depending on the setup defined for the button.

Note: If the Time Clock is operating in Offline mode the clocking records you create using the Time Clock will not be transferred to IFS/Time and Attendance immediately. Instead the information you enter will be buffered and when the Time Clock reverts back online it transfers the information to the Time and Attendance.

Depending on the Time Clock configuration, some of these fields may be automatically filled with default data for your convenience and thereby the fields may be disabled or unavailable for editing. When these values are entered, you can click OK on the dialog box to create the clocking.

If the relevant button is set to card driven in the Time Clock configuration, you are only required to click the button and swipe your card. Your employee ID and company ID will immediately display in the text panel on the Time Clock.  Therefore, if the card driven setting applies to the button, you will not have to use the dialog box for clocking IN.

Also note that some parameters connected to the employee's work hour rules may block the employee from clocking In attendance or may force the employee to register alternative clocking records. The Disallow Early Clocking parameter will determine how early (compared to the schedules start time) an employee is allowed to clock In attendance. The Limit for Clocking without Absence parameter will determine how late an employee is allowed to clock In attendance. If this maximum allowed time is passed, the employee will be forced to register absence.

If IFS/Manufacturing is installed in the system;

When the resume option specified for the employee in the Shop Floor Employee page is set to Ask for Resume, a question message will be prompted when employee creates the IN clocking. This will give employee the option of resuming the shop order operations or indirect jobs which were auto stopped on the previous day.

However, if the employee's last auto stop clocking was a team clocking, the Join Team dialog box will open instead of the warning message enabling the employee to join a labor team at the time of the IN clocking. The team from which the employee last clocked out will be selected to the Team field by default. If required you can change this value. Click OK to save the information.

Prerequisites
In order to perform this activity;

The relevant Time Clock buttons should be configured in the Time Clock Type Details and Time Clock Type Detail Items pages.
Employee is required to have a day type dependent schedule assigned.
System Effects
As a result of this activity;

The Time Card and Employee Clockings pages will be updated with an IN clocking of type Normal.
An open interval will be generated in the Intervals area of the Time Card page  and the Employee Intervals page
The Day Info column of the respective day on the Time Card  page will be set to Open.

If IFS/Manufacturing is installed, the following will also be effective;
 
When an IN clocking record is created, any operations or indirect jobs from which the employee last clocked out may be automatically started for the employee. The automatic start will work only if the resume option specified for employee in the Shop Floor Employees page is Automatic Resume.


	

System Effects

	

A purchase requisition is created.

	

Pages

Project Deliverables Materials and Services