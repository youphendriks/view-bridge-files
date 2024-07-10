# viewbridgefiles
# A guide to view .bridge files using SQuirreL SQL  
Source: 
This guide is based on the following instructions:  
https://db.apache.org/derby/integrate/SQuirreL_Derby.html  
  
## 1. Do you have java?  
You need to have java installed on your system.  
Check if you have java installed by typing the following command in your terminal:  
```
java -version  
```
If you don't have java installed you can follow the instructions to install [Java](https://www.geeksforgeeks.org/how-to-download-and-install-java-for-64-bit-machine/) or [OpenJDK](https://openjdk.org/install/).  
  
## 2. Download and install SQuirreL SQL  
Follow the [instructions](https://squirrel-sql.sourceforge.io/index.php?page=home#installation) found on the homepage.  
During the installation you can pick "plugins", make sure to select the "Apache Derby embedded" checkbox.  
  
## 3. Download the .jar file from this github  
Download and extract the .zip file from this github, or clone it by using the following command:  
```
git clone https://github.com/youphendriks/viewbridgefiles.git 
```  

## 4. Set the driver in SQuirreL SQL  
Launch SQuirrel SQL and click "Drivers" on the far left.  
![click "Drivers"](https://github.com/youphendriks/viewbridgefiles/blob/main/images/1drivers.png)  
Find "Apache Derby embedded" in the list, right-click on it and click "Modify Driver...".  
![click "Modify Driver..."](https://github.com/youphendriks/viewbridgefiles/blob/main/images/2modifyDrivers.png)  
Click "Add" on the pop-up window and navigate to the location of the .jar file you've downloaded in step 3.  
Once added you can click "List Drivers", the bottom field, called "Class Name", should now be filled with text.  
Select "org.apache.derby.jdbc.EmbeddedDriver" from the dropdown menu. Then click "Ok".  
![select "Class Name"](https://github.com/youphendriks/viewbridgefiles/blob/main/images/3className.png)  
If everything went correct the "Apache Derby embedded" driver should have a checkmark in front of it.  
![Checkmark](https://github.com/youphendriks/viewbridgefiles/blob/main/images/4checkmark.png)  
You are now all set up to start adding and inspecting .bridge files!  

## 5. Adding a .bridge file 





