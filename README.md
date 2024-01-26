# Docker Compose - Python Alpine, Mongo DB, and MySQL DB Setup Instructions
### Pre-Requisites: Ensure you have Visual Studio Code (VSC) and Docker installed with Windows Subsystem for Linux (WSL2).

This guide will assist you in setting up a development container that runs Docker and includes a well-defined tool/runtime stack. The container comprises Jupyter Notebook, MongoDB, and MySQL databases on a minimal-notebook, along with Visual Studio Code (VSC) plugins customised to suit our requirements.

After completion of this setup, it allows you to open or clone code in a local or cloud-hosted Dev Container and take advantage of VS Code's full development feature set.

We are going to use Alpine Linux for our container, read more at: Minimal Notebook Container Documentation](https://hub.docker.com/r/jupyter/minimal-notebok)

## Setup Steps

**1. Download the Repository Zip:**
  - Click Code Button > Download ZIP to download the zip file from this repository.
  
  <img width="676" alt="image" src="https://github.com/limkimhoe/docker-python-mongo-mysql/assets/22229616/93cbc897-bc7f-420d-9cb4-3f778061af53"><br/><br/>

   
**2. Create Project Workspace:**
   - Create a "Workspace" folder on your C:\ or D:\ drive.
   - Inside the Workspace folder, create a subfolder for your project.
     - Example: C:\Workspace\YOUR_PROJECT_NAME
   - Note: This step links your local Workspace folder with the container's Workspace folder. 
     
**3. Unzip the Repository:**
   - Unzip the downloaded zip file into your project folder.
   - Your project folder should now have a structure like this:
     
  <img width="126" alt="image" src="https://github.com/limkimhoe/docker-python-mongo-mysql/assets/22229616/97638aba-86f6-4866-bf16-d101267a98e0"><br/><br/>
  
     
**4. Install Dev Containers Extension:**
   - Launch Visual Studio Code (VSC) and install the Dev Containers extension.

   <img width="800" alt="image" src="https://github.com/limkimhoe/docker-python-mongo-mysql/assets/22229616/9d4d500c-bbe2-4f55-bf95-1d27849b232d"><br/><br/>
   
   
**5. Open Your Project in VSC:**
   - Open your project folder by clicking File > Open Folder and navigate to your project folder.
   
   <img width="240" alt="image" src="https://github.com/limkimhoe/docker-python-mongo-mysql/assets/22229616/5a9578d9-72b4-49be-83b3-01d779f585d2"><br/><br/>

   
**6. Reopen Container:**
    - A popup saying "Reopen" should appear in the bottom right corner. If not, follow these steps:
       - Press F1.
       - Type "Dev Container: Reopen Container".
   
   <img width="360" alt="image" src="https://github.com/limkimhoe/docker-python-mongo-mysql/assets/22229616/bb808168-70f0-4b77-be58-2106e0e5e12f"><br/><br/>

   
**7. Container Setup:Container Setup:**
    - VSC will reopen the folder, download, and install the necessary container files. This may take 10-15 minutes depending on your internet speed.
   
   <img width="453" alt="image" src="https://github.com/limkimhoe/docker-python-mongo-mysql/assets/22229616/2ebe070c-00d5-4463-b8d3-73895bfeecde"><br/><br/>

       
**8. Confirmation:**
   - Once you see a blue bar at the bottom left of VSC, the container has been created successfully.
   
   <img width="202" alt="image" src="https://github.com/limkimhoe/docker-python-mongo-mysql/assets/22229616/a1526e26-d87d-4eab-8863-35b1df42e20e"><br/><br/>
    
**9. Testing Database Connections:**
   - Open the "DBConnectionTest.ipynb" notebook file in VSC by double clicking the file.
   
   <img width="928" alt="image" src="https://github.com/limkimhoe/docker-python-mongo-mysql/assets/22229616/d670b8ae-c3a0-4df5-b150-9b8a5e46b82c"><br/><br/>


**10. MySQL Connection Test:**
   - Click the play button to run the Python script for MySQL DB connection test.
   
   <img width="86" alt="image" src="https://github.com/limkimhoe/docker-python-mongo-mysql/assets/22229616/a714c6d1-d16f-4d51-99bb-9e14f24f545b"><br/><br/>

    
**11. MySQL Test Result:**
   - You should see the output of "(1, 'Test Name)" if successful.
   
   <img width="527" alt="image" src="https://github.com/limkimhoe/docker-python-mongo-mysql/assets/22229616/1c4340d0-76e7-487b-93b7-e16e0cebf52e"><br/><br/>


**12. MongoDB Connection Test:**
   - Scroll down to click the play button to run the Python script for MongoDB connection test.
   
   <img width="98" alt="image" src="https://github.com/limkimhoe/docker-python-mongo-mysql/assets/22229616/00748099-e825-4f04-a408-fc8d7dc08ae9"><br/><br/>

    
**13. MongoDB Test Result:**
   - You should see the output of "{'_id': ObjectId('65a1178e2be39485c150fb05'), 'name': 'Test', 'value': 123}" if successful.
   
   <img width="377" alt="image" src="https://github.com/limkimhoe/docker-python-mongo-mysql/assets/22229616/128e9076-1de4-457c-92a2-743bbff42ba8"><br/><br/>



## Congratulations! Your setup is complete, and you are ready for Python development!
