0.	The following code is applicable to Linux servers, download using Node's official Linux package manager
https://nodejs.org/en/download/package-manager
Recommended to install using NVM
Follow the command line prompts on the official website to select and install Node 18 or above (recommended to install LTS suffixed versions)
Copy the Linux commands from the page line by line and execute them on the server, wait for completion prompts, then check if the installed version is correct. After that, please restart the command window or remote window.
Next, use npm to install the necessary backend runtime environment:

1.	npm i ws -g
Globally install websocket for node plugin to enable node to support websocket protocol. If running the program with pm2 fails in step 6 below, use the cd command to enter the folder from step 6 and use npm i ws to configure the plugin separately in that folder.

2.	npm i pm2 -g
Globally install PM2. Since node programs don't support background running, and using Linux's built-in background running is unreliable, it's recommended to use PM2 to host your program in the background (supports automatic restart when the program crashes).

3.	Create a folder in the directory to store server-side code (for example: www/myws) and place the websocketNode.js file into it.

4.	Use the cd command to enter your folder (for example: cd www/myws)

5.	Execute the command npx pm2 start websocketNode.js to see the running prompt.
If you need to view the log output printed during runtime, after running the code, enter npx pm2 log 0 in the command line in this directory and press Enter to view.
(Usually when you only have one program running, the id is 0. If you're running multiple programs, after executing the start command, the command line will display the id for this task - replace the 0 at the end of the command with the corresponding id)
