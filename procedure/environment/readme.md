# Instructions for creating the computational environment used to run this study

This study uses the OSMnx package for network analysis. 
It can be finicky to install, so please use a clean environment. 

1. Install Anaconda Navigator (I used version 2.5.0)
2. Go to the 'Environments' tab and then at the bottom of the Environments page, 'New'
3. Name the new environment (I called it oxnz) and select your python version (I used 3.11), then hit 'create.'
4. Go to the 'Home' tab and make sure you are working in the oxnz environment.
5. Install the CMD.exe Prompt (I used version 0.1.1)
6. Launch the CMD.exe Prompt. It should be running from the oxnz environment (the command line will start with (oxnz)).
7. Run conda install -c conda-forge --strict-channel-priority osmnx (this will take a while!!)
8. Type y to proceed when prompted
9. Hopefully osmnx installed successfully! Now, return to the Anaconda navigation window (Home, in the oxnz environment).
10. Install JupyterLabs. When it loads, launch JupyterLabs and nagivate to the research compendium.
11. Celebrate!!! You did it :)

12. All packages needed to run this analysis will be documented in requirements.yml. After creating this environment, any additional packages needed *should* be downloadable from this file.
