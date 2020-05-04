# Appatella Diagnostic Example

This is a project which you can use to get started to produce your own diagnostic tool, for use with the Appatella Mobile App

## Deploying Appatella Diagnostic 

___

### Requirements:

- [Visual Studio Code](https://code.visualstudio.com/)
- [Node.js](https://nodejs.org/en/about/)
- [NPM](https://docs.npmjs.com/about-npm/)
- [Heroku Account](https://signup.heroku.com/)
- [Github Account](https://github.com/join?source=header-home)
- [Github Desktop](https://desktop.github.com)

This guide will help clinicians accomplish these things:

- Installation of Node.js, NPM & Visual Studio Code
- Local deployment of their diagnostic server for testing.
- Deploy using Heroku for remote data collection

### Getting Started: 

#### Installing Node.js and NPM:

**Node.js** is a run-time environment which includes everything you need to execute a program written in JavaScript. It’s used for running scripts on the server to render content before it is delivered to a web browser.

NPM stands for Node Package Manager, which is an application and repository for developing and sharing JavaScript code.

**Prerequisites**

- A user account with administrator privileges (or the ability to download and install software)
- Access to the Windows command line (search > cmd > right-click > run as administrator) 

1. Go to https://nodejs.org/en/, this will bring you straight to the homepage.

2. Next, go to the navigation bar and click `DOWNLOADS`.

3. This page will contain a row of installations for different operating systems.

   - For Windows go to the row titled **Windows Installer** and click 64bit as most systems are this by standard however 32bit is also available. To check your systems specification go [here](https://www.windowscentral.com/how-check-your-computer-full-specifications-windows-10)
   - For Mac go the row titled **MacOS Installer** and click 64bit. 

4. When the installers have downloaded, go to your downloads folder and click the file to install.

5. Installation Process:

   1. You will be welcomed to the Node.js Setup Wizard – click Next.

   2. On the next screen, review the license agreement. Click Next if you agree to the terms and install the software.

   3. The installer will prompt you for the installation location. Leave the default location, unless you have a specific need to install it somewhere else – then click Next.

   4. The wizard will let you select components to include or remove from the installation. Again, unless you have a specific need, accept the defaults by clicking Next.

   5. Finally, click the Install button to run the installer. When it finishes, click Finish

6. Verifying your installation by opening a command prompt (or terminal), and enter the following:

   `node –v`

   `npm -v`

   The given commands above should return version numbers such as `v12.16.3`

___

#### Installing Visual Studio Code: 

1. Go to https://code.visualstudio.com, this will bring you straight to the homepage.
2. After opening the website, click on the Download for Windows(Download for Mac if on MacOS) button. This will download the VS code Setup Wizard on our system.
3. Run the VS code Setup Wizard So the VS code Setup Wizard is downloaded successfully and we need to run it.
4. At first, it recommends that we need to close all other application before the VS code installation starts. It is not mandatory.
5. In this step, read the license agreement and choose whether we accept it or not. But the installation continues only after we accept the agreement.
6. Choose the location in your system to install Visual Studio Code. If we are not bothering about the location, go with the default location.
7. As a default, the VS code shortcut will be placed in the Start Menu folder(Applications if on Mac). We can change the destination or skip creating shortcuts.
8. We get a group of additional tasks to be performed before the installation begins. Choose tasks we prefer and continue.
9. So we have set up everything and the VS code can be installed on our system now.
10. After the successful installation, we can launch the VS code on our system.

___

#### Installing Github Desktop:

GitHub Desktop is a tool that allows you to interact with GitHub from the desktop. With this new application, you can work easier without having to depend on your browser. GitHub Desktop supports: 

- Checkout branches with pull requests.
- Push to your remote Git repositories.

1. Open a browser and visit [desktop.github.com](https://desktop.github.com/).
2. Click Download for Windows or Mac dependent on your operating system.
3. When prompted, click Run.
4. Allow the installation to download and install.
5. Allow the program to open, it will then prompt you for your Github sign-in credentials

#### Downloading Appatella Diagnostic to Your System: 

1. To use the Appatella Diagnostic effectively you must have a GitHub account if you already have an account, skip to 4th step.
2. go to https://github.com/join?source=header-home, this will open a page of input fields such as: 

   - Username
   - Email
   - Password
3. Fill the required details accordingly then click create an account.
4. Go to https://github.com/CMDT/AppatellaDiagnostic, this will bring you to the diagnostics repository webpage.
5. Look for a button labelled 'Fork' then click, this will invoke a modal to appear asking "Where should we fork AppatellaDiagnostic?" choose your organisation.
6. This will create a new project repository and bring you to the webpage.
7. On the webpage, you will find a button labelled 'Clone or download' clicking this button will give you a dropdown featuring the options of: 

   - Open in desktop

   - Download Zip

8. Choose open in desktop, this will invoke a pop up asking "Do you want to allow this page to open Github Desktop?" click allow.
9. This causes Github Desktop to open with a window labelled 'Clone a Repository', click the blue button to clone. This will add the project to your system.
10. Finally, go to the toolbar > Repository > Open in Visual Studio Code 

___

#### Deploying Diagnostic Locally:

After opening the project in visual studio code you will see a menu of folders aside on the left; click the api folder.

1. You will find a swagger.yaml file click this file twice to open in visual studio code.

2. Go to line 10 and make sure it has "host: 'localhost:8010' #local debug"detailed within and is not greyed out if it is remove the '#' next to host.

3. Then go to line 18 the phrase 'schemes' will be found next to it, below this line you will find "http" make sure this not greyed out neither if it is remove the '#' 

4. Now go to your toolbar above to look for the phrase 'Terminal' click this then click 'New Terminal'

5. This will open a window beneath your YAML file prompting input.

6. Input `npm install` this will install necessary dependencies to run the project on your system.

7. Next, go to the play button aside on the left.

8. This will open a side-menu with a disabled button labelled 'Run and Debug' below this button you will a small line of text "To customize Run and Debug create a launch.json file." Click create a launch.json file in blue.

9. Remove everything within the launch.json file with `ctrl + a` or `cmd + a` then backspace.

10. Copy and past this block of code within: 

    ```json
    {
        // Use IntelliSense to learn about possible Node.js debug attributes.
        // Hover to view descriptions of existing attributes.
        // For more information, visit: https://go.microsoft.com/fwlink/?linkid=830387
        "version": "0.2.0",
        "configurations": [
            {
                "type": "node",
                "request": "launch",
                "name": "Launch Program",
                "program": "${workspaceRoot}/index.js"
            },
            {
                "type": "node",
                "request": "attach",
                "name": "Attach to Process",
                "address": "localhost",
                "port": 5858
            }
        ]
    }
    ```

    

11. Now go to the play button in the side-menu at the top of this menu you will see a the word 'Run' next to a play button with 'Launch Program'. Click Launch Program this will run your Diagnostic API.

12. Open your internet browser of choice and search `http://localhost:8010/docs` and that's all.

___

#### Deploying Diagnostic With Heroku 

1. To deploy your diagnostic server to Heroku you must have both a Heroku and Github account if you already have an account, skip to the 4th step.

2. go to https://signup.heroku.com, this will open a page of required input fields such as: 

   - First name
   - Last name
   - Email address
   - Role
   - Country
   - Primary developer language

3. Fill the required details accordingly then click create an account.

4. Navigate to your [Heroku Dashboard](<https://dashboard.heroku.com/apps>) and click the button labelled as 'New'

5. Producing two different options; applications and pipelines. Choose application. Give your application a name > Select your region > Create App

6. Taking you to the deploy tab of your application this where you deploy via Github, Heroku, more, however, choose Github.

7. Choosing Github will link with your organisation and repository of choice. Type in the repository's name > click search > connect.

8. Next, find the segment of the page titled 'Manual deploy'. Choose which branch you want to deploy from then click the button 'Deploy Branch'

9. This will deploy the server to a webpage linked as ex. `appatelladiagnostic.herokuapp.com/docs` 

   > However, at this time, the deployment will be successful but the webpage would not work as expected this is because there may need to be some changes made to the YAML which will be explained below.

   

10. Open visual studio code.

11. Go to file > open this will open up your file browser.

12. Go to the folder where you unzipped the diagnostic folder.

13. Click the folder then click open.

14. This will open the folder within visual studio code.

15. Opening the folder in the visual studio code will open the file explorer aside on the left; click the `api` folder.

16. You will find a swagger.yaml file click this file twice to open in visual studio code.

17. Go to line 12 and change the given URL to the one you will receive back from Heroku, this usually the name of your of application ex. `appatelladiagnostic.herokuapp.com`

18. Then go to line 18 the phrase 'schemes' will be found next to it, below this on line 19 you will find "https" make sure this not greyed out neither if it is remove the '#'. This is so your deployment will be under a secure connection.

19. After this change has been made and saved, open Github Desktop

20. Github Desktop will represent your changes in a window with a side-menu featuring a list of the changed files, below the list are two input boxes with placeholders of:

    - Summary(Required)
    - Description

    > It is commonly good practice to give a code change a summary of what has changed and a description of how it was changed but in this instance, we are just going to add a summary.

    

21. Input "Change to Swagger YAML for Heroku Deployment" in the summary input field.

22. Then click commit to master, then above the window click `push origin`, this will push your changes to your repository. Once that is done go back to your Heroku applications [dashboard](dashboard.heroku.com)

23. In your applications dashboard click the `deploy` tab  and scroll down to the page segment titled 'Manual deploy' then click the button 'Deploy Branch'





