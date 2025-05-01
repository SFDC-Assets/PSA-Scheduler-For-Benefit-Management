![Public Sector Accelerators logo](/docs/Logo_GPSAccelerators_v01.png)

# Scheduler for Benefit Management

**Connect Benefit Management with Scheduler to schedule clients and track benefit disbursements.**

[Accelerator Listing](https://gpsaccelerators.developer.salesforce.com/accelerator/a0wDo000000BBEeIAO/scheduler-for-benefit-management)


## Description

The Benefit Scheduler Accelerator is to connect Benefit Management with Lightning Scheduler. Many times customers need to track the benefits that are delivered to a client, but need the ease of an efficient scheduling tool. This accelerator connects the process of creating a Benefit Schedules and turns that into a Shift for Lightning Scheduler to use. Secondly, in order to determine what types of services a client is eligibile to schedule for, Lightning Scheduler will reference active Benefits Assigned to the client. Lastly, once a Service Appointment is scheduled, the Benefit Disbersement is logged for benefit management. 

<html style="overflow-y: hidden;">
</head>
<body style="height: auto; min-height: auto;">
<p><strong>Welcome to the Benefit Scheduler Quick Start</strong></p>

<p>This Accelerator was built to help jumpstart your environment to support Lightning Scheduler and then connect that the Benefit Management.</p>

<p><strong>Benefit Management</strong>:</p>

<ul>
	<li><strong>Benefit</strong>: Identifies the types of services you may offer. This could be sessions or even goods and services.</li>
	<li><strong>Schedules</strong>: Helps to set the frequency and cadence for the benefit to be offered. Example: Intakes can occur Mon - Fri from 8 to 5. Cooking classes will be every other Tuesday from 5-6pm)</li>
	<li><strong>Benefit Session</strong>: This record represents each session within the Schedule and the participants for future attendance tracking.</li>
	<li><strong>Benefit Assignment:</strong> These records help to confirm specific benefits each client or participant is eligible for.</li>
	<li><strong>Benefit Disbursements</strong>: This record represents individuals who are signed up for a Session or who have received goods.</li>
</ul>

<p><strong>Lightning Scheduler</strong>:</p>

<ul>
	<li><strong>Work Type and Work Type Groups</strong>: Is designed to help map specific Work Types and Work Type Groups to jobs or types of appointments you may offer. Example Intake Appointments vs Home Visits</li>
	<li><strong>Skills</strong>: From there, Scheduler will allow you to set Skills that control what Resources are eligible to provide the service.</li>
	<li><strong>Service Territories</strong>: Create Service Territory (or location) that offers these services. Example: The San Fransisco Office vs the Oakland Office.</li>
	<li><strong>Max Participation</strong>: Scheduler allows you to set rules in place to control the maximum attendees per Service Appointment (Attendees per Service Appointment, meaning maybe only 4 per family can attend) and/or total Service Appointments per Shift (meaning you can have a max of 5 Service Appointments set for each Shift).</li>
	<li><strong>Shift: </strong>Shifts assigned to the Session also tells you which resource will be running each session/shift.</li>
</ul>

<p><strong>The Accelerator - How it Works?</strong></p>

