---
title: "[]{#_18wkn9e6tvwx .anchor}Table of Contents "
---

[INTRODUCTION 3](#introduction)

[XM Cyber Features 3](#xm-cyber-features)

[Benefits from XM Cyber Deployment
3](#benefits-from-xm-cyber-deployment)

[How to Use this Manual 3](#how-to-use-this-manual)

[OVERVIEW 4](#overview)

[XM Cyber Architecture 4](#xm-cyber-architecture)

[XM Cyber Workflow 6](#xm-cyber-workflow)

[GETTING STARTED 7](#getting-started)

[XM Cyber Deployment 7](#xm-cyber-deployment)

[Starting the XM Cyber Application 8](#_Toc41055378)

[THE DASHBOARD 10](#the-dashboard)

[Dashboard Display 10](#dashboard-display)

[THE SCENARIO HUB 13](#the-scenario-hub)

[Scenario Display 14](#scenario-display)

[Viewing Campaigns 15](#viewing-campaigns)

[CREATING AND MODIFYING SCENARIOS 20](#creating-and-modifying-scenarios)

[Creating a New Scenario 20](#_Toc41055385)

[Manually Generating a Campaign from a Scenario
29](#manually-generating-a-campaign-from-a-scenario)

[THE BATTLEGROUND 30](#vulnerability-management)

[Navigating to the Battleground 30](#navigating-to-the-battleground)

[Understanding the Battleground Screen
31](#understanding-the-battleground-screen)

[Campaign Visualization 35](#campaign-visualization)

[REPORTS 45](#vulnerability-management-1)

[How to Access Reports 45](#how-to-access-reports)

[Report Navigation 46](#_Toc41055393)

[Understanding Reports 47](#understanding-reports)

[Other Reporting Capabilities 54](#other-reporting-capabilities)

[SYSTEM CONFIG 55](#system-config)

[System Config Tabs and Links 55](#system-config-tabs-and-links)

[XM Cyber Terminology -- Glossary 73](#xm-cyber-terminology-glossary)

[User Manual and UI Conventions 76](#user-manual-and-ui-conventions)

INTRODUCTION
============

XM^®^ Cyber provides the first fully automated APT (Advanced Persistent
Threat) Simulation Platform to continuously expose all attack vectors,
above and below the surface, from breach point to any critical
organizational asset. This continuous loop of automated red teaming is
completed by ongoing and prioritized actionable remediation of security
gaps. XM Cyber operates as an automated purple team that fluidly
combines red team and blue team processes to ensure that organizations
are always one step ahead of hackers.

XM Cyber provides organizations with a clear, up-to-date understanding
of where and how hackers can (and will) infiltrate their network and
compromise critical assets. The platform is meticulously designed to
work safely in an organizational network, simulating malicious methods
without disrupting network availability or causing harm to critical
assets.

XM Cyber Features 
-----------------

-   Automated generation of actionable and prioritized remediation
    reports

-   Customized attack scenarios from any starting point to any target
    asset

-   Comprehensive and up-to-date attack methods

-   Fully secure simulation based on real user actions implemented in
    real-time

-   Detailed visual display of the attacker path(s) to critical assets

-   Comprehensive reports on organization cybersecurity status and
    posture

Benefits from XM Cyber Deployment
---------------------------------

-   Easy deployment and rapid returns on security investment

-   Accompanies changes to networks and asset distribution

-   Scalable Architecture

-   Reduces risk from non-optimal security hygiene

-   Optimizes use of cyber resources, digital and human

How to Use this Manual
----------------------

This manual is intended for security practitioners and analysts, and IT
personnel. It explains how to use XM Cyber to run virtual APT (Advanced
Persistent Threat) campaigns to test the viability of your company's
cybersecurity and uncover exploitable vulnerabilities.

The document assumes that XM Cyber has already been installed on Windows
and Linux servers as explained in the *XM Cyber Installation Manual*.

OVERVIEW
========

This section provides an overview of XM Cyber functioning, details on
system components, and an outline of how to work with XM Cyber. A short
glossary at the end of this guide assists in understanding key concepts
and terminology. Instructions and requirements for installing the
components of the XM Cyber virtual APT system are found in the *XM Cyber
Installation Manual*.

### Safe and Continuous Operation

XM Cyber simulates, assesses, and validates cyber-attacks using
knowledge of APT techniques catalogued by XM Cyber. XM Cyber addresses
real user behavior and actual exploits across a wide spectrum of attack
scenarios to expose blind spots -- bad configurations, latent
vulnerabilities and other weak points. The attacks use real-world
techniques but XM Cyber simulations are run safely without affecting
network availability or user experience.

### Comprehensive Approach

XM Cyber provides visibility along an entire attack path, from breach
points to critical assets, followed by prioritized and actionable
remediation guidance. XM Cyber operates as an automated purple team,
continuously combining red team (attack) and blue team (defense)
techniques to help you optimize allocation of resources and deliver
measurable return on security investments.

XM Cyber Architecture
---------------------

To perform attack simulations, XM Cyber deploys software across the
organization to manage, monitor and analyze simulated attacks using the
following components:

### Sensors

Sensors are lightweight passive software agents deployed on user
computers and servers across the organization that monitor and report on
the state of network nodes and sub-nets in support of APT simulations
(campaigns). XM Cyber sensors communicate with the South server over a
secure SSL/TLS channel. Sensors contain host self-defense to protect
themselves from attack, via signature validation of executed code, and
resource monitoring.

Sensors can be installed on computers running Windows, Linux and MacOS.
They can run on physical or virtual devices with the supporting
operating systems. The sensors continuously capture information from
systems and can identify changes in the network and devices that effect
the risk of assets. For an accurate security assessment, organizations
must deploy sensors on at least 10% of network nodes distributed across
different network segments, departments and device types.

### North Server

The North Server hosts the main XM Cyber software components under Linux
(CentOS/RHEL 6/7). The North Server is responsible for running campaigns
that simulate attacks, including discovering weaknesses and exploiting
them. The North Server also analyzes data collected during campaigns and
generates reports that highlight vulnerabilities and offer remediation
plans postmortem. The server can reside either on premises or in the
cloud.

### Database Server

XM Cyber requires a NoSQL database (MongoDB) to store information
collected from the sensors deployed throughout the network, before,
during and after campaigns. The Database Server can be hosted on
premises or in the Cloud. For smaller organizations, the database can
reside on the Norther Server.

### South Server

![](media/image1.tiff){width="4.269444444444445in"
height="4.695590551181103in"}The South Server runs Windows Server
Edition and manages communication between the North Server and sensors
during campaigns. It also provisions sensor node with up-to-date
binaries to the sensors.

### XM Cyber Gateway (not pictured)

For air-gapped or otherwise isolated sub-networks, a computer may be
assigned to act as a gateway, relaying and regulating communication
between sensors in the segment and the South Server.

XM Cyber Workflow
-----------------

After XM Cyber is installed, XM Cyber can run APT simulations
(campaigns) in each Scenario. Scenarios are created by customers
depending on the business risk they want to assess. Within each
Scenario, campaigns are activated to begin at an endpoint in the
network, which is deemed vulnerable. Defining scenarios is explained in
[Creating and Modifying Scenarios](#creating-and-modifying-scenarios).

Once a scenario has been created in XM Cyber, the system can execute
campaigns either automatically or manually.

![](media/image2.tiff){width="3.5590277777777777in"
height="3.313254593175853in"}A typical workflow is as follows:

1.  Create a Scenario around a particular risk, e.g., starting from a
    > remote office, is an organization's PCI network accessible?

2.  Once the scenario is configured with one or more breach points,
    > assets and a schedule, the campaign will run. Users can view a
    > graphic simulation of the APT in real time (*battleground*) and
    > observe endpoints that are discovered to be compromised or
    > vulnerable. Campaigns can be set to run automatically at specified
    > times or can be activated manually whenever desired.

3.  Generate reports that identify security problems and provide
    > remediation guidance for overcoming them.

GETTING STARTED 
===============

This chapter explains how to begin running campaigns with XM Cyber. It
also introduces the XM Cyber user interface and explains the information
it displays.

XM Cyber Deployment 
-------------------

Getting Started with XM Cyber involves the following steps:

1.  On-premises - Install XM Cyber on the North, South and Database
    > servers as explained in the *Installation Manual*. The XM Cyber
    > team can provide assistance with this step.

2.  Cloud-hosted -- for cloud-based configurations, no server
    > installation is required.

3.  Deploy XM Cyber sensors on servers and workstations across an
    > on-premise and/or cloud environment, whose security is being
    > checked. Administrators can deploy sensors across their
    > environments and include those sensors as part of their base
    > images.

> **Optional** -- XM Cyber can provide guidance on sensor deployment
> based upon analysis of your network topology and security measures in
> place. To support this analysis, XM Cyber asks that users fill out a
> questionnaire that describing their system security.

4.  Start the XM Cyber application and specify parameters for a scenario
    > from the **Scenarios** screen (see [*SCENARIO
    > HUB*](#the-scenario-hub) below). The scenario specifies which
    > computers will be breach points for the start of the campaign, as
    > well as other parameters such as the timing and duration of the
    > campaign.

5.  Start and run the campaign from the XM Cyber application.

![](media/image3.png){width="2.6319444444444446in" height="2.738888888888889in"}Starting the XM Cyber Application
-----------------------------------------------------------------------------------------------------------------

Launch XM Cyber by doing the following:

1.  From an Internet browser[^1], enter the IP address of the North
    > Server or the URL of a cloud instance provided by XM Cyber and
    > press\
    > Enter to reach the XM Cyber login screen.

2.  Log in with your username and password; the XM Cyber dashboard
    > appears if you forgot your password, click Forgot Password on the
    > login screen to initiate a password reset sequence via your
    > registered email address.

> **Note -- XM Cyber supports SSO with OpenID Connect and OAuth2.**

![](media/image5.png){width="6.2362204724409445in"
height="2.9173228346456694in"}

*The XM Cyber Opening Screen*

At the left side of the screen is the *XM Cyber Sidebar* that enables
navigation around XM Cyber.

+----------------------------------+----------------------------------+
| ![](media/image7.p               | **XM Cyber Sidebar Icons and     |
| ng){width="0.6150820209973753in" | Functions**                      |
| height="3.486956474190726in"}    |                                  |
|                                  | **DASHBOARD:** Provides an       |
|                                  | overview of your organization\'s |
|                                  | security posture, including      |
|                                  | security ratings over time, and  |
|                                  | measurements of factors          |
|                                  | affecting it. The dashboard also |
|                                  | displays information on          |
|                                  | currently running campaigns, the |
|                                  | number of active sensors, as     |
|                                  | well as an attack summary.       |
+----------------------------------+----------------------------------+
|                                  | **SCENARIO HUB:** Displays       |
|                                  | information on campaigns and     |
|                                  | campaign scenarios. This screen  |
|                                  | also enables you to create and   |
|                                  | modify scenarios that specify    |
|                                  | the parameters of campaigns. See |
|                                  | [*SCENARIO                       |
|                                  | HUB*](#the-scenario-hub) for     |
|                                  | details.                         |
+----------------------------------+----------------------------------+
|                                  | **BATTLEGROUND:** Displays a     |
|                                  | graphic representation of a      |
|                                  | scenario and campaign.           |
|                                  | Information on the origin,       |
|                                  | target, and method of each       |
|                                  | attack is displayed at varying   |
|                                  | levels of granularity. Complete  |
|                                  | campaigns can also be viewed and |
|                                  | replayed. See *[THE              |
|                                  | BATTLEGRO                        |
|                                  | UND](#vulnerability-management)* |
|                                  | for details.                     |
+----------------------------------+----------------------------------+
|                                  | **SYSTEM CONFIG:** Contains tabs |
|                                  | displaying the health of the     |
|                                  | system, information on the       |
|                                  | sensors deployed across the      |
|                                  | system, and administration       |
|                                  | details. See                     |
|                                  | *[SYSTEM](#system-config)        |
|                                  | [CONFIG]{.ul}* for details.      |
+----------------------------------+----------------------------------+

THE DASHBOARD
=============

The **Dashboard** provides information to help assess your
organization's security posture, as well as displaying essential
information on XM Cyber operation, including the number of campaigns
currently running, the number of connected sensors, a summary of attacks
that occurred in the course of campaigns, and the overall health of the
XM Cyber system.

Dashboard Display
-----------------

### Security Rating

At the top of the dashboard is a graph that displays security ratings
over time:

![A picture containing monitor, front, large, television Description
automatically generated](media/image8.tiff){width="6.268055555555556in"
height="1.1868055555555554in"}

*Security Rating Graph*

The **Security Rating** is derived from scenario attributes --
number/type of assets, paths to assets, complexity, likelihood of
compromise, etc. Applying remediation (e.g., to reduce or eliminate
attack paths) will increase the security rating, indicating better IT
hygiene.

The **Security Rating** graph displays a time span with security ratings
ranging from 1 -- 5, in increments of .1. You can scale timespan to
cover days, weeks, months, or a year by clicking the buttons at the top
right of the graph. These buttons indicate the last 24 hours (day), the
previous seven days (week), the prior 30 days (month), or a full 365
days (year). The percentages for security factors such as configuration
management, network segmentation, etc. change to indicate the
measurement for the time span selected.

Placing the cursor on the graph displays a purple marker that you can
drag to a point on the graph showing the security rating for a specific
date and time.

### Utilization Statistics pane

Just below the Security Rating pane is the Utilization Statistics area.
It shows statistics for Configuration Management, Network Segmentation,
User Access Management and Vulnerability Management. You can find
additional information on these metrics in *Findings Reports* in the
[Reports](#vulnerability-management-1) section of this document.

![A picture containing drawing, clock Description automatically
generated](media/image9.tiff){width="6.268055555555556in"
height="0.5701388888888889in"}

*Utilization Statistics pane*

### Running Campaigns pane

This graph enables you to display the number of running campaigns for a
specific time. The time span of the graph changes according to the time
span button (day, week, month or year) selected at the top right of the
dashboard. Placing the cursor on the graph displays a marker that you
can use to locate a specific time.

![A picture containing object, light, drawing Description automatically
generated](media/image10.tiff){width="6.268055555555556in"
height="0.925in"}

*Dashboard Running Campaigns pane*

### Connected Sensors pane

This graph indicates the number of connected sensors. Similar to the
other graphs, the time span changes according to the time span button
that you selected and placing your cursor on the graph enables you to
locate a specific time.

![A picture containing drawing Description automatically
generated](media/image11.tiff){width="6.268055555555556in"
height="0.925in"}

*Connected Sensors pane*

### Clusters

Clusters are groupings of computers or subnets, by type, that appear on
the Dashboard as hexagons in the **Attack Summary** pane described
below. You can select the type of clusters to be displayed -- Network
Subnet, Domain/Workgroup, Computer Organization Unit, or User
Organizational Unit.

### Attack Summary

An **Attack Summary** provides information on the first device in a
cluster compromised by an attack. The **Dashboard Attack Summary**
displays information on the attacking device and target, as well as the
method of attack. The **Dashboard Attack Summary** area enables you to
select from a list of scenarios, campaigns, and cluster types in which
an attack occurred.

![](media/image12.png){width="6.2362204724409445in"
height="1.7440944881889764in"}

*Attack Summary*

To change the displayed attack:

1.  At the right of the Attack Summary area, click the Edit button
    > ![](media/image13.png){width="0.15147528433945756in"
    > height="0.19881233595800524in"} to display a dropdown list of
    > icons ![](media/image14.png){width="0.15075240594925635in"
    > height="0.15075240594925635in"}.

2.  Click the first drop-down list button
    > ![](media/image14.png){width="0.15075240594925635in"
    > height="0.15075240594925635in"} at the left to display a list of
    > scenarios and select one.

3.  Click the next drop-down list button
    > ![](media/image14.png){width="0.15075240594925635in"
    > height="0.15075240594925635in"} to display a list of campaigns and
    > select one.

4.  Click the next drop-down list button
    > ![](media/image14.png){width="0.15075240594925635in"
    > height="0.15075240594925635in"} to select a cluster type.

5.  Click OK.

6.  The display changes to show the cluster from which the attack
    > originated and the cluster containing the device that was
    > compromised (see figure above).

7.  To view the attack on the Battleground, click the Battleground
    > button in the Sidebar. The Battleground Attack Summary provides
    > details about the specific devices involved in the attack and
    > provides information about the method of attack.

THE SCENARIO HUB
================

The **Scenario Hub** displays user-created XM Cyber scenarios laid out
in a grid. Each scenario represents a mission for the APT simulation
engine. A scenario in the grid may display currently running campaigns,
past campaigns, or scheduled campaigns not yet begun.

![](media/image15.png){width="6.254166666666666in"
height="2.6517213473315837in"}

*Scenario Hub*

At the top of the screen is a panel that shows the number of scenarios
displayed on the screen
![](media/image16.png){width="0.7725688976377952in"
height="0.1404669728783902in"}, a text entry / search box
![](media/image17.png){width="0.9333048993875765in"
height="0.1652723097112861in"} to filter the scenarios displayed,
buttons to display active or inactive scenarios
![](media/image18.png){width="0.7411745406824147in"
height="0.16153762029746283in"}, and a Sort pulldown menu
![](media/image19.png){width="1.1552373140857393in"
height="0.15532589676290465in"}to sort the displayed scenarios according
in ascending or descending order. You use the **Create New Scenario**
button ![](media/image20.png){width="0.6160301837270341in"
height="0.16550087489063867in"} to create and configure a new scenario
(see *[[CREATING AND MODIFYING
SCENARIOS](#creating-and-modifying-scenarios)]{.ul}* below.)

![](media/image21.png){width="6.427724190726159in"
height="2.1734601924759405in"}

![](media/image22.png){width="2.38in" height="6.26in"}At the right side
of the **Scenario Hub** is an information pane that displays the total
number of scenarios in the system, the total number of campaigns run by
the scenarios, the average percentage of the network compromised by the
total of all campaigns, and a list of the top methods that compromised
the network.

Scenario Display
----------------

Scenarios are displayed in a grid, with each square (scenario "card")
highlighting scenario name and creation date. For scenarios in completed
campaigns, the scenario display includes statistics on the percentage of
compromised network and assets, as well as data yield in gigabytes. The
bottom margin displays the number of hours and minutes until the next
campaign scheduled by the scenario will run.

![](media/image23.png){width="2.392361111111111in"
height="2.991304680664917in"}A typical scenario card is pictured in the
Example Scenario pictured to the right. Note the graph in the center
representing a timeline of campaigns that have completed for that
scenario. Placing the cursor on the graph displays a date and the name
of the campaign run by the scenario on that date. For example, in the
figure, on June 27 the scenario ran Campaign 000047. The graph also
depicts the percentage of assets compromised (red line), network
compromised (dashed purple line), and the data yield (blue line) for the
campaign. At the top left, above the scenario name, is a symbol that
indicates the current status of the scenario: Active
![](media/image25.png){width="0.16956692913385826in"
height="0.16956692913385826in"} or Inactive
![](media/image27.png){width="0.16666666666666666in"
height="0.16666666666666666in"}.

Clicking on the graph displays two buttons at the bottom enabling you to
**View Report** ![](media/image28.png){width="0.7929297900262468in"
height="0.16666666666666666in"} or **View the Battleground**
![](media/image29.png){width="0.9479166666666666in"
height="0.16666666666666666in"} for the selected campaign.

![](media/image30.png){width="2.1729166666666666in"
height="2.8520833333333333in"}At the top of each scenario card is a
**More** button ![](media/image31.png){width="0.17708333333333334in"
height="0.23958333333333334in"}. Clicking the button displays a list of
options enabling you to Generate a new campaign, as well as options to
Activate/De-activate the scenario, Duplicate to New, Pause all campaigns
run by the scenario, Complete all campaigns, or Delete the scenario:

Clicking a Scenario card selects it and displays the relevant details in
the Information pane at the right of the screen.

Viewing Campaigns
-----------------

### Viewing a Campaign from Scenarios

At the top of each scenario display, near the scenario name, is a button
showing the number of campaigns run by the scenario to date:
![](media/image33.png){width="0.4166666666666667in"
height="0.2604166666666667in"}. Clicking this button displays the
campaign on a screen as follows:

![](media/image34.png){width="6.2362204724409445in"
height="2.720472440944882in"}

*Scenario Details Screen*

The top of the screen displays the name of the campaign scenario and a
**More** button with the following options:

+----------------------------------+----------------------------------+
| -   Edit Scenario Configuration, | ![](media/image35.p              |
|                                  | ng){width="2.2093252405949255in" |
| -   View Report,                 | height="2.507211286089239in"}    |
|                                  |                                  |
| -   Generate New Campaign,       | *Campaign Scenario Options*      |
|                                  |                                  |
| -   De-activate Scenario,        |                                  |
|                                  |                                  |
| -   Duplicate to New,            |                                  |
|                                  |                                  |
| -   Pause All Campaigns,         |                                  |
|                                  |                                  |
| -   and Complete All Campaigns.  |                                  |
+----------------------------------+----------------------------------+

The remainder of the screen displays a list of campaigns already run or
are currently being run by the scenario. For each campaign, the
following information is displayed:

**Status**: Completed
![](media/image36.png){width="0.15844816272965878in"
height="0.17708661417322835in"}, Currently running
![](media/image25.png){width="0.15354330708661418in"
height="0.15354330708661418in"}, Paused
![](media/image37.png){width="0.15354330708661418in"
height="0.15354330708661418in"}, or Failed
![](media/image38.png){width="0.15354330708661418in"
height="0.15354330708661418in"}. A campaign can also be flagged
![](media/image39.png){width="0.17708333333333334in"
height="0.14583333333333334in"}for tracking, by clicking the Flag icon
to the left of the campaign.

**Campaign number**: a unique number assigned by XM Cyber that
identifies the campaign.

**Start Date**: the date on which the campaign started.

**Duration**: the number of hours and minutes the campaign has run.

**Network Compromised**: the percentage of the user network compromised.
The number in the center of the circle represents the actual percent. A
completed circle around the percent signifies 100 percent, while lower
percentages appear within incomplete circles. For currently running
campaigns, the circle and its percentages change in real time,
reflecting how much of the network has been compromised so far by the
campaign.

**Assets Compromised**: the percentage of assets that have been
compromised by the campaign. The percentage is displayed in the same way
as Network Compromised (see above).

**Date Yield**: The amount of data potentially exfiltrated by the
campaign in gigabytes.

Clicking a heading enables you to sort the list by that heading in
ascending/descending order. You can also filter the list of campaigns
using the buttons at the top of the campaign list (All, Running, Paused,
Failed, Completed, and Flagged).

For each campaign, placing the cursor at the far-right of the
information-row reveals a More button
![](media/image31.png){width="0.17708333333333334in"
height="0.23958333333333334in"} with the following options: View
Battleground, View Report, Delete. For campaigns that are currently
running, there is also an option to pause the campaign.

### Viewing Information on a Selected Campaign

Clicking on a campaign in a scenario campaign list selects the campaign
and displays a panel of buttons at the bottom of the screen:

![](media/image40.png){width="6.254166666666666in"
height="4.3165463692038495in"}

*Scenario Campaign List Buttons*

The buttons enable you to view a report or view the campaign
battleground ![](media/image41.png){width="0.5746248906386702in"
height="0.18229221347331584in"}![](media/image41.png){width="0.7804068241469816in"
height="0.18229221347331584in"} as well as performing other functions:
pause/resume ![](media/image42.png){width="0.46679680664916884in"
height="0.19555008748906386in"}, force completion of the campaign
![](media/image43.png){width="0.17368438320209975in"
height="0.18333333333333332in"}, delete the campaign
![](media/image44.png){width="0.1901038932633421in"
height="0.18397200349956255in"}, or flag the campaign
![](media/image45.png){width="0.19791666666666666in"
height="0.19791666666666666in"}.

Selecting a campaign also displays further information about the
campaign on the Information pane at the right of the screen:

The top of the Information pane displays Start Date, End Date, and
Duration of the selected campaign.

The **Network Summary** details the number of entities (devices, data,
network, or cloud ) in the network that were Compromised, Reconned, or
that remained Undiscovered by the campaign. Placing the cursor over one
of these categories changes the display in the circle to reflect the
![](media/image46.png){width="2.21in" height="6.44in"}percentage of
these categories. The percentage is displayed as red for Compromised,
blue for Reconned, and gray for Undiscovered, with parts of the circle
around the percentage, color-coded accordingly. For example, Figure 13.
represents the number and percentage of the network that was
compromised.

The **Asset Summary** provides details on the assets that were
compromised in the campaign. The summary shows statistics for three
asset categories: Device, Data, and Network assets. As with the Network
Summary, placing the cursor on one of these categories displays the
percentage of such assets in the circle.

The Data Yield for the campaign is displayed in gigabytes below the
Network and Asset summaries.

![](media/image47.png){width="2.1041666666666665in"
height="2.5194444444444444in"}The Information pane also lists the **TOP
METHODS** used by the campaign that were successful in compromising the
network. The name of each method is listed along with the number of
devices compromised by the method, as well as the percentage of the
network compromised by that method. The percentage is also displayed
graphically as a section of red along a grey line:

Clicking the name of a method displays a **Campaign Report**, with links
to additional details, including information on how methods function.

![](media/image49.png){width="6.270833333333333in"
height="2.8472222222222223in"}

*Method Details Report Section*

Scrolling to the bottom of the Campaign Information pane displays the
Scenario Configuration, containing the following information and
pop-downs:

**Scope (all)**: the number of entities included in the scenario.

**Breach Points**: the number of devices that were the starting points
for the scenario. Clicking this number lists the names of the devices in
a pop-down.

**Assets**: the number of assets in the scenario. Clicking the number
displays the names of the assets that are part of the scenario in a
pop-down.

**Exclusions**: the number of attack methods that were excluded from the
campaign. Clicking this number displays the names of the attack methods
that were excluded.

![](media/image50.tiff){width="2.655586176727909in"
height="2.2408934820647417in"}

CREATING AND MODIFYING SCENARIOS
================================

This chapter explains how to create or modify the scenarios that specify
the parameters for running campaigns. Scenario parameters determine the
following:

-   campaign scope

-   the breach point (entity or entities from which the campaign starts)

-   rules for which devices are defined as assets

-   duration of the campaign

-   campaign schedules

and other attributes of a campaign.

![](media/image51.png){width="3.0368055555555555in" height="1.7083333333333333in"}Creating a New Scenario
---------------------------------------------------------------------------------------------------------

You can create a scenario by clicking the New Scenario button at the top
of the Scenario Hub screen and naming the scenario.

![](media/image52.tiff){width="6.268055555555556in"
height="3.777415791776028in"}Clicking Confirm begins the Scenario
definition process, beginning with Scope.

Then proceed through the following steps, using the Plus button
![](media/image53.tiff){width="0.23879811898512687in"
height="0.23879811898512687in"} to add attributes at each stage and the
Next and Previous links at the bottom of the screen to move through the
various steps.

1.  Define the **Scope** of campaigns run by the scenario. By default,
    > all Entities are included.

2.  Define **Breach Points** for campaigns run by the scenario.

3.  Define **Assets** -- device, data, network and cloud assets for
    > campaigns run by the scenario.

4.  Add **Exclusions** for specific methods, pathnames, or credentials
    > from campaigns run by the scenario.

5.  Configure scenario **Settings** to edit scenario name, add an
    > optional description, and specify settings for scheduling
    > campaigns and duration.

![](media/image54.tiff){width="2.186111111111111in"
height="1.9041666666666666in"}Note that returning to earlier steps
requires that you repeat the subsequent steps and reset the parameters
for each step (i.e., if you return to step 3, you must repeat steps 4
and 5).

The following section describes each scenario creation step in detail.

### Step 1: Define Scope Rules

![](media/image55.tiff){width="2.1979166666666665in"
height="3.161111111111111in"}This step defines the rules that identify
which entities (Devices, Data, Network or Cloud) are included in the
scope of campaigns run by the scenario. All entities are included by
default and XM Cyber recommends not limiting the scope without specific
requirements to do so. Clicking the **Plus** button
![](media/image56.png){width="0.13753280839895013in"
height="0.16927055993000875in"} lets you add a new rule specifying the
exact entities to include in a scenario.

For each entity type in the pull-down, proceed to add scope rules by
clicking **Add Rule**
![](media/image58.png){width="0.5054910323709536in" height="0.24375in"}
and choosing from the listing, as illustrated for **Devices** with
**Device Type** set to Computer.

![](media/image59.png){width="6.190041557305337in"
height="2.545138888888889in"}

*Set Scope Rules Screen*

![](media/image61.png){width="1.9in" height="4.24in"}Once you choose
your desired entity types and entities (Devices, Data, Network and
Cloud) for inclusion in the scenario, they will appear in the **Scope
Rules** listing.

You can display all entities in the system by clicking the **All
Entities** tab (not just those in the current rule set). You can then
add entities to the scope of the scenario by selecting it on the **All
Entities** tab and clicking
![](media/image63.png){width="0.37331911636045495in"
height="0.13913057742782153in"}at the bottom of the screen. Similarly,
you can remove devices from the scenario scope by selecting the
device(s) on the **Scope** tab and then locating the selected devices on
the **All Entities** tab and clicking Remove at the bottom of the
screen.

You can also customize which columns are displayed on the **Scope** and
**All Entities** tabs by using the **Show/Hide** button at the right of
the screen.

When you are finished setting the Scope Rules, click **Next, Define
Breach points** at the bottom right of the screen.

### ![](media/image64.png){width="1.9747287839020122in" height="3.8434776902887138in"}Step 2: Define Breach Points

The **Define Breach Points** screen enables you to select entities
(Device, Data, Network or Cloud) as breach points for the scenario. By
default, no breach points are defined in a scenario and at least one is
required. It is advised to start defining a campaign using entities
considered most vulnerable to a hacker. For example, these entities
might be specific computers, network domains, or cloud users/tokens.

As you add entities (if they are actually present in your environment),
each is displayed as a rule in the **Breach Points Rules** pane and in
the Breach Points listing on the right hand part of the screen.

As with determining Scope in the previous section, you can use the
**Breach Points** tab to delete breach points and the **All Entities**
tab to add them to a given rule.

![A screenshot of a cell phone Description automatically
generated](media/image65.tiff){width="6.268055555555556in"
height="2.2368055555555557in"}

Breach Points Tab display

**NOTE**: You must define at least one breach point before proceeding to
the next stage.

After defining breach points, click **Next, Define Assets**
![](media/image66.png){width="0.7894389763779528in"
height="0.23998906386701663in"}at the bottom of the screen.

### Step 3: Define Assets

![](media/image67.tiff){width="2.26in" height="2.64in"}The Define Assets
screen enables you to define rules that identify assets within your
system. By default, no assets are defined for a scenario and at least
one asset is required. Asset rules can be defined for entities known to
XM Cyber, as with scope and breach points. For example, a device may be
considered an asset if it performs a specific role such as a server, if
it stores data contained in specific files, or if it is located in a
certain subnet or workgroup.

To create an asset rule, click the **Plus** button
![](media/image56.png){width="0.13753280839895013in"
height="0.16927055993000875in"} to choose the asset type and see the
available entities for that type. You can use the **Assets** and **All
Entities** tabs in the main pane to view/remove assets already included
or to add new ones from **All Entities**.

![A screenshot of a cell phone Description automatically
generated](media/image68.tiff){width="6.268055555555556in"
height="3.452777777777778in"}

*Define Assets Screen Showing Rules for Cloud Assets*

Asset rules may overlap and specify the same device. For example, the
same computer may conform to the rule for a specific computer name as
well as fulfill a role included in the device rules, such as Web Server.

After defining assets, click **Exclusions** at the bottom of the screen
to move to the next step.

### Step 4: Exclusions

You can exclude specific methods or parameters, such as CVEs and
credentials, from participation in scenarios. Exclusion enables you to
customize scenarios to control how they affect your network. For
example, you can remove a method to simulate a remediation action.

![A screenshot of a social media post Description automatically
generated](media/image69.tiff){width="6.268055555555556in"
height="2.1034722222222224in"}

Initial Exclusions screen

![](media/image71.png){width="3.1145833333333335in"
height="2.2729166666666667in"}There are no exclusions defined by default
and none are required to move to the next step.

To exclude a method:

1.  Click the **Plus**
    > ![](media/image56.png){width="0.13753280839895013in"
    > height="0.16927055993000875in"} button to create an **Exclusion**

2.  ![](media/image72.tiff){width="3.1282797462817147in"
    > height="2.7264490376202977in"}Click the **Methods** drop-down to
    > select a method type. By default, all methods found in the
    > environment will be excluded.

3.  ![](media/image73.png){width="3.2579702537182853in"
    > height="2.420893482064742in"}To add a parameter to the method,
    > underneath **Parameters**, click the **Add new parameter** button
    > ![](media/image75.png){width="0.19791666666666666in"
    > height="0.20833333333333334in"} and select a parameter type from
    > the Parameters dropdown:

4.  To add an additional parameter, click the **Add** button
    > ![](media/image75.png){width="0.19791666666666666in"
    > height="0.20833333333333334in"} at the right of the **Parameter**
    > box. To remove a parameter, click the
    > ![](media/image76.png){width="0.20833333333333334in"
    > height="0.20833333333333334in"}at the right of the parameter to
    > remove.

5.  After adding parameters to the method, click the **Exclude** button
    > ![](media/image77.png){width="0.7744794400699913in"
    > height="0.23025043744531934in"}. The method, along with its type
    > and parameters, is displayed on the **Exclusions** screen.

After adding exclusions, click **Settings** at the bottom of the screen
to move to the last step, **Settings**.

### Step 5: Settings

In this step, the **Settings** screen lets you further customize various
attributes of a scenario

![A screenshot of a cell phone Description automatically
generated](media/image78.tiff){width="5.991790244969379in"
height="3.577415791776028in"}

*Scenario Settings Screen*

This screen contains the following configuration options:

+--------------------------------+------------------------------------+
| **Scenario Name**              | Edit the scenario name visible in  |
|                                | various contexts.                  |
+--------------------------------+------------------------------------+
| **Description**                | Enter an optional description for  |
|                                | the scenario.                      |
+--------------------------------+------------------------------------+
| **Maximum Running Campaigns:** | Specify the maximum number of      |
|                                | campaigns that can be run          |
|                                | concurrently by the scenario.      |
+--------------------------------+------------------------------------+
| **Complete Campaigns:**        | Specify the conditions to          |
|                                | terminate the campaign: when the   |
|                                | entire network is compromised, or  |
|                                | when all assets are compromised.   |
|                                | You can choose either or both      |
|                                | options. Selecting neither will    |
|                                | run the campaign for the duration  |
|                                | specified in **Campaigns run       |
|                                | for**.                             |
+--------------------------------+------------------------------------+
| **Campaigns run for:**         | Specify the duration of campaigns  |
|                                | run under the scenario.            |
+--------------------------------+------------------------------------+
| **Multiple Attack Vectors:**   | **Recommended to enable**          |
|                                |                                    |
|                                | Allows assets to be compromised    |
|                                | multiple times via different       |
|                                | attack vectors. After the first    |
|                                | attack, an asset can be            |
|                                | compromised again via another      |
|                                | attack vector, to find all         |
|                                | compromises and report them in     |
|                                | order of complexity.               |
+--------------------------------+------------------------------------+
| **Generate Campaigns Now:**    | Select for generating new          |
|                                | campaigns immediately or later, at |
|                                | your convenience.                  |
+--------------------------------+------------------------------------+

When you are finished entering the settings, click **Review** at the
bottom of the screen.

### Step 6: Review

This final step lets you review the scenario settings. You can change
settings by clicking the **Edit** button
![](media/image79.png){width="0.17708333333333334in" height="0.21875in"}
at the top right corner of each step encountered above (Scope, Breach
Points, etc.).

When you are satisfied with the settings, click the **Create Scenario**
button ![](media/image81.png){width="0.8673173665791776in"
height="0.22536636045494313in"} at the bottom of the screen. The
Scenario is now displayed as a card on the **Scenario Hub** screen.

![A screenshot of a cell phone Description automatically
generated](media/image82.tiff){width="6.268055555555556in"
height="3.428472222222222in"}

Review Screen

### Editing Scenario Settings

You can edit the settings of any scenario on the **Scenario Hub**
screen. You can change all settings including scope settings, breach
points, assets, and scheduling settings.

![](media/image83.png){width="2.8020833333333335in"
height="3.547825896762905in"}To edit a scenario:

1.  On the **Scenario Hub** screen, select a scenario and at the upper
    > right of the card, click the **Edit** button. The Review screen
    > appears (see above).

```{=html}
<!-- -->
```
2.  Review the settings and click the **Edit** button
    > ![](media/image84.png){width="0.13541666666666666in"
    > height="0.15625in"} at the top right of the step whose settings
    > you want to edit. A screen will appear enabling you to edit the
    > settings of the selected step.

3.  After completing the settings for a particular step, click the
    > **Save Changes** button
    > ![](media/image85.png){width="0.9218755468066492in"
    > height="0.295in"} at the lower right of the screen.

4.  After completing your edits, click **Close**.

Manually Generating a Campaign from a Scenario
----------------------------------------------

![](media/image86.tiff){width="2.75625in"
height="4.156522309711286in"}To start a campaign manually from an
existing scenario:

1.  On the **Scenarios** screen, select the scenario from which you want
    to start the campaign.

2.  At the top of the scenario's card, click the **More** button (three
    dots) and click **Generate** **New Campaign**.

3.  A new campaign is generated according to the scenario settings.

VULNERABILITY MANAGEMENT
========================

The Vulnerability Management module enables you to view your XM Cyber
sensors in a layout specifically designed to guide you in continuous
vulnerability assessments and remediation for your Windows devices.

This module displays information about vulnerabilities affecting your
system from multiple perspectives:

-   the vulnerabilities affecting your network, detailed descriptions
    about those vulnerabilities, and details about all of the devices in
    your network that are affected by them

-   the devices affected by vulnerabilities, and information about all
    of the vulnerabilities affecting each of them

-   the patches that will remediate vulnerabilities, and details about
    those patches including which vulnerabilities each fixes

The overview and details provided from this module help you prioritize
vulnerabilities so you can easily focus on and fix the most urgent
vulnerabilities and the most vulnerable devices, with the most
comprehensive patches. Once you've patched the vulnerabilities, you can
also send mails directly from the system notifying of actions taken
based to those parties who submitted related requests.

Navigating the Vulnerabilities Management Module
------------------------------------------------

From the side panel, select the **Vulnerabilities Management** option:

The Overview, default, tab is displayed:

The module offers these tabs:

-   Overview

-   Vulnerabilities

-   Devices

-   Patches

-   Requests

Overview
--------

The Overview tab displays an overview of the current status of your
scenarios, including a summary of:

-   The most recently discovered vulnerabilities (based on the
    information in the Vulnerabilities tab)

-   The vulnerabilities not yet handled, divided by severity, and how
    many vulnerabilities have been in the network for the indicated
    periods of time (in days) (based on the information in the
    Vulnerabilities tab)

-   The most recent pending patch requests (based on the information in
    the Requests tab)

-   Missing patches (based on the information in the Patches tab) -
    displays the number of patches that need to be applied

### Gaining insight

-   Hover over any of the pies or charts to view additional details
    about the summary information displayed.

-   Click View all for any of the summaries. XM Cyber redirects you to
    the relevant tab.

Vulnerabilities
---------------

The Vulnerabilities tab displays all of the vulnerabilities that were
found in your network in any of your scenarios, with Vulnerabilities as
the key. The table appears similar to the following example:

### Manipulating the data

From this tab, you can customize the columns that appear, and you can
sort and filter the data as follows:

-   Click Show/Hide to display the list of columns and check or uncheck
    the different columns of data:\
    \
    Additionally, click **Restore default** to return the display to the
    default display, which shows these columns:

    -   Vulnerabilities

    -   CVSS v3

    -   Affected Devices

    -   Products

    -   First Detected

    -   Updated

-   Click any column to sort (up or down) the entire table by that
    column.

-   Filter data:

    -   Type any keyword in the search box to filter the table and view
        only rows containing that keyword.

    -   Click to

    -   Click to toggle between case sensitive, and not case sensitive.

-   Click to export to a CSV (comma separated values) file:

    -   the data for the selected rows, when one or more is selected

    -   the data for all of the rows in the system, when no rows are
        selected

**Note:** Even when you've hidden a column, its data is still used when
filtering.

### Gaining insight

We recommend you start by sorting the table according to CVSS v3 score
in order to view the vulnerabilities with the highest severity first.
These are the vulnerabilities determined to be the greatest risk to any
network.

Once you view the highest scored vulnerabilities at the top of your
list, try selecting those with the most affected devices, similar to the
following:

As you select rows, the summary at the bottom of the table updates with
the total number of unique devices affected and the total number of
unique patches that can fix those vulnerabilities.

Often times, the vulnerabilities are fixed with shared patches, as in
the above example. This makes the overall picture clearer, and easier to
prioritize which vulnerabilities should be handled first.

### Understanding the vulnerabilities

To understand the vulnerabilities better, click anywhere on the row that
you're investigating. The right-side panel opens with a detailed
explanation and additional data about the vulnerability and how it's
affecting your system specifically:

Hover over the data listed in the **Affected Devices** area to view that
data in the graphical display.

To gain additional insights, click the number in the button that appears
next to **Affected Devices**. The page redirects to the **Devices** tab,
filtered to only those devices affected by the specific vulnerability.

### Managing fix timelines 

From the right-side panel, you can enter:

-   **SLA** -- click the field to enter a date by which you intend on
    fixing the vulnerability

-   **Comments** -- enter any useful free text

Once you enter information in these fields, you can sort and filter data
according to SLA date.

Additionally, if there is data for at least one vulnerability, then the
relative column is also included whenever you download a CSV version of
the data.

### CSV export

  Column                    Description
  ------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------
  CVE ID                    The official CVSS identifier for the vulnerability. This is the same as the number that appears in the Vulnerability column from the user interface.
  Affected entities count   The number of devices affected by the vulnerability.
  Detected at               The date on which the vulnerability was identified in your network.
  CVSS V2                   The score, or severity, of the vulnerability according to CVSS v2.
  CVSS V3                   The score, or severity, of the vulnerability according to CVSS v3.
  Published on              
  Type                      
  Products                  The software or applications on the affected devices that carry the vulnerability.
  CVE num                   
  SLA                       If enter a date by which you plan on handling at least one vulnerability, then the **SLA** column is also included whenever you download a CSV version of the data.
  Comments                  If enter comments for at least one vulnerability, then the **Comments** column is also included whenever you download a CSV version of the data.

Devices
-------

Patches
-------

Requests
--------

THE BATTLEGROUND
================

The **Battleground** offers a real-time graphical view of the progress
of an ongoing campaign. The Battleground can also play back a completed
campaign. The **Battleground** provides layers of information that
reflect the progress of a campaign and a timeline. Information includes
the identity of each node participating in the campaign, its status at
any time in the campaign (compromised, reconned, or undiscovered), as
well as listing events that caused the change of status.

![](media/image87.tiff){width="1.8402777777777777in"
height="2.7125in"}Zoom out to display the top layer of information with
a bird's eye view of organizational units, workgroups, subnets, etc. By
zooming in, you view a graphical representation of each device in the
campaign along with its identity, a timestamp of the event that changed
its status, and the source of the event.

Navigating to the Battleground
------------------------------

There are multiped ways to display the **Battleground** screen. The
simplest path is to click the **Battleground** button on the main
navigation strip on the left-hand side of the XM Cyber display.

To display the **Battleground** for a campaign:

1.  On the **Scenario Hub** screen, select a scenario card.

2.  ![](media/image89.png){width="2.3895833333333334in"
    height="3.234782370953631in"}Then, do one of the following:

-   Use the slider in the selected card to locate a campaign along the
    > displayed timeline and click once. Click the **View Battleground**
    > button that appears at the right bottom corner of the card:

> --**OR**--

-   Click the oval next to the scenario name displaying the number of
    > campaigns run by the scenario. From the displayed list of
    > scenarios select a campaign and click the **View Battleground**
    > button at the bottom of the screen.

![](media/image90.png){width="6.236111111111111in"
height="4.520049212598425in"}

--**OR**--

-   On the **Scenario Hub** screen, select a scenario, and on the
    **Scenario Information** pane that appears at the right of the
    screen, click the **Campaigns** link under the scenario title. A
    similar list of campaigns is displayed. Select a campaign and click
    the **View Battleground** button at the bottom of the screen.

Understanding the Battleground Screen
-------------------------------------

Below is the opening battleground display.

The **Battleground** screen displays several key pieces of information
and features controls to adjust your view of the Battleground, as
follows

### Screen Layout

The screen is broken into a number of functional areas: Campaign Info,
Ribbon, Events and Event Log, Campaign Visualization, Timeline and
Playback Control. The following sections describe each in detail.

![A screenshot of a cell phone Description automatically
generated](media/image91.tiff){width="6.268055555555556in"
height="3.2645833333333334in"}

*Battleground Screen Layout*

### Ribbon

At the top of the screen is a ribbon displaying information and display
controls.

![](media/image92.png){width="6.2362204724409445in"
height="0.3464566929133858in"}

*Battleground Ribbon*

![](media/image93.png){width="2.86in" height="2.98in"}On the left-hand
side of the ribbon, above the central display, is displayed the name of
the scenario and campaign. For example, in the figure above, the
campaign 000093 is running under the Model Tester scenario. The ribbon
includes a button for displaying reports on the campaign
![](media/image94.png){width="0.18541666666666667in"
height="0.18541666666666667in"} and scenario, as well as icons
indicating the number of online sensors, the number of compromised
assets compared to the total number of assets, the data yield in
gigabytes, the number of breach points, and the number of exclusions.

Clicking the dropdown menu next to the **scenario: campaign name**
displays a list of other campaigns run by the same scenario. Each
campaign in the list displays the date and time of the start of the
campaign as well as percentages of the network and assets that were
compromised. Clicking a campaign displays the associated
**Battleground**.

Hovering over a campaign in the list displays additional information on
the number of devices, data, and network assets compromised in the
campaign.

The ribbon has buttons that enable control of the display, described in
the following table.

+----------------------------------+----------------------------------+
| **Ribbon Elements**              | **Function**                     |
+----------------------------------+----------------------------------+
| ![](medi                         | **Settings** - displays a        |
| a/image96.png){width="0.53125in" | dropdown menu with two sections. |
| height="0.3828127734033246in"}   |                                  |
|                                  | The upper section displays       |
| ![](media/image97.ti             | options to customize the         |
| ff){width="1.8444444444444446in" | display:                         |
| height="2.4409722222222223in"}   |                                  |
|                                  | **Auto Zoom**: zooms on devices  |
|                                  | in close proximity to attacks    |
|                                  | displayed in the Events and      |
|                                  | Event log area.                  |
|                                  |                                  |
|                                  | **Auto Zoom On Attack Path       |
|                                  | Event**: Automatically zooms     |
|                                  | into a selected attack path as a |
|                                  | user steps through them          |
|                                  |                                  |
|                                  | **Auto Play Attack Path:** zooms |
|                                  | on attack path(s) during         |
|                                  | playback of past campaigns       |
|                                  |                                  |
|                                  | **Show Assets Choke Points --**  |
|                                  | highlight devices presenting the |
|                                  | greatest risk to the environment |
|                                  |                                  |
|                                  | **Cluster Type**                 |
|                                  |                                  |
|                                  | The lower section of the menu is |
|                                  | labeled **Cluster type** and     |
|                                  | displays options to enable       |
|                                  | display of the **Battleground**  |
|                                  | in a grouping of computers by    |
|                                  | the following criteria: Network  |
|                                  | Subnet, Domain/Workgroup,        |
|                                  | Computers Organizational Unit,   |
|                                  | or Users Organizational Unit.    |
+----------------------------------+----------------------------------+
| ![](media/image100.p             | **Search** -- enables search for |
| ng){width="0.5234372265966755in" | strings in the **Battleground**. |
| height="0.3828127734033246in"}   | For example, to find and display |
|                                  | a list of all computers with     |
|                                  | Server in their name. Clicking   |
|                                  | an item in the list zooms in on  |
|                                  | the item.                        |
+----------------------------------+----------------------------------+

###  

### ![](media/image101.tiff){width="2.35in" height="1.61in"}Campaign and Event Info Panel

The left-hand area of the **Battleground** screen features a panel
displaying general information on the campaign, a summary of compromised
devices and methods of compromise, and access to more detailed logs of
compromise events.

![](media/image102.png){width="2.4in" height="4.04in"}The large circle
on the left of the Tracker shows the percentage of compromised devices
reflecting selections on the Campaign Visualization. This circle changes
to a small horizontal bar with scrolling down the list of methods. The
smaller circles on the right of the Tracker (Compromised, Reconned,
Undiscovered and Assets Only) are actually buttons. These buttons let
you filter the visualization to show only clusters with the associated
status, i.e., clicking **Compromised** will highlight compromised
clusters in white and redraw all others in black (but not fully hide
them). Filtering also recalculates the value in the larger tracker
circle.

Clicking on the methods listed below the tracker changes the
**Battleground** visualization to show only devices compromised by that
method. Note that the number of devices compromised by a given method is
displayed above the methods list These selections determine the content
display on the **Battleground**. Clicking on the lines in this area
displays details about the **Battleground.** such as **Compromised** or
**Reconned**.

![](media/image103.tiff){width="2.386111111111111in" height="3.2in"}The
bottom part of this panel features four event-type tabs that follow the
MITR ATT&CK TTP:

-   **Compromise -** a device or asset can be compromised

-   **Recon -** a device or asset can be discovered

-   **Hacking** - an action an attacker would take to modify a system

-   **Environment -** user and device behaviors

With listings of the methods encountered of the type specified by the
tab. Clicking on the method opens a log of attacks made thus far in a
campaign, showing the number of attacks and a list of the attacks
themselves. Each attack shows the device IP address of the origin of the
attack and the name of the device under attack, and the date and time of
the attack. Colored symbols indicate whether the attack resulted in a
compromised or reconned device (red circles indicate compromise, blue,
recon).

Clicking a log entry displays the attack on the **Battleground**
visualization panel.

Campaign Visualization
----------------------

The **Campaign Visualization** panel is the main focus of the
Battleground, where the "action" occurs. The rest of this section will
concentrate on this panel and its uses.

### Battleground Opening Display: Viewing Clusters

Upon opening a campaign **Battleground**, XM Cyber displays the clusters
involved in the campaign. Clusters appear as hexagons filled with
circles representing monitored devices.

By default, the display shows clusters organized by Microsoft Active
Directory organizational units. Clicking the **Settings** button on the
ribbon allows changing the display as explained in the table above.

As devices in a cluster progressively become compromised or reconned,
the sides of the hexagon in which they are grouped turn red or blue,
respectively. At the edge of each hexagon are displayed the total number
of devices in the cluster and the number of compromised nodes.

![A screen shot of a computer Description automatically
generated](media/image104.jpeg){width="6.268055555555556in"
height="4.266666666666667in"}

*Opening Battleground Display Showing Clusters displayed by Organization
Unit*

![](media/image105.png){width="1.56in" height="2.63in"}Hovering over the
edge of a cluster displays the cluster IP address and percentage of
compromised devices in it*.*

By using the mouse wheel or the **Zoom** buttons at the right side of
the screen, you can display more information for each device. Icons in
the hexagon represent devices according to the following scheme.

Device names are displayed below the icon. Hovering over the icon
displays its IP and operating system, and the compromise or recon method
for the device.

Assets are indicated by diamond shaped icons. described in the table
below.

  --------------------------------------------------------- -------------------------------------------------
  ![](media/image106.png){width="0.31in" height="0.35in"}   Compromised breach point (Windows device)
  ![](media/image108.png){width="0.31in" height="0.35in"}   Compromised Windows device
  ![](media/image109.png){width="0.31in" height="0.35in"}   Reconned Windows device
  ![](media/image110.png){width="0.31in" height="0.35in"}   Disconnected reconned Windows device
  ![](media/image111.png){width="0.31in" height="0.35in"}   Undiscovered Windows device
  ![](media/image112.png){width="0.31in" height="0.35in"}   Disconnected undiscovered Windows device
  ![](media/image114.png){width="0.31in" height="0.35in"}   Compromised breach point (Windows device asset)
  ![](media/image116.png){width="0.31in" height="0.35in"}   Compromised Windows device asset
  ![](media/image118.png){width="0.31in" height="0.35in"}   Reconned Windows device asset
  ![](media/image119.png){width="0.31in" height="0.35in"}   Undiscovered Windows device asset
  ![](media/image121.png){width="0.31in" height="0.35in"}   Compromised Linux device asset
  ![](media/image122.png){width="0.31in" height="0.35in"}   Reconned Linux device asset
  ![](media/image123.png){width="0.31in" height="0.35in"}   Undiscovered Linux device asset
  ![](media/image124.png){width="0.31in" height="0.35in"}   Compromised Linux device
  ![](media/image125.png){width="0.31in" height="0.35in"}   Reconned Linux device
  ![](media/image126.png){width="0.31in" height="0.35in"}   Undiscovered Linux device
  --------------------------------------------------------- -------------------------------------------------

*Cluster device icon descriptions*

### ![](media/image127.jpeg){width="4.0256944444444445in" height="4.225694444444445in"}Viewing Attacks 

Events that cause nodes to be compromised or reconned are indicated as
red/blue arrows. For currently running campaigns, arrows appear in real
time to indicate attacks in progress. To view attacks that have already
occurred, click on the node.

An arrow appears leading from the attacking device to the compromised or
reconned node. If the attacking node itself was compromised from a
breach point, an arrow is displayed showing that as well:

![](media/image128.png){width="2.4097222222222223in"
height="3.9819444444444443in"}Note that the arrows come and go as the
simulation progresses, in real-time or across the time-line of a
recorded attack.

Details of attacks that have occurred up to the time specified on the
timeline are represented in the **LOG** area on the panel at the left of
the screen:

![](media/image129.png){width="2.451388888888889in"
height="2.234782370953631in"}You can also scroll through the log to view
all attacks. To view the attack on a specific node, click the node on
the **Battleground** display; the **LOG** jumps to the attack that
compromised or reconned the node:

#### Zooming

You can clarify your view of the **Battleground** by zooming in. Zooming
enables you to view each compromised or reconned device by name. Zooming
in and out can also increase your understanding of the campaign. For
example, zooming out to the top level emphasizes events across device
clusters. Arrows indicate the cluster from which attacks originated and
the number of attacks. Red arrows indicate attacks that compromised
devices, while blue arrows indicate attacks that enabled a hacker to
discover (recon) a device.

![A close up of a logo Description automatically
generated](media/image130.tiff){width="6.268055555555556in"
height="4.209027777777778in"}

Battleground Display Zoomed Out to the Top Level

### Using the Timeline to View the Progress of a Campaign

You can view the progress of an already finished campaign by using the
timeline and navigation and play buttons at the bottom of the screen. To
display navigation buttons, first, click the **Hide** arrowhead at the
top right of the **Campaign Information Panel** to remove the
information display.

+----------------------------------+----------------------------------+
| The Play and Navigation buttons  | ![](media/image131.p             |
| are displayed at the bottom of   | ng){width="2.1979166666666665in" |
| the screen.                      | height="0.3854166666666667in"}   |
|                                  |                                  |
|                                  | *Timeline Playback Controls*     |
+----------------------------------+----------------------------------+

The campaign **Timeline** is displayed at the bottom of the screen. The
**Timeline** displays time in increments that you can specify as
explained below. The full **Timeline** also displays a graph indicating
the percentage of devices that the campaign has compromised. To display
the timeline together with its graph, click the **Timeline Display**
button ![](media/image132.png){width="0.3125in"
height="0.16666666666666666in"} at the right bottom corner of the
screen. The **Timeline**, together with its graph, appears at the bottom
of the screen

![](media/image133.png){width="6.268055555555556in"
height="0.9756944444444444in"}

![](media/image134.png){width="0.8083333333333333in"
height="1.7833333333333334in"}*Timeline Display*

The white marker can be dragged to an exact time on the **Timeline** and
displays the percentage of the system compromised up until that time

Clicking a point on the timeline displays attacks that have occurred up
until that time on the **LOG**. You can easily scroll the **LOG** upward
from the last attack to view previous attacks. Clicking at the right
side of the attack display on the **LOG** displays the attack
graphically on the **Battleground**:

![A screenshot of a computer Description automatically
generated](media/image135.tiff){width="6.268055555555556in"
height="3.45625in"}

*Attach log entries correspond to Battleground arrows*

The **Timeline** also displays red and blue markers to indicate the
attacks that occurred at that time. Double-clicking a marker on the
**Timeline** jumps to the corresponding attack on the log. Compromised
assets are indicated by red diamond markers on the timeline.

#### ![](media/image136.png){width="2.2958333333333334in" height="0.7125in"}Modifying time intervals on the timeline

You can increase or decrease the time interval displayed on the
**Timeline** by expanding or contracting the bar underneath the
timeline, at intervals between 1\
second and 15 minutes.

  -------------------------------------------------------------------------- ----------------------------------------
  **Button:**                                                                **Function:**
  ![](media/image137.png){width="0.40625in" height="0.5520833333333334in"}   Long Jump Backward
  ![](media/image137.png){width="0.40625in" height="0.5520833333333334in"}   Jump to Previous Event
  ![](media/image137.png){width="0.40625in" height="0.5520833333333334in"}   Play/Pause
  ![](media/image137.png){width="0.40625in" height="0.5520833333333334in"}   Jump to Next Event
  ![](media/image137.png){width="0.40625in" height="0.5520833333333334in"}   Long Jump Forward
  ![](media/image137.png){width="0.40625in" height="0.5520833333333334in"}   Current Speed; Increase/Decrease Speed
  -------------------------------------------------------------------------- ----------------------------------------

*Timeline Control Buttons*

The **Timeline** displays events as colored lines (red for compromised
events, blue for reconned). You can use the **Zoom** buttons on the
right side of the **Timeline** to zoom in and out. When you zoom out to
view only clusters, lines represent groups of events with the number of
events displayed inside a circle on the line:

![A close up of a logo Description automatically
generated](media/image130.tiff){width="6.298616579177603in"
height="3.208695319335083in"}

*Cluster View with Numbers of Events Displayed inside Circles*

Clicking on an event on the **Timeline** navigates to the device and the
attack that compromised or reconned the device on the **Battleground**.
If the event represents a group of events, all events in that group are
displayed.

![](media/image138.png){width="1.4069444444444446in"
height="2.220833333333333in"}You can also navigate the timeline by
dragging the purple marker.

You can also move the marker by double clicking on any location on the
**Timeline**; the marker jumps to the location selected.

As you move across the **Timeline**, the **Battleground** changes to
display events that occurred at the specified time. By alternately using
the **Zoom** and **Filter** buttons, you can gain an accurate picture of
how the campaign progressed and identify how devices were compromised or
reconned.

### Color Key

The use of colors on the **Battleground** aids in understanding the
campaign. Undiscovered devices appear in grey. A device turns color when
compromised (red) or reconned (blue). Events that triggered the change
in status are displayed as red or blue arrows. The arrows originate from
the device that caused the event to the device whose status was changed
as a result. For example, a typical **Battleground** display looks like
this

![](media/image139.tiff){width="6.077312992125984in"
height="5.190972222222222in"}:

*Battleground Display with different colored arrows*

There are four arrows colors that correspond to different attack
activities

-   Red Arrow -- Compromise

-   Blue Arrow -- Recon

-   Yellow arrow -- Hacking

-   Grey arrow -- Environment activity

-   Dotted yellow line -- credential harvest from another source

### Modifying the Display Using Filter Buttons

![](media/image140.jpeg){width="1.6520833333333333in"
height="1.9215277777777777in"}![](media/image141.png){width="2.8645833333333335in"
height="0.8086964129483815in"}On the top right of the **Battleground**
information panel are filter buttons that enable filtering the
**Battleground** and display devices according to their status:
compromised, reconned, or undiscovered.

Moreover, you can restrict the display to assets only. For example, you
can select the **Compromised** and **Assets** only buttons, resulting in
a display showing only compromised assets (see below)

![](media/image143.png){width="3.3069444444444445in"
height="3.2956528871391075in"}

Zooming in to this area displays\
additional detail for each node.

![](media/image144.png){width="2.0in" height="1.7395833333333333in"}

![](media/image145.tiff){width="3.4694444444444446in"
height="0.9043482064741907in"}*Zoomed-in Linux Device Asset*

### Campaign Playback

The **Battleground** supports playback of previously run campaigns. When
you open a pre-recorded campaign, **Playback Controls** will appear in
the lower left-hand part of the **Campaign Visualization** pane. The
buttons, left to right, control rewind, play, play to next log entry,
fast-forward to end, and adjust playback speed pop-up menu (0.5X -- 4X).

As you playback a campaign, the **Campaign Visualization** pane steps
through the pre-recorded activities, reflected in the **Timeline** at
the bottom of the display.

Vulnerability Management
========================

The Vulnerability Management module

Vulnerabilities
---------------

Devices
-------

Patches
-------

Requests 
--------

REPORTS
=======

XM Cyber provides detailed reports on campaigns currently underway or
already finished. Reports can be viewed on-screen or can be downloaded
as PDF files. Reports provide useful summaries of scenarios, campaigns,
technical details, and remediation advice.

How to Access Reports
---------------------

### ![](media/image146.tiff){width="2.2in" height="2.897222222222222in"}Accessing Reports from the Scenario Hub

#### Scenario Reports

To view a scenario report, from the **Scenario Hub** screen, select a
scenario card. Make sure you only click in the white space surrounding
the scenario content. If you click on the scenario timeline graph, you
will end up selecting a single campaign for that scenario. Once you have
chosen a scenario, click the View Report button
![](media/image147.tiff){width="1.0in" height="0.20026027996500437in"}
(the button fill will be white).

#### Campaign Reports

![](media/image148.tiff){width="2.1in" height="2.7534722222222223in"}To
view a campaign report, from the **Scenario Hub** screen, select a
scenario card. Move your mouse across the campaign timeline graphic in
the middle of the card until you find your campaign of interest. Click
in the white space surrounding the scenario content. If you click on the
scenario graph, you will end up selecting a single campaign for that
scenario. Once you have chosen a scenario, click the View Report button
![](media/image149.png){width="1.0in" height="0.20833333333333334in"}
(the button fill will be solid).

**Note** -- once you have selected a campaign on a scenario timeline
graph, you will only be able to select individual campaign reports from
that scenario card using the graph. To view a full scenario report, you
must reload the **Scenario Hub**.

### ![](media/image150.tiff){width="3.1682360017497815in" height="1.6421194225721785in"}Accessing Reports from the Battleground 

You can access any campaign's report from the Battleground by clicking
the Reports button on the **Battleground** ribbon and selecting **Open
Campaign Report**. You can also view a report for the entire scenario by
selecting **Open Scenario Report.** In either case, a new tab opens in
your browser displaying the report.

![](media/image151.tiff){width="1.3in" height="2.8399573490813648in"}Report Navigation
--------------------------------------------------------------------------------------

### Scenario Reports

Scenario Reports require that you specify start and end dates to view
summarized campaign data
![](media/image152.tiff){width="1.2090912073490814in"
height="0.2in"}using the calendar tool at the top of the **View Report**
screen.

You can scroll through the Scenario Report **Overview** to view the
constituent Campaign Reports.

You can use the menu at the left of the report window to navigate to the
type of Scenario Report information you want to view. See
**Understanding Reports** below for a fuller explanation of the
information in the report.

### ![](media/image153.tiff){width="1.3384612860892389in" height="3.2475896762904637in"}Campaign Reports 

You can use the menu at the left of the report window to navigate to the
type of Campaign Report information you want to view. See
**Understanding Reports** below for a fuller explanation of the
information in the report.

Note -- the Campaign Report navigation menu contains the additional
destination, **OS Summary**.

To download a Campaign Report as a PDF, click the **Export Report** pull
down menu at the top right of the screen and specify the report items
that you want to download. In addition, you can also download any
section of the report as a .CSV file for use with Excel or other
spreadsheet software by clicking the **Download** button
![](media/image154.png){width="0.21875in"
height="0.13541666666666666in"} at the far right, just below the **View
Battleground** button.

Understanding Reports
---------------------

Both Scenario Reports and Campaign Reports consist of the following
sections:

+------------------------------+-----------------------------+
| -   Critical Assets Findings | -   All Devices             |
|                              |                             |
| -   Critical Assets          | -   Breach Points           |
|                              |                             |
| -   All Findings             | -   Scenario Configurations |
+------------------------------+-----------------------------+

Campaign Reports have an additional section, OS Summary

The primary difference between Scenario and Campaign Reports is that
while Scenario Reports summarize the data from all associated campaigns,
Campaign Reports focus exclusively on a single campaign.

### Overview

The Campaign Report **Overview** section displays the date, time, and
duration of the campaign and provides a graphic overview of the number
and percentage of compromised and reconned network devices and assets.

Note that in the following report extracts, the **Scenario** is named
"VPN Network / Remote Employees" and the **Campaign** is 000007.

![A screenshot of a cell phone Description automatically
generated](media/image155.tiff){width="6.268055555555556in"
height="3.4583333333333335in"}

*Campaign Report Overview Section*

### Critical Asset Findings

The **Critical** **Asset Findings** section highlights which assets were
compromised in the campaign(s) and allows you to explore the particulars
of each finding by clicking on the **View Technical Details** link.

![A screenshot of a cell phone Description automatically
generated](media/image156.tiff){width="6.268055555555556in"
height="3.301496062992126in"}

*The Critical Asset Findings display*

### Critical Assets

The **Critical Assets** section lists assets involved in the scenario or
campaign.

![A screenshot of a cell phone Description automatically
generated](media/image157.tiff){width="6.268055555555556in"
height="2.4168799212598424in"}

*The Critical Assets display*

For large asset inventories, you can Search through the listed assets.
You can also hide the various columns in this report using the Show/Hide
pull-down and selecting which columns to hide.

### Asset / Entity Deep Dive

You can deep dive for additional asset and related entity information
and learn about methods used to compromise that asset, by clicking on
the asset names in a Campaign Report. Those links will bring you to the
device and entity report screen and will show:

-   Compromising Methods

-   Critical Assets at Risk

-   Affected Entities

-   Outbound Attack Paths

-   Hardening for that specific device

![](media/image158.tiff){width="6.268055555555556in"
height="2.027083333333333in"}

![](media/image159.png){width="6.268055555555556in"
height="1.2527777777777778in"}Asset / Entity Reporting Display

![](media/image161.png){width="6.268055555555556in"
height="1.6777777777777778in"}

Additional Asset /Entity Report display

![](media/image162.png){width="6.268055555555556in"
height="1.2965277777777777in"}

Hardening suggestions

### All Findings

The **All** **Findings** section of a Campaign Report lists the types of
attacks that succeeded in compromising devices, the number of such
devices, and the percentage of all compromised devices they represent.

![A screenshot of a cell phone Description automatically
generated](media/image163.tiff){width="6.2in"
height="3.2784186351706035in"}

*All Findings Display*

For each attack, you can click the **View Technical Details** link to
display additional information, attack methods, and remediation advice.

![A screenshot of a cell phone Description automatically
generated](media/image164.tiff){width="6.201496062992126in"
height="3.434346019247594in"}

*View Technical Details display*

Under **Affected Devices**, the first 40 affected devices are displayed
by default; clicking **Show More**, displays a window with a scrollable
list of all devices compromised by the attack. Clicking a device in the
list displays a window with detailed information on the attack,
including the time of the attack and the devices involved.

![A screenshot of a cell phone Description automatically
generated](media/image165.tiff){width="6.123349737532808in"
height="3.201496062992126in"}

*Affected Devices, Device Details display*

### All Devices

The **All Devices** section lists the devices participating in the
campaign and provides information on Status (compromised or reconned),
Method, OS, IP, Cluster, User, and Source Device. You can deep dive for
additional device information by clicking on the device names. For large
device inventories, you can **Search** through the listed assets. You
can also hide the various columns in this report using the **Show/Hide**
pull-down and selecting which columns to hide.

![A screenshot of a cell phone Description automatically
generated](media/image166.tiff){width="6.268055555555556in"
height="2.8091885389326334in"}

*Scenario Report All Devices Display*

### Breach Points

The **Breach Points** section of reports provides information on the
breach points configured in the scenario or campaign.

![A screenshot of a cell phone Description automatically
generated](media/image167.tiff){width="6.254166666666666in"
height="2.4141786964129484in"}

*Campaign Breach Points display*

Clicking on a breach point provides additional detail about the device
specified as a breach point.

### Scenario Configuration

The Scenario Configuration section of both Scenario and Campaign reports
provides comprehensive information on the selected scenario. See
**Getting Started** for more information on scenarios and scenario
configuration.

![A screenshot of a social media post Description automatically
generated](media/image168.tiff){width="6.268055555555556in"
height="3.370138888888889in"}

*Scenario Configuration Report*

Click the tabs at the top of the section to display specific
information, including Setting, Scope, Breach Points, Critical Assets
and Exclusions. Not every scenario will have configuration data for all
of these topics.

### OS Summary

The **OS Summary** section (of Campaign Reports only) provides a graphic
display showing a breakdown of the **Operating System** (Windows Server,
Windows Client, Linux, MacOS) of compromised, reconned, or undiscovered
devices. The percentage represented by each of these platforms is
indicated in the circle:

![A screenshot of a cell phone Description automatically
generated](media/image169.tiff){width="6.268055555555556in"
height="3.772222222222222in"}

OS Summary Display in a Campaign Report

### ![](media/image170.png){width="2.446558398950131in" height="2.942632327209099in"}Aggregated Report

On the righthand side of the **Scenario Hub** are controls for
generating an **Aggregated Report** for all scenarios across a specified
range of dates.

Within the Aggregated Report itself, you can select which campaign
scenarios to include in the report with the All Scenarios pull-down menu
(see figure below)

![A screenshot of a cell phone Description automatically
generated](media/image172.png){width="6.266774934383202in"
height="3.721738845144357in"}

*Selecting scenarios to include in an Aggregated Report*

Other Reporting Capabilities
----------------------------

Throughout the XM Cyber user interface, tabular data can be exported and
downloaded in CSV format (comma separated values) by clicking download
icons (![](media/image173.tiff){width="0.3043471128608924in"
height="0.16665354330708662in"}) above the tables in question.

SYSTEM CONFIG
=============

The **System Config** screen has six tabs, described in the following
table.

  ------------------ -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **Tab**            **Function**
  Health (default)   Displays CPU, Memory, and Disk Utilization for major parts of the XM system: Servers (Database, North, and South), and Sensors.
  Sensors            Enables management of sensors including enabling, disabling, updating, and other tasks.
  System Update      Displays the current XM Cyber version and provides an upload area for the latest system installation files.
  Users              Enables XM Cyber user management. The tab displays user attributes such as Username, Role, etc. and enables creation and deletion of users and credentials management. It also supports configuration of the LDAP server connector and of OpenID service.
  SIEM               Enables addition and management of one or more SIEMs (Security Information and Event Management) targets.
  General Settings   Allows specification of a range of configuration options: DNS and Certificates, SMTP servers, API keys, cloud accounts and Email Security Validation.
  ------------------ -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The following sections describe each of these tabs and their functions
in detail.

System Config Tabs and Links
----------------------------

The System Config pane allows users to monitor the state of the system
and set up and configure a range of functions. It also supports
downloading the Sensor Installer (see Sensors below) and the System Log
in CEF (Common Event Format). You may be asked to supply this file to XM
Cyber for support and debugging purposes.

### Health tab

The Health tab displays CPU, Memory, and Disk Utilization for each part
of the XM Cyber system components (Database, North, South, and Sensors).

![A screenshot of a social media post Description automatically
generated](media/image174.tiff){width="6.268055555555556in"
height="2.7284722222222224in"}

*System Config Health Tab*

A usage graph for each part of the system is displayed for both the
current time and for a time period that you specify by sliding the time
marker along the graph.

![](media/image175.png){width="6.2362204724409445in"
height="1.078740157480315in"}

*Using the Marker to Specify a Time on the Health Graph*

The **Health Tab** also includes display statistics for connected
sensors, campaigns and utilization of campaigns across scenarios.

The **Health Tab** ![](media/image177.png){width="1.77in"
height="2.59in"} also offers a pop-up menu for rebooting services and
restarting services, including assets and services hosted in the Cloud.

### Sensors tab

The Sensors tab enables you to manage sensors, including enabling and
disabling them, updating them, and other tasks, and looks like this:

![A screenshot of a cell phone Description automatically
generated](media/image178.tiff){width="6.268055555555556in"
height="2.8680555555555554in"}

*Sensors Tab*

![](media/image179.png){width="1.45in" height="3.6243055555555554in"}For
each sensor in the list, the following information is displayed: Status
(green for enabled, red for disabled), Sensor Name (the name of the
device on which the sensor is running), Sensor ID, Version,
Domain/Workgroup, IP, OS, Enabled (move the slider to enable/disable the
sensor).

![](media/image180.png){width="1.6604166666666667in"
height="2.0155194663167104in"}Clicking on the **Show/Hide** pull-down at
the far right of the column headings displays the following column
options:

For each sensor in the list, placing the cursor to the right of the
**Enabled** button displays a **Download** button to download the sensor
activity log, and a **More** button that provides two further options:
Reboot and Uninstall.

Clicking on the pull-down to the left of a sensor name displays
information on CPU, Memory, and Disk Usage of the device running the
sensor, including a usage graph for a specified time period. Use the
purple marker to display usage for a specified time:

![](media/image181.png){width="6.2362204724409445in"
height="1.3700787401574803in"}

*Information display for a device on which the sensor is located.*

Hovering over an item (CPU, Memory or Disk Usage) displays the graph for
that item:

![](media/image182.png){width="6.2362204724409445in"
height="1.1456692913385826in"}

*Display for the memory information of a device hosting a sensor.*

#### Updating Sensor Software

You can update the version of sensor software manually by clicking the
update button to the right of the sensor version column.

![A screenshot of a cell phone Description automatically
generated](media/image183.tiff){width="6.268055555555556in"
height="2.1444444444444444in"}

*Updating sensor software versions*

Sensors also have the ability to update to new versions automatically.
You can enable automatic update via the System Config **Sensors** tab as
follows.

1.  First, select one, multiple or all sensors using the checkbox(es) to
    the left of the Sensors pane. When you click any of the checkboxes,
    an options ribbon appears at the bottom of the Sensors pane.

2.  To enable auto-update, click on the pop-up next to **Auto Update**
    and select Enable

![](media/image184.tiff){width="6.268055555555556in"
height="1.1006944444444444in"}

*Sensor configuration options ribbon with Auto Update pop-up*

![](media/image186.tiff){width="3.92in" height="2.26in"}This screen also
lets you download sensor software installation packages (depending on
the host OS). When you click the Download Sensor Installer link at the
top right of the screen, the following dialog appears with the option of
downloading sensor software for Windows, Linux or MacOS.

Consult the *XM Cyber Sensor Installation Guide* and/or contact your
system administrator for assistance.

### System Update tab

The System Update tab displays the current version number and date of
the last update to the XM Cyber system as well as a listing of past
updates. It also contains an upload area to enable for new versions of
XM Cyber.

![A screenshot of a social media post Description automatically
generated](media/image187.tiff){width="6.267669510061243in"
height="3.8382852143482067in"}

*The System Update Tab*

### Users tab

The Users tab supports various types of user management and has three
sub-tabs: **Users**, **LDAP Connector** and **OpenID Config**.

#### Users sub-tab

The Users sub-tab displays the XM Cyber user information, including Full
Name, User Name, Realm Role (Admin, Security Analyst, Security
Architect, SOC or user), Mail, and Last Login, and supports basic user
administration.

![A screenshot of a cell phone Description automatically
generated](media/image188.tiff){width="6.268055555555556in"
height="2.3027777777777776in"}*\
Users tab*

#### Creating a New User

To create a new user, click the **Add User** button
![](media/image189.tiff){width="0.16304352580927384in"
height="0.16304352580927384in"} at the top of the tab and specify user
attributes in the boxes that appear at the top of the user listing.

![A screenshot of a cell phone Description automatically
generated](media/image190.tiff){width="6.268055555555556in"
height="1.1527777777777777in"}

*Add New User dialog*

![](media/image191.tiff){width="1.2465277777777777in"
height="1.8956517935258093in"}For each new user created, you must supply
their Full Name, a unique Username, an email address and a Role from the
Role Type pull-down.

You can assign users one of four **Role Types**, with accompanying XM
Cyber system privileges.

-   **Admin** - full access to all XM Cyber system elements and
    configuration options, including user management

-   **Security Analyst **-- read-only access to scenarios and campaigns,
    without access to system configuration

-   **Security Architect** -- read write on scenarios and campaigns,
    without access to system configuration

-   **SOC** -- read-only access to the health of XM Cyber servers and
    system

#### Editing User Attributes and Deleting Users

To delete a user or edit user attributes, click one of four buttons to
the right of the user row on the Users tab.

  ---------------------------------------------------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------
  ![](media/image192.png){width="0.8908989501312335in" height="0.6510422134733158in"}      Prompts to delete the indicated user
  ![](media/image194.png){width="0.9300273403324585in" height="0.5781255468066492in"}      Enables changing a user password
  ![](media/image195.png){width="0.9332589676290464in" height="0.5885422134733158in"}      Edit the user details such as realm, username, role, full name or email
  ![](media/image196.tiff){width="0.28845581802274717in" height="0.22608705161854767in"}   When you are editing user attributes, the Enable Local switch (normally grayed out) lets you enable/disable users without actually deleting them.
  ---------------------------------------------------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------

#### LDAP Connector sub-tab

You can manage XM Cyber users via LDAP (Lightweight Directory Access
Protocol) using the **LDAP Connector** tab.

![A screenshot of a cell phone Description automatically
generated](media/image197.tiff){width="6.268055555555556in"
height="3.2666666666666666in"}

LDAP Connector tab

The **LDAP connector** tab has the following fields, buttons and
switches.

![](media/image198.tiff){width="1.0695647419072616in"
height="0.2362992125984252in"} -- the **Use LDAP Connector** switch
determines whether to use the connector and is Disabled by default.

**Domain** and **URL** -- these fields are required to establish a
connection to an LDAP server

**Username** and **Password** -- credentials required to access the LDAP
server. Note that the Username must be entered in either UPN (User
Principal Name) or DN (Distinguished Name) format. See the [XM Cyber
Glossary](#xm-cyber-terminology-glossary) for additional information.

**Base DN** -- the Base DN (Distinguished Name) is point in the LDAP
directory tree where the server starts searches for usernames. You can
test the validity of the Base DN with the accompanying Test button
![](media/image199.tiff){width="0.6253619860017497in"
height="0.20845363079615048in"}.

![](media/image200.tiff){width="0.8040758967629046in"
height="0.15652230971128608in"} - the **Add Group** button allows you to
add existing LDAP groups to the XM Cyber user set. You will need to know
the name of the group and will be permitted to assign one XM Cyber role
to all members of that group.

![](media/image201.tiff){width="3.168086176727909in"
height="2.0295898950131233in"}**Secure LDAP box** -- if you are using
Secure LDAP, this box lets you drag-and-drop or select certificate files
for upload containing a PEM CA (Privacy Enhanced Email Certificate of
Authority).

Once you have edited the LDAP Connector settings, click **Apply
Changes** to update or **Cancel** to revert.

#### OpenID Config sub-tab

![](media/image202.tiff){width="2.9972222222222222in"
height="2.8381944444444445in"}XM Cyber allows you to use the OpenID
protocol for login authentication. Disabled by default, the
Enable/Disable switch lets you enable the protocol and select an OpenID
/ SSO provider.

Most users will select a provider from the list -- Google, Okta or
AzureAD -- which bring up the following authentication and configuration
fields associated with that provider. These fields include

**Client ID** and **Client Secret** -- authentication strings for the
OpenID provider

**Default Role** -- one of the four XM Cyber roles defined in the
**Users sub-tab** above.

**Issuer URL** -- the API URL associated with the OpenID provider. XM
Cyber automatically provides a default value for this field.

![A screenshot of a cell phone Description automatically
generated](media/image203.tiff){width="6.268055555555556in"
height="2.095138888888889in"}\
OpenID Config fields for AzureAD

Selecting a **Custom** provider brings up further fields as show below.
Contact your OpenID administrator for the appropriate values to enter in
those fields.

![A screenshot of a cell phone Description automatically
generated](media/image204.tiff){width="6.268055555555556in"
height="3.254166666666667in"}

Custom OpenID provider fields

Once you have edited the OpenID Config settings, click **Apply Changes**
to update or **Cancel** to revert.

Remember to set <https://demong.xmcyber.com/api/openId/loginSuccess> as
an allowed callback when configuring your OpenID provider account.

### SIEM tab

XM Cyber supports logging security events to one or more SIEM (Security
Information and Event Management) servers and/or local files. The SIEM
tab lets you specify the address of each and attributes of logging using
the Add Server button
![](media/image205.tiff){width="0.8347823709536308in"
height="0.1855074365704287in"}.

![A screenshot of a cell phone Description automatically
generated](media/image206.tiff){width="6.268055555555556in"
height="5.6375in"}\
Logging Server dialog

The New Logging Server dialog includes a number of fields, buttons and
swtiches.

**SIEM Target Name** -- this field allows you to specify a display name
for the SIEM logging target, by default, a file on the system hosting XM
Cyber. Using the Format pull-down, you can specify whether events are
logged as plaintext or in CEF (Common Event Format).

The **Enabled** switch allows you to disable and re-enable logging to a
given target.

![](media/image207.tiff){width="1.0260870516185476in"
height="0.13268372703412074in"} - the Remote server radio button lets
you set up a remote SIEM server and requires that you supply a server
address (as an FQDN), protocol (currently UDP only) and port number
(default = 514).

**Event Settings** -- this area includes checkboxes and pull-downs for
logging major event types -- Scenarios, Campaigns, System Updates,
System Health and Sensors. Each pull-down includes checkboxes for
sub-types, e.g., under Scenarios, there are checkboxes for Scenario
Created, Scenario Deactivated, etc. Top-level checkboxes select all
sub-types automatically, and you can select and delect sub-types using
the individual pull-downs.

![A screenshot of a cell phone Description automatically
generated](media/image208.tiff){width="6.268055555555556in"
height="3.0597222222222222in"}\
Event Settings pull-down

Once you have edited the **Logging Server** settings, click **Add New**
or click the X at the top of the dialog to cancel.

#### ![](media/image209.tiff){width="2.073611111111111in" height="1.1965277777777779in"}Editing and Deleting Existing SIEM Servers. 

You can disable/enable, test, modify or update SIEM server using the
switch and buttons on the right-hand part of pane.

![](media/image210.tiff){width="0.3433573928258968in"
height="0.19261482939632546in"}**Enable** -- this switch lets you
disable/enable logging to a listed SIEM target

![](media/image211.tiff){width="0.34516951006124236in"
height="0.199834864391951in"} **Test** -- this button sends a test event
to a logging file or server.

![](media/image212.tiff){width="0.12002734033245845in"
height="0.14607502187226595in"} **Trashcan** -- lets you delete a listed
SIEM target

![](media/image213.tiff){width="0.12445647419072615in"
height="0.16441929133858268in"} Pen -- open a dialog comparable to the
above New Logging Server dialog (above) to allow modification of SIEM
target logging attributes.

### General Settings tab

The General Settings tab has four sub-tabs with the following functions:

  DNS and Certificates   Specifies the IP address / URL of the server hosting the XM Cyber application, keys and certificates to secure access to it.
  ---------------------- ------------------------------------------------------------------------------------------------------------------------------
  SMTP Server            Email notifications from XM Cyber require specification of an SMTP (Simple Mail Transfer Protocol) server.
  API Keys               Specifies API keys to use when accessing reports and other data outside of the XM Cyber application.
  AWS Accounts           Configuration page to connect XM Cyber to AWS Accounts for attack simulations.

#### DNS and Certificates

This pane lets you specify the IP address or DNS URL of the server
hosting the XM Cyber application, keys and certificates to secure access
to it. The pane has the following fields and functions

**Server IP / FQDN** -- enables specification of the XM Cyber server
address either by IP address or using an FQDN (Fully Qualified Domain
Name).

**Certificate Information** -- while XM Cyber manages certificates for
hosting of XM Cyber in the Cloud, on-premises users can upload keys and
other certificate information here.

![A screenshot of a cell phone Description automatically
generated](media/image214.tiff){width="6.268055555555556in"
height="2.8368055555555554in"}

*Default General Settings tab*

#### SMTP Server

![](media/image215.tiff){width="1.8083333333333333in"
height="1.386111111111111in"}Email notifications from XM Cyber require
specification of an SMTP (Simple Mail Transfer Protocol) server, in
particular for password reset requests. The fields, buttons and menus of
interest in this pane are

**Type** -- allows you to specify whether the server requires
authentication via simple login or with SMTP Oauth2.

**Server IP / FQDN** and **Port** -- the address or URL of the SMTP
server and port number, obtained from your service provider or from the
configuration settings of your local email client.

![](media/image216.tiff){width="1.0608694225721784in"
height="0.18112423447069118in"} -- this checkbox indicates whether the
server requires secure SMTP.

**Username** and **Password** -- the login credentials for your SMTP
server.

**Username**, **Refresh Token**, **Client ID** and **Client Secret** --
these items apply only to OAuth2 configurations to support limited
authorization access for sending emails. Contact your system
administrator for appropriate values.

**Send Test Email** -- this button allows you to test login or Oauth2
configurations. It will use the supplied email address (Username) to
access the SMTP server. Check your email after using this test function.

**Certificate Upload** -- the box in the upper right-hand part of the
pane offers you the option of dragging/dropping or uploading a file
containing an email server certificate (if required).

**Apply Changes** -- click this button to commit any changes made to the
SMTP Server configuration fields or click **Cancel** to exit without
saving changes.

![A screenshot of a social media post Description automatically
generated](media/image217.tiff){width="6.099154636920385in"
height="3.2414851268591427in"}

SMTP Server Settings pane

#### API Keys

This pane lets you specifiy API keys to use when accessing XM Cyber
reports and other data from outside of the XM Cyber application. XM
Cyber APIs let users generate their own reports and extensions to XM
Cyber analysis.

![](media/image218.tiff){width="3.374336176727909in"
height="2.107306430446194in"}These keys are typically appended to the
URL used to invoke the web APIs in question. The fields, buttons and
menues in this pane include

![](media/image219.tiff){width="1.2521741032370954in"
height="0.22318897637795276in"}\-- the **Add API Key** button lets you
add new API keys to the set maintained by XM Cyber. Pressing this button
brings up the **Create API Key** dialog. With successful API Key
creation, a new entry will appear in the list shown in the pane.­

**Name, Key Prefix, Role**, etc. -- fields reflecting the attributes of
previously entered API keys. You can enable/disable the keys using the
switch ![](media/image210.tiff){width="0.3433573928258968in"
height="0.19261482939632546in"}at the right of the row and delete keys
with the dimmed trash icon
![](media/image220.tiff){width="0.1853707349081365in"
height="0.1998786089238845in"} at the far right.

![](media/image221.tiff){width="0.8260870516185477in"
height="0.1937729658792651in"} -- The **Show/Hide** pull-down lets you
display or hide the various columns in the API Key listing.

![A screenshot of a cell phone Description automatically
generated](media/image222.tiff){width="6.268055555555556in"
height="1.8138888888888889in"}

API Keys configuration pane

#### AWS Accounts

XM Cyber supports inclusion of assets and entities hosted on user
private and public clouds. This page lets you configure the accounts and
credentials needed to connect XM Cyber to AWS Accounts to facilitate
attack simulations.

The fields, buttons, switches and menus on this pane include

![](media/image223.tiff){width="0.921738845144357in"
height="0.23896981627296587in"} \-- the **Disabled/Enabled** switch is
enabled by default and should only be disabled for configurations not
utilizing AWS (Amazon Web Services).

![](media/image224.tiff){width="1.3130435258092739in"
height="0.16219925634295712in"}- the **Use default credentials** switch
is ON by default to support cloud users. When XM Cyber creates a
customer cloud instance, an associated ARN (Amazon Resource Name) is
created, and that ARN is then used with **Add Account** (see below).

![](media/image225.tiff){width="1.0256944444444445in"
height="0.22110673665791777in"} -- the **Create AWS User** button opens
a new browser tab or window to login to your AWS account and create a
new User. This step is not required for cloud configurations using
credentials. Consult Amazon Web Services documentation for additional
details.

![A screenshot of a social media post Description automatically
generated](media/image226.tiff){width="6.268055555555556in"
height="4.909027777777778in"}

AWS Accounts configuration pane

**Access Key** **ID** and **Secret Access Key** -- these fields allow
you to specify authentication credentials needed to access AWS APIs.
Contact your cloud administrator or AWS support to obtain these
credentials.

![](media/image227.tiff){width="0.7043482064741907in"
height="0.22843722659667542in"} -- the **Test User** button tests the
supplied AWS credentials and reports on success or failure. If
unsuccessful, recheck your input of the credentials for typos.

![](media/image228.tiff){width="1.0256944444444445in"
height="0.21849081364829395in"} -- the **Add Account** button opens a
new browser tab or window and takes you to the AWS add account page.
Upon returning to the XM Cyber screen, you will be prompted for an ARN
(Amazon Resource Name) for the created role. Consult Amazon Web Services
documentation for additional details.

**Accounts** -- this listing summarizes all available AWS accounts and
the fields specified in the **Show/Hide** pull-down. You can click the
trashcan icon ![](media/image220.tiff){width="0.1853707349081365in"
height="0.1998786089238845in"} to remove accounts and the pen icon
![](media/image229.tiff){width="0.18128062117235347in"
height="0.20990376202974628in"} to edit account entries.

![](media/image230.tiff){width="0.7041666666666667in"
height="0.2304549431321085in"} -- the **Test Roles** button uses the
Accounts information to test specified roles. If unsuccessful, recheck
your input of the account info for typos and/or the roles actually
associated with the AWS account.

XM Cyber Terminology -- Glossary
================================

The following are important terms that should be understood when
conducting a campaign.

### APT Attack {#apt-attack .Glossary-Heading}

An advanced persistent threat (APT) is an attack on the network that is
undetected for a long period of time thereby enabling the attacker to
exfiltrate data.

### Asset {#asset .Glossary-Heading}

An entity in the tested network that has possible value to an attacker
or the organization (which makes it a point of interest to an attacker).
An asset can be one of the following:

-   Device －endpoint in the network

-   Data － file types found on any of the endpoints

-   Network － a network-related entity, like a certain segment or
    subnet, etc.

-   Cloud -- there are multiple cloud entity types, such as S3, Lambda,
    roles, etc.

### Blue Team {#blue-team .Glossary-Heading}

A dedicated internal security team that defends against attackers. If
such a team does not exist in an organization, it may be specially set
up in order to conduct a red team simulation.

### Breach Point {#breach-point .Glossary-Heading}

Every campaign starts at a compromised endpoint called a breach point. A
breach point may be an endpoint with a high probability to get infected,
as the initial foothold of an attack. In XM Cyber you define breach
points when setting up a scenario.

### Campaign {#campaign .Glossary-Heading}

An attack scenario executed by the virtual hacker. It contains the
loaded APT capabilities (*methods*) and the current state of all sensors
in the network -- compromised, discovered, undiscovered or disabled.
Every campaign runs with its configuration defined in its parent
scenario.

### Compromised Endpoint {#compromised-endpoint .Glossary-Heading}

An endpoint on which an attacker could potentially execute arbitrary
code remotely.

### CVE {#cve .Glossary-Heading}

Common Vulnerabilities and Exposures and/ Common Vulnerability
Enumeration -- the identification number and accompanying description
(including public references) for known vulnerabilities as catalogued by
[NIST](https://www.nist.gov/) in the [National Vulnerability
Database](https://nvd.nist.gov/).

### Data Yield {#data-yield .Glossary-Heading}

The amount of data in gigabytes potentially exfiltrated by an attacker
as a result of a campaign. The measurement is based on files that the
system has marked as important. Files that comprise the calculated data
yield include databases, MS Office files, source code (e.g., Swift
files), CAD files and other types.

### Discovered/Undiscovered Endpoint {#discoveredundiscovered-endpoint .Glossary-Heading}

A discovered endpoint is an endpoint that a hacker has discovered, but
not yet succeeded in compromising. A discovered endpoint is vulnerable
as a hacker can then try various methods to gain access to the endpoint.
An undiscovered endpoint is an endpoint in the organization that remains
unknown to a hacker.

### DN -- Distinguished Name {#dn-distinguished-name .Glossary-Heading}

A distinguished name (usually just shortened to "DN") uniquely
identifies an entry and describes its position in the LDAP Directory
Information Table (DIT). DNs are comprised of comma-separated components
called relative distinguished names, or RDNs. For example, the DN
"uid=john.doe,ou=People,dc=example,dc=com" has four RDNs.

### FQDN -- Fully Qualified Domain Name {#fqdn-fully-qualified-domain-name .Glossary-Heading}

A complete domain name for a specific computer, or host, on the
internet. An **FQDN** consists of two parts: a hostname and a domain
name, e.g., an **FQDN** for a mail server might be
*corpmail.somecompany.com*, where *corpmail* is the host and
*somecompany.com* is the domain.

### Method {#method .Glossary-Heading}

This refers to one or more techniques used to compromise a computer
system.

### Network Superiority {#network-superiority .Glossary-Heading}

Compromising more than 80% of the network is considered achieving
superiority over the network.

### Organizational Unit {#organizational-unit .Glossary-Heading}

A container within a Microsoft Active Directory domain which can hold
users, groups, computers and other Organizational Units (OUs). An OU is
the smallest unit to which an administrator can assign Group Policy
settings or account permissions.

### Purple Team {#purple-team .Glossary-Heading}

Enhances the effectiveness of campaigns conducted by red and blue teams
by coordinating the campaigns and analyzing vulnerabilities found by the
red team together with the defensive strategies and tactics of the blue
team.

### Recon {#recon .Glossary-Heading}

Refers to a key step in attacking a computer system: gathering
information on potential victims. In XM Cyber, recon refers to
discovering a victim which is the first step in conducting a successful
hack.

### Red Team {#red-team .Glossary-Heading}

A team of cybersecurity analysts, IT and communication professionals,
hackers, and others that conducts a comprehensive simulated campaign
that tests how well an organization's personnel, network, and physical
security withstand a real attack.

### Rule {#rule .Glossary-Heading}

Rules are \"If X then Y\" assertions that provide guidance on how to act
when those assertions are true. In XM Cyber rules determine which
entities participate in scenarios, from which Breach Points attacks
emanate, which assets are targeted, and which methods, pathnames, or
credentials are excluded.

### Scenario {#scenario .Glossary-Heading}

A set of rules created by a XM Cyber user running a campaign. The rules
determine such things as the scope of campaigns, breach points, the type
of devices to be included, as well as campaign frequency and duration.
XM Cyber assists users in creating scenarios.

### Target {#target .Glossary-Heading}

In XM Cyber this refers to a device that is attacked during a campaign.
The device may represent an asset, or simply be part of a computer
network.

### UPN -- User Principal Name {#upn-user-principal-name .Glossary-Heading}

In Windows Active Directory, a User Principal Name (UPN) is the name of
a system user in an email address format. A UPN (for example:
john.doe\@domain.com) consists of the username (logon name), separator
(the @ symbol), and domain name (UPN suffix). A UPNis not the same as an
email address.

User Manual and UI Conventions
==============================

This XM Cyber User manual and the User Interface it describes employ
certain typographic and design conventions.

-   **Bold Type** -- Bold type in-line (not in section headers) refers
    to on-screen elements.

-   **Purple UI Elements** -- UI elements (text, buttons and switches)
    are colored purple when they are enabled and available for use.

-   **Gray UI Elements** -- UI elements (buttons, icons and switches)
    are grayed out either when disabled (buttons and switches) or when
    their use is restricted to certain roles (e.g., delete and edit
    icons).

-   **Red Text** -- XM Cyber issues warning text in red type, e.g., when
    elements are missing from fields in an input dialog.

[^1]: Chrome and Firefox are recommended browsers
