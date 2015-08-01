# BootstrapToLead Quick Start Tutorial 

&nbsp;

## Intro 

Fascinated by the new modern websites? Have you wondered how to built a super cool Visualfoce page that looks great and surprises everyone?. Just in ten minutes, you'll learn how to take advantage of the easy and rich Bootstrap web framework to build increible VF pages. Not only this. You'll get an incredibly tiny custom app,that will help you to create Leads by using Remote Objects and without any Apex line of code. 

## Learning Objectives

After completing this module you will be able to:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - Create and set a Visualforce page for Bootstrap web Framework

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - Use Remote Objects for new data creation

&nbsp;

## Steps

**1 - Create a new Visualforce Page**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; From Setup, **Develop** | **Pages**, then click on **New** button.

**2 - Prepare the page for Bootstap support**

Here you will import the necessary resources to make this page Bootstrap ready.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; In the code edit, paste the folling code:

	<apex:page sidebar="false" standardStylesheets="false" showHeader="false" docType="html-5.0">
	    <apex:includeScript value="//ajax.googleapis.com/ajax/libs/jquery/1.11.2/jquery.min.js"/>
	    <apex:includeScript value="//maxcdn.bootstrapcdn.com/bootstrap/3.3.4/js/bootstrap.min.js"/>
	    <apex:stylesheet value="//maxcdn.bootstrapcdn.com/bootstrap/3.3.4/css/bootstrap.min.css"/>
	    <apex:stylesheet value="//maxcdn.bootstrapcdn.com/bootstrap/3.3.4/css/bootstrap-theme.min.css"/>
	</apex:page>    

3.&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Copy following code in Visualforce editor window
	

		
		<apex:page title="Trailhead QuickStart" standardcontroller="Account" showheader="false">

		<h1> Hello World, Hello Dreamforce! </h1>

		</apex:page>
		
