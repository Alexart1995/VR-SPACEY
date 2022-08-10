# VR-SPACEY
Desktop and VR app for testing the quality of the approach of the cosmonaut rescue device with the International Space Station

## Introduction 
This Software was made in VR/AR Laboratory of Lomonosov Moscow State University depending on special practice of Mechanics and Mathematics Department of Lomonosov Moscow State University "Testing the quality of the approach of the cosmonaut rescue device with the International Space Station" (see in materials). <br>
Examples of how the application works are shown in the attached videos. <br>
Due to the fact that the work is the property of VR/AR Laboratory of Lomonosov Moscow State University, it is not possible to provide the source code. Regarding the description of the works and the demonstration of the code, please contact the author. <br>

## Desktop Version Overview
### Main Menu
<img src="https://github.com/Alexart1995/VR-SPACEY/blob/main/MainMenu.png" width="320" height="160"> <br>
### Generate Menu
<img src="https://github.com/Alexart1995/VR-SPACEY/blob/main/GenerateMenu.png" width="320" height="160"> <br> 
### Check Menu
<img src="https://github.com/Alexart1995/VR-SPACEY/blob/main/CheckMenu.png" width="320" height="160"> <br>
### Game Interface
<img src="https://github.com/Alexart1995/VR-SPACEY/blob/main/DesktopGameplay.png" width="320" height="160"> <br>

## VR Version Overview
### Game Interface
<img src="https://github.com/Alexart1995/VR-SPACEY/blob/main/VR1.png" width="320" height="160"> <br>
<img src="https://github.com/Alexart1995/VR-SPACEY/blob/main/VR3.png" width="320" height="160"> <br>
<img src="https://github.com/Alexart1995/VR-SPACEY/blob/main/VR5.png" width="320" height="160"> <br>

## Main menu
### Types of buttons
- GENERATE - switching to the option generation mode for students
- CHECK - switching to option check mode
- SETTINGS - selection of settings and management

## Generation Menu (GENERATE MENU)
In the Generation menu, the main indicators of the cosmonaut rescue device (hereinafter CRD) are set, its position and deviation (DataCollection.cs script)
All indicators are stored in the DataCollectionBetweenScreens class
### Calculation of the optimal trajectory
- After entering all the indicators, when the Calculate Distance button is pressed, the optimal approach trajectory is calculated, as well as the engine on/off time based on the entered indicators
### Generating an option for students
- When the GENERATE button is pressed, a variant with disturbances is formed for the student and writes the variant to a file Task.txt
- Also, all variants are written to a Json file to store all data of variants and for subsequent verification
- In parallel, the correct answer and the presence of a saddle point are calculated
- The calculation of the correct answer is stored in the DataCollectionBetweenScreen class, as well as in a Json file for further verification with the student's answer
### To Main Menu
- After completing the generation of options, when pressing the To Main Menu key, we go to the Main Menu

## The menu for checking the solution (CHECK MENU)
### The work performed by the student
- After receiving the variant, the student must find out whether there is a saddle point for these
conditions of the problem
- if a saddle point exists, find the worst disturbance and determine the best
value of the quality functional J0.
- According to the work done, the student introduces the worst disturbance and the presence of a saddle point in the fields allocated for this
### Task verification
- After completing the task, the student goes to the CHECK tab and enters his variant number
- Student variant data is loaded from a Json file to check the correct answer
- After completing the task and entering all the values of the disturbances, press the PLAY button (if you are in the desktop version!!!)
### Switching to simulation mode
- When the PLAY button is pressed, the transition to the simulation scene takes place
### VR version
- The VR version of the app is only available for demonstration
- The student, by clicking on Play VR, goes to the simulation scene of one of the predefined variants and can try to control the CRD using controllers

## Simulation scene (Desktop/VR)
All the main components of Software rotation, software convergence are located on the Move class (Move.cs)
The student can control the CRD depending on the version (desktop/VR)
### Desktop control
- A turn on the engines to move to the left
- D turn on the engines to move to the right
### VR Management
- Left Trigger turn on the engines to move to the left
- Right Trigger turn on the engines to move to the right
### Program turn (ProgramTurnMode.cs)
- Calculation of the angle of rotation, engine on/off time
- Application of calculated indicators for the rotation of the CRD
- Completion of the program turn the beginning of the program approach
### Program Approach (ProgramApproachMode.cs)
- The application of calculated indicators from the main menu and the use of disturbances set by the student
- Program approach of the CRD with the ISS under the control of the student
### Rating
- After the completion of the Approach, the student is given an assessment of the quality of personal Approach in an extreme situation according to the hundred-point system
- Also, the student is shown whether the maximin testing problem was solved correctly
- If the student solved the problem incorrectly, then the student moves to the CHECK MENU, where he can correct the worst disturbance introduced by him and try to go through the simulation Scene again
- In total, the student has 3 attempts to solve the problem
- In VR mode, a student can play the game an unlimited number of times
