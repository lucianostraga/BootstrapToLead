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

Here you will import the necessary resources to make this page ready for Bootstrap. Bootstrap requires jQuery and other .js and css files to work.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; In the code edit, paste the following code:

	<apex:page sidebar="false" standardStylesheets="false" showHeader="false" docType="html-5.0">
	
	    <apex:includeScript value="//ajax.googleapis.com/ajax/libs/jquery/1.11.2/jquery.min.js"/>
	    <apex:includeScript value="//maxcdn.bootstrapcdn.com/bootstrap/3.3.4/js/bootstrap.min.js"/>
	    <apex:stylesheet value="//maxcdn.bootstrapcdn.com/bootstrap/3.3.4/css/bootstrap.min.css"/>
	    <apex:stylesheet value="//maxcdn.bootstrapcdn.com/bootstrap/3.3.4/css/bootstrap-theme.min.css"/>
	    
	</apex:page>    
	
IMPORTANT: For better performance and to avoid styling issues, import the resources as static resources and create custom namespaces like:
	
	<div class="bootstap">
		Your page content here...
	</div>

**3 - Add the Custom Page Content**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Add the following code below to the page:

	<div class="container">
        
	        <div class="page-header">
	          <h1>Lead Creator <small>with Bootstrap and RemoteObjects!!</small></h1>
	        </div>
        
	        <form>
	            
		          <div class="form-group">
		            <label for="exampleInputEmail1">First Name</label>
		              <input type="text" class="form-control" id="firstName" placeholder="First Name"/>
		          </div>
		            
		          <div class="form-group">
		            <label for="exampleInputEmail1">Last Name</label>
		              <input type="text" class="form-control" id="lastName" placeholder="Last Name"/>
		          </div>
		            
		          <div class="form-group">
		            <label for="exampleInputEmail1">Company</label>
		              <input type="text" class="form-control" id="company" placeholder="Company"/>
		          </div>  
		            
		          <button type="button" onClick="createLead();" class="btn btn-primary">Submit</button>
	        </form>
        
	        <br/>
	        <div id="result"></div>	
	</div>
	
This is basically an HTML form, that uses the Bootstrap CSS classes.

**3 - Use Remote Objects for data creation**

Finally, we will add the javascript logic to perform some data creation.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Append the following code below:

	<apex:remoteObjects >
        	<apex:remoteObjectModel name="Lead" fields="FirstName,LastName,Company"/>
    	</apex:remoteObjects>
    
	<script>
    	function createLead(){
            var newLead = new SObjectModel.Lead();
            
            newLead.set('FirstName', document.getElementById("firstName").value );
    		newLead.set('LastName', document.getElementById("lastName").value );
            newLead.set('Company',document.getElementById("company").value );

            newLead.create(function(err,result,event) {
                if(err) {
                    document.getElementById("result").innerHTML = '<div class="alert alert-danger" role="alert">'+
                        						'<strong>Error! </strong>'+
                        							err.message+
                    							'</div>';
                		}
                else {
                    document.getElementById("result").innerHTML = '<div class="alert alert-success" role="alert">'+
                						'<strong>Success! </strong> Lead Created with ID: '+
                        					newLead.get('Id')+
                    						'</div>'; 
                		}
        		});
            
        	}    	
    	</script>
