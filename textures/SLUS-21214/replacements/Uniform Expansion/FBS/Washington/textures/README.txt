This is a batch renaming companion utility for the NCAA NEXT Uniform Expansion project. Please note that a uniform kit cannot be used until all textures are done. The script will not run unless all textures and their new filenames are provided. The only files that may be ommitted are the pride sticker, helmet numbers, and sleeve/shoulder numbers, but a filename must still be provided for the pride sticker so the script can make a transparent PNG.

INSTRUCTIONS:

STEP 1. Copy all of the exported PNG files from the TC Gear template into the "put_exported_textures_in_here" folder.

NOTE: Don't feel like you need to use the chinstrap from the TC Gear template. It's probably best to use a plain white one anyway, unless you see differently in reference photos. The default white one is in the 'default-textures' folder. If you want to use that, copy it into the 'put_exported_textures_in_here' folder and replace the chinstrap from the TC Gear export. Make sure it is named 'img22.png' or '22-Chinstrap.png'.

STEP 2. Put your other uniform pieces in the same folder. They must be named exactly as follows. The number shadows are automatically made transparent. No need to add those.

helmet.png
pants.png
jersey.png
pridesticker.png*
num07.png
num89.png
num07helmet.png*
num89helmet.png*
num07ss.png† 
num89ss.png† 

* if no replacement texture is provided, a transparent will be created automatically.

† if no replacement texture is provided, the script will use the main jersey numbers for the sleeve/shoulders (this is usually what you want)

STEP 3. After dumping textures and recording the file names in the Texture-Dumps-Tracker.csv spreadsheet, copy the 34 rows of the "FILENAME" column into texture-names.txt. Make sure that none of the cells are blank, even if they are not needed (eg. if helmet numbers are disabled). Put a dash or "na" in that case.

STEP 4. Double-click the batch-rename-textures.bat file. It will copy the appropriate files from the "put_exported_textures_in_here" folder into a newly created folder called "renamed", and will rename them accordingly.

STEP 5. Rename the 'renamed' folder to the name of the uniform slot (Eg. home, away, alt01, alt02, etc.).

STEP 6. Test the textures in your emulator to ensure all of the replacement textures are named properly and working as intended. PLEASE DO NOT SKIP THIS STEP!

STEP 7. If everything looks good and is working as expected, upload the home/away/alt01/etc folder to Google Drive. Be sure to put it in the correct team folder.
https://drive.google.com/drive/folders/1jKRN70C3EIExMDVUeHQ2x_yei1iKjwbm

STEP 8. Post in the #files-to-merge channel the name of the team and uniform slot(s) you uploaded.

THANK YOU!