<ul>
	<li><strong>Setup New Benefit</strong>: From the Program record, select the &quot;New Benefit &amp; Work Type&quot; button, which launches the Flow &quot;Accelerator: Benefit Scheduler - New Benefit and Work Type/Groups&quot;. This Flow allows you to set all the major required fields to setup a Benefit, Work Type/Group, Service Territory, and Resource who will own the upcoming sessions (required for Lightning Scheduler to run).</li>
	<li><strong>Create a Shift from Sessions with Work Types</strong>: This takes the values on the Sessions Benefit record and adds them to the Shift (Resources, Territory, Appointment Category, etc so that each Session is connected to a Shift. Shifts are the primary record used for scheduling on Lightning Scheduler.</li>
	<li><strong>Schedule Client</strong>: From the Account Page, the &quot;Benefit Scheduling&quot; button with launch the &quot;Accelerator: Benefit Scheduler - Outbound New Appointment Using Shifts&quot;. This takes the native Outbound New Appointment Flow, but includes Benefit Assignment requirements in consideration. This means if the client has not been assigned a Benefit, they will not be offered as an option. Only Assigned Benefits will be provided. From there, once a Service Appointment is created, a Benefit Disbursement will also be created for future attendance from the Benefit Session record.</li>
</ul>

<p><strong>The Goal</strong>: Seamlessly connect the Benefit Assignments/Eligibility, to the Lightning Scheduler matching engine to help streamline appointment and scheduling.</p>

<p>Important Note: If a new Benefit/Work Type is created and the desired Resource is not already assigned to the desired Territory, the Flow will automatically assign that Territory to the Resource as a secondary territory. If this is not the desired workflow, please update the &quot;Accelerator: Benefit Scheduler - New Benefit and Work Type/Groups&quot; Flow.</p>
</body>
</html>



## Included Assets

<html style="overflow-y: hidden;">

</head>
<body style="height: auto; min-height: auto;">This Accelerator includes the following assets:
<ol>
	<li>An <strong>unmanaged package</strong> (link below; metadata is also found in the /force-app/main/default/ folder) that includes:
	<ul>
		<li>Lightning App: Benefit Scheduler Admin</li>
		<li>Flows: (x3):
		<ul>
			<li>From the Program record, select the &quot;New Benefit &amp; Work Type&quot; button, which launches the Flow &quot;New Benefit and Work Type/Groups&quot; flow. This Flow will create the Benefit and Work Type. The details on the Benefit will be pulled every time a Session is created and marry them to a Shift record for future scheduling.</li>
			<li>Auto Launch Flow: &quot;Create a Shift from Sessions with Work Types&quot;Benefit Scheduler - Create Shifts from Session Creation&quot;</li>
			<li>From the Account Page, the &quot;Benefit Scheduling&quot; button with launch the &quot;Accelerator: Benefit Scheduler - Outbound New Appointment Using Shifts&quot;. This flow will only allow clients to be scheduled to Benefits they are assigned to and have Shifts available in the preferred Territory.</li>
		</ul>
		</li>
		<li>Page Layouts
		<ul>
			<li>Benefit: Lightning Page &quot;Accelerator: Benefit&quot; includes fields for Scheduler and related records such as Shifts</li>
			<li>Program: Lightning Page &quot;Accelerator Program Record&quot; includes a new button (New Benefit &amp; Work Type) to create a Benefit and Work Type in the same flow.&nbsp;</li>
			<li>Session: Lightning Page &quot;Accelerator Benefit Session&quot; which has a Related Record to show associated Shift</li>
			<li>Account: Lightning Page &quot;Client Lightning Page&quot; which add the related Service Appointment and Disbursements to their page layout</li>
		</ul>
		</li>
	</ul>
	</li>
</ol>
</body>
</html>


## Before You Install

**License Requirements**

Salesforce Scheduler, plus Nonprofit Cloud, Public Sector Solutions, or any other Salesforce industry cloud with access to Program and Benefits Management (internal users); or Nonprofit Cloud Plus edition (which natively includes Scheduler).

**General Assumptions**

It is recommended that you deploy this Accelerator in a sandbox or test environment. It is recommended that you not install any Accelerator directly into production environments.

**Pre-Install Instructions**

- Org Activations
	- Enable Person Accounts: Setup > Person Accounts and walk through the checklist (create a general Account Record type and confirm implications of setting up person accounts). Person Accounts are use for Clients in Nonprofit Cloud.
 	- Enable Program and Benefit Management: Setup, search for "Program and Benefit Management Settings" and enable.
  	- Setup > search for Scheduling Policy > edit the Default Scheduling Policy (or create a new one for Shift Scheduling). Select "Use service territory member’s shift" and "Use service territory’s operating hours with shifts"
- User Permissions
	- Assign the following permission sets to users:
		- Advanced Program Management
 		- Program and Benefit Management Access
  	- Assign the Permission Set License "Salesforce Scheduler" to your Resources
  	- Create a new Permission Set (Setup > Permission Set > New). On the Permission Sets overview page, under System section, click System Permissions (bottom of page). Click Edit. Select "Let a user be included in appointments in Salesforce Scheduler". Click Save.
  	- Assign users the "Industries Assessment" permission set license.


## Installation

* Install the unmanged package: https://test.salesforce.com/packaging/installPackage.apexp?p0=04tam0000010NQf


## Post-Install Setup & Configuration

This Accelerator is used to connect Nonprofit Cloud Program Management and Lightning Scheduler. This means that in order to proceed you will need to make sure you have the following records created. Keep in mind, your environment may already have some of these setup, but if not, you will need the following items in order to use this Accelerator.

Lighting Scheduler

   <li>Create Default Work Type: Setup > This Object Manager > Work Type > Fields and Relationships > Default Appointment Type: Example = “Main Office”
<li>Appointment Categories (record) 
    <li>Service Territory (record). Example: San Fransisco, Oakland, etc. 
        Pro Tip: If you only have one area that resources would go to you could update this as a default in Appointment Scheduling Flows.
<li>Within your Service Territories, you will also need Business Hours field completed, to indicate when this Territory is available for business. Example: “Monday - Friday: 8am to 5pm”
            <b>>* When you create a new Business Hours record you will need to also add time slots to represent hours of business. If you use the example, “Monday - Friday: 8am to 5pm”, you will need to add a Time Slot for Monday 8-5, Tuesday 8-5, etc. </b
   <li>Validate that you have at least one Appointment Types. Go to Setup > Objects tab > under Quick Find search for Work Type > under Fields look for Default Appointment Types > edit and add at least one type. Examples: "Office" or "Remote"
   <li>Service Resources (record): Validate that your staff who you will be scheduling for, have Service Resource records created.

<html style="overflow-y: hidden;">
<head>
	<title></title>
</head>
<body style="height: auto; min-height: auto;">
<h3>How to use the Accelerator to connect Benefit Management with Lightning Scheduler:<br />
<br />
Step 1 - Setup the Benefit</h3>

<ul>
	<li>First, create the Program that offers these Benefits you want to schedule for</li>
	<li>Create a Benefit - From the Program record, use the<b> &ldquo;New Benefit and Work Type&rdquo; Button</b>
	<ul>
		<li>This will help set the Benefit record with details it needs to run Benefit Management and it will create the Work Types and Groups for Lightning Scheduler. Out of the box we assign one Service Resource and Service Territory that will own this Benefit. Example: Group Therapy with Chrissy Thompson at the Main Office.<br />
		<br />
		Example:
		<ul>
			<li>Group Therapy</li>
			<li>Benefit Type = Group</li>
			<li>Active = True</li>
			<li>Status = Active</li>
			<li>Attendee Limit = 5 (assuming only 5 people are allowed due to space or other restrictions)</li>
			<li>Duration Type = Minutes</li>
			<li>Duration of Appointment = 30</li>
			<li>Appointment Category = Office (If blank, Setup &gt; Object Manager &gt; Work Type &gt; Fields &gt; Default Appointment Type &gt; and create your own)</li>
			<li>Operating Hours = Select the one you setup (Example = Monday - Friday 9am to 5pm)</li>
			<li>Next Screen - Select the Service Resource (staff member) and the Service Territory you setup above<br />
			*THIS PROCESS WILL CREATE A BENEFIT AND A WORK TYPE AND CONNECT THEM</li>
		</ul>
		</li>
	</ul>
	</li>
	<li>Create a Benefit Schedule - From the Benefit you just created, create a Schedule using the <b>&ldquo;New Benefit Schedule&rdquo; Button.</b></li>
</ul>
Example

<ul>
	<li>
	<ul>
		<li>Name - Group Therapy - Monday Morning Sessions</li>
		<li>Benefit Qty - 30</li>
		<li>Max Part Count = 1</li>
		<li>First Session Date = future</li>
		<li>Start Time - 10am (Make sure the appointment is within your Operating Hours)</li>
		<li>End Time - 10:30am</li>
		<li>Recurrence Frequency - Weekly on Monday<br />
		*THIS PROCESS CREATES SHIFTS FOR EACH SESSION</li>
	</ul>
	</li>
</ul>

<h3>Step 2 - Schedule the Client</h3>

<ul>
	<li>Create the Client record using the Client Record Type</li>
	<li>Enroll the client in the program you setup from the step above</li>
	<li>From the client&rsquo;s record, create a new Benefit Assignment - this controls what staff can and cannot schedule clients for based on eligibility (Benefit Assignment)</li>
	<li>From the client&rsquo;s record, select the &ldquo;Benefit Scheduling&rdquo; button. This launches a modified Appointment Scheduling Flow that filters only benefits the client is eligible for. Once scheduled, the Flow will also create the standard Service Appointment for Lightning Scheduler, and the Benefit Disbursement for future attendance and benefit delivery tracking.</li>
</ul>
<br />
That&rsquo;s it! Most the setup is making sure you have your basic records for Lightning Scheduler such as, Operating Hours and Territory. From there as you need new Benefits or Sessions, you simply use the easy buttons to create more. Staff can easily schedule a client based on the matching criteria and availability set by the sessions.<br />
&nbsp;</body>
</html>


## FAQs

**_Q: Do I need to use Shifts for this Accelerator?_**

A: Yes, this Accelerator leverages creating Benefit Sessions to determine when staff are eligible for a given benefit/work type. If you would like to leverage Operating Hours, you can create a seperate Scheduling Poilcy that does not leverage Shifts. 

**_Q: Can I modify the Benefit Session Creation process?_**

A: Yes, you are able to clone and then modify the original OmniScript process to meet your needs: Benefit/LightningSchedulerAccelerator. 

**_Q: How do I change the filtering process?_**

A: Yes, you are able to revise the scheduling process and revise the Work Type filter criteria. Please modify Flow: "Accelerator: Benefit Scheduler - Outbound New Appointment Using Shifts". 

## Additional Resources

More information on Scheduler: https://help.salesforce.com/s/articleView?id=platform.ls_overview.htm&type=5
More information on Benefit Management: https://help.salesforce.com/s/articleView?id=sfdo.rn_npc_program_management_release_notes_246.htm&type=5


## Revision History

<strong>1.0 Initial release (January 2025)</strong> - Initial release includes the process for creating a new Benefit Schedule and connecting that to a Shift. When you are ready to schedule a client, the process will account for Benefits that are assigned to to the client, determining scheduling eligibility. Once a Service Appointment is made, the Benefit Disbersement will also be created.


## Acknowledgements

<body style="height: auto; min-height: auto;"><strong>Chrissy Thompson</strong>, Lead Strategic Solution Engineer: https://www.linkedin.com/in/thompsonchrissy/<br />
<strong>Dan Tajbl</strong>, Lead Strategic Solution Engineer: https://www.linkedin.com/in/dantajbl/&nbsp;&nbsp;<br />
<strong>Cassie Bartelme</strong>, Senior Solution Engineer: https://www.linkedin.com/in/cassiebartelme/&nbsp;<br />
<strong>Lauren McGuire</strong>, Solution Engineer: https://www.linkedin.com/in/lauren-mcguire-m-s-ed-6ab4861b8/</body>


## Terms of Use

This Accelerator is to be used to create Shifts based on a Benefit's Schedule, filter clients Benefit Assignment, and then create Benefit Disbersements, leveraging a Service Appointment scheduled through Lightning Scheduler.

Thank you for using Global Public Sector (GPS) Accelerators.  Accelerators are provided by Salesforce.com, Inc., located at 1 Market Street, San Francisco, CA 94105, United States.

By using this site and these accelerators, you are agreeing to these terms. Please read them carefully.

Accelerators are not supported by Salesforce, they are supplied as-is, and are meant to be a starting point for your organization. Salesforce is not liable for the use of accelerators.

For more about the Accelerator program, visit: [https://gpsaccelerators.developer.salesforce.com/](https://gpsaccelerators.developer.salesforce.com/)
