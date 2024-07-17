# viewbridgefiles
# A guide to view .bridge files using SQuirreL SQL  
Source: 
This guide is based on the following instructions:  
https://db.apache.org/derby/integrate/SQuirreL_Derby.html  

# Setup  
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

# 5. Add and inspect .bridge files  
First we need to find the directory SQuirreL SQL stores the files. For me it is:  
```
~/.squirrel-sql/plugins/derby 
```
~/.squirrel-sql/plugins/derby 
I found out this was the directory by creating an alias with a wierd name and then searching for it on my system.  
<br/>
After establishing the used directory you can start extracting and placing the files. When extracting .bridge file a folder called "database" is found within, these are the files we need.  
The resulting file structure for me is the following:  
```
~/.squirrel-sql/plugins/derby/{{bridge-file-name}} 
```
The contents of the directory is the following:  
![Directory structure](https://github.com/youphendriks/viewbridgefiles/blob/main/images/5directoryStructure.png)     
<br/>
Now that the files are in the correct place, you can add the bridge file to SQuirreL SQL.  
In the Alias tab you click the "+" to add an alias.  
![Add alias](https://github.com/youphendriks/viewbridgefiles/blob/main/images/6addAlias.png)  
Now you can give the alias a name. For driver you select "Apache Derby embedded" from the dropdown menu.  
The URL is as follows:
```
jdbc:derby:{{bridge-file-name}};
```
Replace {{bridge-file-name}} with the name you used for the directory before, and don't forget to add ";" at the end!  
![Add alias](https://github.com/youphendriks/viewbridgefiles/blob/main/images/7addAlias.png)  
You can now test the connection, if it succeeds you can click "connect" to add the alias.  
![Test connection](https://github.com/youphendriks/viewbridgefiles/blob/main/images/8testConnection.png)  

# 6. Viewing the bridge file
Finding the information you need is dependant on your .bridge file, but it is important to know you should click the "content" tab to view the contents of the .bridge file.
![Content tab](https://github.com/youphendriks/viewbridgefiles/blob/main/images/9contentTab.png)  
<br/>
I hope this guide helped! If you run into any problems let me know in person or create an issue on this github page.  

