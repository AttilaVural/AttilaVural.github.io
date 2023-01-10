Installing node.js on Windows without admin rights

20. oktober 2022
13:34

1. Download the node.js LTS binary for Windows (https://nodejs.org/en/download/) and extract it to your desired location
	1. Extratede bare til skrivebrodet
2. Add the path of the nodejs folder to the PATH environment variable: 
	1. Shortcut winkey+R and enter: rundll32 sysdm.cpl,EditEnvironmentVariables
	2. Tilføj til sti til mappen under "user variables for ATVQ" (du kan ikke ændre system variables på NN PC)
3. Open a new command window (winkey+R and type cmd)
4. Type node -v and npm -v to verify the installation

From <https://stackoverflow.com/questions/37029089/how-to-install-nodejs-lts-on-windows-as-a-local-user-without-admin-rights> 
