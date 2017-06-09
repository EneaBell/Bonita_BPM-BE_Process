# Bonita_BPM-BE_Process
EPFL Spring 2017 Semester Project in the LAMS lab. Developed the ESOA BE's Process in Bonita BPM.  
![BE_Process](https://github.com/EneaBell/Bonita_BPM-BE_Process/blob/master/ESOA_BE-1.0.png)  
## Development specification
The application has been developed on Bonita BPM v. 7.4.3, Window 64 bits.  
Known issue : Linux v. 7.4.3 had authentication failure on the REST connector.  

## Installation
You must have 
Download Bonita BPM Community v. 7.4.3 for window 64 bits [here](http://www.bonitasoft.com/products/download/bonita-bpm-windows-7-4-3-64bit?skip=true). Project is confirmed working on this version.
Other versions are available [here](http://www.bonitasoft.com/downloads-v2#!). Other setups are described in the [documentation](http://documentation.bonitasoft.com/?page=_installation).

Run the executable to install Bonita BPM on your machine.

## Import project
The project can be imported in Bonita BPM by importing the .bos. This is done by clicking in the tab first tab *Diagram -> Import …*.  
![import_screenshot](https://github.com/EneaBell/Bonita_BPM-BE_Process/blob/master/img/import_1.PNG)  
In the import wizard, select *Bonita 6.x and 7.x* and the [.bos file](https://github.com/EneaBell/Bonita_BPM-BE_Process/blob/master/ESOA_BE-1.0.bos) from the repository.
 
### Publish ESOA organization on the server 
The users login in the organization are: 
•	be
•	acd
•	blg
With password *ESOA*.  
The organization was imported in the previous step, but we need to publish it on the server. Click on *Organization->Publish...*.  
![Publish_screenshot](https://github.com/EneaBell/Bonita_BPM-BE_Process/blob/master/img/import_org_publish.PNG)  
Then select ESOA and enter the username of the default user, *be* in this example.  
![Select_ESOA](https://github.com/EneaBell/Bonita_BPM-BE_Process/blob/master/img/ESOA_select.PNG)  

## Run Process
If you are in the Bonita BPM IDE, you can deploy and run the process by clicking on the Run button in the toolbar. It will deploy the process, log you in and start the process.  
Otherwise, you can run the process directly from the server portal.
### From the server
Log in the portal and change to the administrator view on the top right. Go in *BPM ->  Processes* and click on + Install button. Select > the [.bar file](https://github.com/EneaBell/Bonita_BPM-BE_Process/blob/master/BE_StoryFlow--1.0.bar) from the repository.  
To start manually the process, change the view to *User* on the top right. Go on the *Processes* tab and click on the *START* button.  
![manual process start](https://github.com/EneaBell/Bonita_BPM-BE_Process/blob/master/img/start_proc_manually.PNG)  

## Run-through process.
We'll showcase the process execution step by step after starting the process using one of two above method.

Click Submit on the initialization form to start the process.  
![Initialization process](https://github.com/EneaBell/Bonita_BPM-BE_Process/blob/master/img/Run-through_1.PNG)  
You should be log in as Jane No, BE user. By going in the Tasks tab, you have a form on the right side where you have to enter the parameters for the diagnostic. Enter a Garage ID, for example : G_001. Then enter the Engine serial number, can be anything but the presence of a *d* will return a diagnostic of a defective engine. In our case, we enter abcd for defective engine. Click submit to go to the next step.
![Diagnostic of engine](https://github.com/EneaBell/Bonita_BPM-BE_Process/blob/master/img/Run-through_2.PNG)  
Click on the refresh button after each step to see pending task (we have to wait for the web request).
You'll see a read-only form that show the result. Submit to continue the process execution.  
![Diagnostic Review](https://github.com/EneaBell/Bonita_BPM-BE_Process/blob/master/img/Run-through_3.PNG)  
The following tasks are automatic, you are given read-only form to review the retreived result from the web services. Submit the form to continue the process execution  
![Garage details review](https://github.com/EneaBell/Bonita_BPM-BE_Process/blob/master/img/Run-through_4.PNG)  
![Order replacement part review](https://github.com/EneaBell/Bonita_BPM-BE_Process/blob/master/img/Run-through_5.PNG)  
After reviewing the order part, we change user to continue the process. Log out, then log in with the user *acd*.
In the following task, ACD confirm the reservation date of the technician  
![ACD confirmation](https://github.com/EneaBell/Bonita_BPM-BE_Process/blob/master/img/Run-through_6.PNG)  
Log back in with the user *be* to see the confirmation and in the following screen, notify BLG.  
![Tech booking confirmation](https://github.com/EneaBell/Bonita_BPM-BE_Process/blob/master/img/Run-through_7.PNG)  
![Notify BLG](https://github.com/EneaBell/Bonita_BPM-BE_Process/blob/master/img/Run-through_8.PNG)  
Finally, log in as *blg* to receive the notification. Then the process is over.  
![BLG receive notification](https://github.com/EneaBell/Bonita_BPM-BE_Process/blob/master/img/Run-through_9.PNG)
