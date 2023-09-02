@echo off
setlocal enabledelayedexpansion

rem Set the source and destination directories.
set "src_dir=put_exported_textures_in_here"
set "dest_dir=renamed"

set "errormsg=ERROR: Something went wrong. A uniform kit cannot be used unless all 30 to 34 textures are done. Either one is missing, something in the source folder is not named correctly, or a line is missing from the texture-names.txt file. Be sure the default-textures folder still exists and contains 15 files."

rem Create the destination directory if it doesn't exist.
if not exist "%dest_dir%" mkdir "%dest_dir%"
if not exist "%dest_dir%\gear" mkdir "%dest_dir%\gear"
if not exist "%dest_dir%\gear" mkdir "%dest_dir%\gear"
if not exist "%dest_dir%\transparents" mkdir "%dest_dir%\transparents"
if not exist "%dest_dir%\transparents\pride-sticker" mkdir "%dest_dir%\transparents\pride-sticker"
if not exist "%dest_dir%\transparents\num07-shadow" mkdir "%dest_dir%\transparents\num07-shadow"
if not exist "%dest_dir%\transparents\num89-shadow" mkdir "%dest_dir%\transparents\num89-shadow"
if not exist "%dest_dir%\transparents\num07-helmet" mkdir "%dest_dir%\transparents\num07-helmet"
if not exist "%dest_dir%\transparents\num89-helmet" mkdir "%dest_dir%\transparents\num89-helmet"
if not exist "%dest_dir%\transparents\README.txt" (
    echo INSTRUCTIONS: >> "%dest_dir%\transparents\README.txt"
    echo.>> "%dest_dir%\transparents\README.txt"
    echo This transparents folder is for any textures that you make transparent to disable them in the game. For example, if you don't want to have pride stickers on the helmet, make the 'pridesticker.png' texture that you put in 'put_exported_textures_in_here' transparent. Then, after it is renamed by the script and put in the root of the 'renamed' folder, move that file into the respective folder in this directory so we know what it is in case we want to enable it again down the road.  >> "%dest_dir%\transparents\README.txt"
)

rem Open the text file that contains the new filenames.
set "file_list=texture-names.txt"

rem Check if the file has at least 32 lines
set "line_count=0"
for /F %%i in ('type "%file_list%" ^| find /c /v ""') do set "line_count=%%i"

if !line_count! LSS 34 (
    echo .
    echo ERROR: The texture-names.txt file does not contain 34 lines. Be sure to put na or a dash in the helmet and sleeve numbers fields if those are disabled and there is no filename.
    echo .
    rmdir /s /q "%dest_dir%"
    pause
    exit /b 1
)

rem Initialize line counter.
set "line=0"

rem Process the lines in the text file and rename the corresponding files in the source directory.
for /F "usebackq delims=" %%i in ("%file_list%") do (
    set /A "line+=1"
    set "new_name=%%i.png"

    rem Check if the current line number matches the specified logic and rename the corresponding file accordingly.
    if !line! == 11 (
        if exist "%src_dir%\img1.png" (
            echo "Renaming img1.png to !new_name!"
            copy "%src_dir%\img1.png" "%dest_dir%\gear\!new_name!" >nul
        ) else if exist "%src_dir%\01-TC_Wrist.png" (
            echo "Renaming 01-TC_Wrist.png to !new_name!"
            copy "%src_dir%\01-TC_Wrist.png" "%dest_dir%\gear\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
    ) else if !line! == 10 (
        if exist "%src_dir%\img3.png" (
            echo "Renaming img3.png to !new_name!"
            copy "%src_dir%\img3.png" "%dest_dir%\gear\!new_name!" >nul
        ) else if exist "%src_dir%\03-TC_QB_Wrist.png" (
            echo "Renaming 03-TC_QB_Wrist.png to !new_name!"
            copy "%src_dir%\03-TC_QB_Wrist.png" "%dest_dir%\gear\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
    ) else if !line! == 6 (
        if exist "%src_dir%\img4.png" (
            echo "Renaming img4.png to !new_name!"
            copy "%src_dir%\img4.png" "%dest_dir%\gear\!new_name!" >nul
        ) else if exist "%src_dir%\04-TC_Thin_Band.png" (
            echo "Renaming 04-TC_Thin_Band.png to !new_name!"
            copy "%src_dir%\04-TC_Thin_Band.png" "%dest_dir%\gear\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
    ) else if !line! == 1 (
        if exist "%src_dir%\img6.png" (
            echo "Renaming img6.png to !new_name!"
            copy "%src_dir%\img6.png" "%dest_dir%\gear\!new_name!" >nul
        ) else if exist "%src_dir%\06-TC_Face_Protector.png" (
            echo "Renaming 06-TC_Face_Protector.png to !new_name!"
            copy "%src_dir%\06-TC_Face_Protector.png" "%dest_dir%\gear\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
    ) else if !line! == 2 (
        if exist "%src_dir%\img25.png" (
            echo "Renaming img25.png to !new_name!"
            copy "%src_dir%\img25.png" "%dest_dir%\gear\!new_name!" >nul
        ) else if exist "%src_dir%\25-TC_Face_Protector_Top.png" (
            echo "Renaming 25-TC_Face_Protector_Top.png to !new_name!"
            copy "%src_dir%\25-TC_Face_Protector_Top.png" "%dest_dir%\gear\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
    ) else if !line! == 5 (
        if exist "%src_dir%\img7.png" (
            echo "Renaming img7.png to !new_name!"
            copy "%src_dir%\img7.png" "%dest_dir%\gear\!new_name!" >nul
        ) else if exist "%src_dir%\07-TC_Med_Band--34_sleeve_top.png" (
            echo "Renaming 07-TC_Med_Band--34_sleeve_top.png to !new_name!"
            copy "%src_dir%\07-TC_Med_Band--34_sleeve_top.png" "%dest_dir%\gear\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
    ) else if !line! == 4 (
        if exist "%src_dir%\img10.png" (
            echo "Renaming img10.png to !new_name!"
            copy "%src_dir%\img10.png" "%dest_dir%\gear\!new_name!" >nul
        ) else if exist "%src_dir%\10-Wt_TC_Pad.png" (
            echo "Renaming 10-Wt_TC_Pad.png to !new_name!"
            copy "%src_dir%\10-Wt_TC_Pad.png" "%dest_dir%\gear\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
    ) else if !line! == 14 (
        if exist "%src_dir%\img11.png" (
            echo "Renaming img11.png to !new_name!"
            copy "%src_dir%\img11.png" "%dest_dir%\gear\!new_name!" >nul
        ) else if exist "%src_dir%\11-TC_Half_Sleeve.png" (
            echo "Renaming 11-TC_Half_Sleeve.png to !new_name!"
            copy "%src_dir%\11-TC_Half_Sleeve.png" "%dest_dir%\gear\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
    ) else if !line! == 19 (
        if exist "%src_dir%\img13.png" (
            echo "Renaming img13.png to !new_name!"
            copy "%src_dir%\img13.png" "%dest_dir%\!new_name!" >nul
        ) else if exist "%src_dir%\13-Sock.png" (
            echo "Renaming 13-Sock.png to !new_name!"
            copy "%src_dir%\13-Sock.png" "%dest_dir%\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
    ) else if !line! == 3 (
        if exist "%src_dir%\img14.png" (
            echo "Renaming img14.png to !new_name!"
            copy "%src_dir%\img14.png" "%dest_dir%\gear\!new_name!" >nul
        ) else if exist "%src_dir%\14-Bk_TC_Pad.png" (
            echo "Renaming 14-Bk_TC_Pad.png to !new_name!"
            copy "%src_dir%\14-Bk_TC_Pad.png" "%dest_dir%\gear\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
    ) else if !line! == 7 (
        if exist "%src_dir%\img15.png" (
            echo "Renaming img15.png to !new_name!"
            copy "%src_dir%\img15.png" "%dest_dir%\gear\!new_name!" >nul
        ) else if exist "%src_dir%\15-TC_Long_Sleeve.png" (
            echo "Renaming 15-TC_Long_Sleeve.png to !new_name!"
            copy "%src_dir%\15-TC_Long_Sleeve.png" "%dest_dir%\gear\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
    ) else if !line! == 15 (
        if exist "%src_dir%\img16.png" (
            echo "Renaming img16.png to !new_name!"
            copy "%src_dir%\img16.png" "%dest_dir%\!new_name!" >nul
        ) else if exist "%src_dir%\16-Shoe.png" (
            echo "Renaming 16-Shoe.png to !new_name!"
            copy "%src_dir%\16-Shoe.png" "%dest_dir%\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
    ) else if !line! == 16 (
        if exist "%src_dir%\img17.png" (
            echo "Renaming img17.png to !new_name!"
            copy "%src_dir%\img17.png" "%dest_dir%\!new_name!" >nul
        ) else if exist "%src_dir%\17-Shoe_w_White_Tape.png" (
            echo "Renaming 17-Shoe_w_White_Tape.png to !new_name!"
            copy "%src_dir%\17-Shoe_w_White_Tape.png" "%dest_dir%\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
    ) else if !line! == 23 (
        if exist "%src_dir%\img18.png" (
            echo "Renaming img18.png to !new_name!"
            copy "%src_dir%\img18.png" "%dest_dir%\!new_name!" >nul
        ) else if exist "%src_dir%\18-Facemask_Far.png" (
            echo "Renaming 18-Facemask_Far.png to !new_name!"
            copy "%src_dir%\18-Facemask_Far.png" "%dest_dir%\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
    ) else if !line! == 24 (
        if exist "%src_dir%\img20.png" (
            echo "Renaming img20.png to !new_name!"
            copy "%src_dir%\img20.png" "%dest_dir%\!new_name!" >nul
        ) else if exist "%src_dir%\20-Facemask_Near.png" (
            echo "Renaming 20-Facemask_Near.png to !new_name!"
            copy "%src_dir%\20-Facemask_Near.png" "%dest_dir%\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
    ) else if !line! == 21 (
        if exist "%src_dir%\img22.png" (
            echo "Renaming img22.png to !new_name!"
            copy "%src_dir%\img22.png" "%dest_dir%\!new_name!" >nul
        ) else if exist "%src_dir%\22-Chinstrap.png" (
            echo "Renaming 22-Chinstrap.png to !new_name!"
            copy "%src_dir%\22-Chinstrap.png" "%dest_dir%\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
    ) else if !line! == 17 (
        if exist "%src_dir%\img23.png" (
            echo "Renaming img23.png to !new_name!"
            copy "%src_dir%\img23.png" "%dest_dir%\!new_name!" >nul
        ) else if exist "%src_dir%\23-Shoe_w_Black_Tape.png" (
            echo "Renaming 23-Shoe_w_Black_Tape.png to !new_name!"
            copy "%src_dir%\23-Shoe_w_Black_Tape.png" "%dest_dir%\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
    ) else if !line! == 18 (
        if exist "%src_dir%\img24.png" (
            echo "Renaming img24.png to !new_name!"
            copy "%src_dir%\img24.png" "%dest_dir%\!new_name!" >nul
        ) else if exist "%src_dir%\24-Shoe_w_TC_Tape.png" (
            echo "Renaming 24-Shoe_w_TC_Tape.png to !new_name!"
            copy "%src_dir%\24-Shoe_w_TC_Tape.png" "%dest_dir%\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
    ) else if !line! == 20 (
        if exist "%src_dir%\helmet.png" (
            echo "Renaming helmet.png to !new_name!"
            copy "%src_dir%\helmet.png" "%dest_dir%\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
        
    ) else if !line! == 22 (
        set "name=!new_name!"
        set "png_check=!name:.png=!"
        if "!png_check!" NEQ "!name!" (
            if exist "%src_dir%\pridesticker.png" (
                echo "Renaming pridesticker.png to !new_name!"
                copy "%src_dir%\pridesticker.png" "%dest_dir%\!new_name!" >nul
            ) else (
                echo "No texture found for pridesticker.png. Creating transparent for !new_name!"
                copy "default-textures\transparent.png" "%dest_dir%\transparents\pride-sticker\!new_name!" >nul
            )
        ) else (
            echo "Line 22 does not contain '.png'. Deleting pride-sticker subfolder in transparents."
            rmdir /s /q "%dest_dir%\transparents\pride-sticker"
        )
    ) else if !line! == 25 (
        if exist "%src_dir%\pants.png" (
            echo "Renaming pants.png to !new_name!"
            copy "%src_dir%\pants.png" "%dest_dir%\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
        
    ) else if !line! == 26 (
        if exist "%src_dir%\jersey.png" (
            echo "Renaming jersey.png to !new_name!"
            copy "%src_dir%\jersey.png" "%dest_dir%\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
        
    ) else if !line! == 27 (
        if exist "%src_dir%\num07.png" (
            echo "Renaming num07.png to !new_name!"
            copy "%src_dir%\num07.png" "%dest_dir%\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
        
    ) else if !line! == 28 (
        if exist "%src_dir%\num89.png" (
            echo "Renaming num89.png to !new_name!"
            copy "%src_dir%\num89.png" "%dest_dir%\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
        
    ) else if !line! == 29 (
        echo "Renaming transparent.png to !new_name! for num07-shadow"
        copy "default-textures\transparent.png" "%dest_dir%\transparents\num07-shadow\!new_name!" >nul
        
        
    ) else if !line! == 30 (
        echo "Renaming transparent.png to !new_name! for num89-shadow"
        copy "default-textures\transparent.png" "%dest_dir%\transparents\num89-shadow\!new_name!" >nul
       
        
    ) else if !line! == 31 (
        set "name=!new_name!"
        set "png_check=!name:.png=!"
        if "!png_check!" NEQ "!name!" (
            if exist "%src_dir%\num07helmet.png" (
                echo "Renaming num07helmet.png to !new_name!"
                copy "%src_dir%\num07helmet.png" "%dest_dir%\!new_name!" >nul
            ) else (
                echo "No texture found for num07helmet.png. Creating transparent for !new_name!"
                copy "default-textures\transparent.png" "%dest_dir%\transparents\num07-helmet\!new_name!" >nul
            )
        ) else (
            echo "Line 31 does not contain '.png'. Deleting num07-helmet subfolder in transparents."
            rmdir /s /q "%dest_dir%\transparents\num07-helmet"
        )
    ) else if !line! == 32 (
        set "name=!new_name!"
        set "png_check=!name:.png=!"
        if "!png_check!" NEQ "!name!" (
            if exist "%src_dir%\num89helmet.png" (
                echo "Renaming num89helmet.png to !new_name!"
                copy "%src_dir%\num89helmet.png" "%dest_dir%\!new_name!" >nul
            ) else (
                echo "No texture found for num89helmet.png. Creating transparent for !new_name!"
                copy "default-textures\transparent.png" "%dest_dir%\transparents\num89-helmet\!new_name!" >nul
            )
        ) else (
            echo "Line 32 does not contain '.png'. Deleting num89-helmet subfolder in transparents."
            rmdir /s /q "%dest_dir%\transparents\num89-helmet"
        )
    )  else if !line! == 33 (
        set "name=!new_name!"
        set "png_check=!name:.png=!"
        if "!png_check!" NEQ "!name!" (
            if exist "%src_dir%\num07ss.png" (
                echo "Renaming num07ss.png to !new_name!"
                copy "%src_dir%\num07ss.png" "%dest_dir%\!new_name!" >nul
            ) else (
                echo "No texture found for num07ss.png. Using main jersey number texture for !new_name!"
                copy "%src_dir%\num07.png" "%dest_dir%\!new_name!" >nul
            )
        ) else (
            echo "Line 33 does not contain '.png'. Skipping sleeve/shoulder num07ss."
        )
    ) else if !line! == 34 (
        set "name=!new_name!"
        set "png_check=!name:.png=!"
        if "!png_check!" NEQ "!name!" (
            if exist "%src_dir%\num89ss.png" (
                echo "Renaming num89ss.png to !new_name!"
                copy "%src_dir%\num89ss.png" "%dest_dir%\!new_name!" >nul
            ) else (
                echo "No texture found for num89ss.png. Using main jersey number texture for !new_name!"
                copy "%src_dir%\num89.png" "%dest_dir%\!new_name!" >nul            )
        ) else (
            echo "Line 34 does not contain '.png'. Skipping sleeve/shoulder num89ss."
        )
    ) else if !line! == 8 (
        if exist "default-textures\wrist_QB_Wrist_Wt.png" (
            echo "Renaming default-textures\wrist_QB_Wrist_Wt.png to !new_name!"
            copy "default-textures\wrist_QB_Wrist_Wt.png" "%dest_dir%\gear\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
        
    ) else if !line! == 9 (
        if exist "default-textures\wrist_QB_Wrist_Bk.png" (
            echo "Renaming default-textures\wrist_QB_Wrist_Bk.png to !new_name!"
            copy "default-textures\wrist_QB_Wrist_Bk.png" "%dest_dir%\gear\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
        
    ) else if !line! == 12 (
        if exist "default-textures\wrist_Half_Sleeve_Wt.png" (
            echo "Renaming default-textures\wrist_Half_Sleeve_Wt.png to !new_name!"
            copy "default-textures\wrist_Half_Sleeve_Wt.png" "%dest_dir%\gear\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
        
    ) else if !line! == 13 (
        if exist "default-textures\wrist_Half_Sleeve_Bk.png" (
            echo "Renaming default-textures\wrist_Half_Sleeve_Bk.png to !new_name!"
            copy "default-textures\wrist_Half_Sleeve_Bk.png" "%dest_dir%\gear\!new_name!" >nul
        ) else (
            echo .
            echo %errormsg%
            echo .
            rmdir /s /q "%dest_dir%"
            pause
            exit /b 1
        )
        
    )
)
echo .
echo "DONE. Files were successfully copied to the 'renamed' folder and renamed. Please move any transparent PNGs to their correct subfolder."
echo .
pause
exit
