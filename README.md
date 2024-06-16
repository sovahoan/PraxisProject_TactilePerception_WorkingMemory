# Getting Started Ink tutorial
1. Introduction:
   
   This is the repository for the basic Windows app that supports writing with Windows Ink, used primarily in the context of the Praxis Project "Investigating the effect of tactile perception on the working memory". It contains snippets from a sample app, which you can find and download from Github [Sample code](https://github.com/Microsoft/Windows-tutorials-inputs-and-devices/tree/master/GettingStarted-Ink).
   The following tools are implemented:
     + Add an average pressure meter for each stroke collected.
     + Recognizing when the average pressure of said stroke is under a certain threshold
     + Play a small sound when the pressure is below the threshold
     + Support handwriting recognition
     + Record average pressure of each recognized word and export to a CSV file
   For further information, please see [Tutorial: Support ink in your Windows app](https://learn.microsoft.com/en-us/windows/apps/design/input/ink-walkthrough#sample-code)

3. Prerequisites:
   - A computer (or virtual machine) that can run Windows 10 or Windows 11
   - Virtual Studio 2019 and RS2 SDK or up, see [Developer](https://developer.microsoft.com/en-us/windows/downloads/)
   - Depending on your configuration, you might have to install the Microsoft.NETCore.UniversalWindowsPlatform NuGet package.
   - Enable **Developer Mode** in your system
   - Digital pen and tablet
  
4. Sample
   - Download or clone this repository to your local machine:
     
     ![image](https://github.com/sovahoan/PraxisProject_TactilePerception_WorkingMemory/assets/143092181/6b15efd8-642b-420b-8c67-70ffd5afecff)
   - Open the sample in Visual Studio. I already uncomment and add neccessary changes, so it should look something like this:
     
     ![image](https://github.com/sovahoan/PraxisProject_TactilePerception_WorkingMemory/assets/143092181/8110cd2f-847b-4165-89b6-527e46e96ef0)
   - Run the sample by pressing **Run Local Machine**:
     
    ![image](https://github.com/sovahoan/PraxisProject_TactilePerception_WorkingMemory/assets/143092181/9ea71696-b3d1-4d5b-8521-9371f8977116)
   - The app windows then opens, and after a splash screen for a few seconds, you should see something like this:
     
     ![image](https://github.com/sovahoan/PraxisProject_TactilePerception_WorkingMemory/assets/143092181/7f3fa9c9-f941-4c59-97b1-e6a52d44773c)
     
   - A clear and blank canvas, in case you need to add a heading, you can also visit the XAML file and add it, I also don't show the current pressure, you can see it in **Output** window in Visual Studio (View > Output), or uncomment the line:
     ```
     pressureTextBlock.Text += $"Pressure: {averagePressure:F2}";
     ```
     
   - A small beep should play when the pressure is under 0.6, you can change it by simply replace 0.6 with your desired value in the line:
      ```
      //Check if pressure is less than 0.6
      if (averagePressure < 0.6f)
     ```
      
   - To replace the sound, import your sound to folder **Assets**, then replace the current sound file name in the code with your file:
    ```
    Windows.Storage.StorageFolder folder = await Windows.ApplicationModel.Package.Current.InstalledLocation.GetFolderAsync(@"Assets");
    Windows.Storage.StorageFile soundFile = await folder.GetFileAsync("beep.wav"); //replace beep.wav with your file here
    ```
    
   - When done with writing, you can press **Recognize text** to record the average pressure of each word, it will then prompt the screen so you can pick where to save and rename the file accordingly to the mothercode:
     
 ![image](https://github.com/sovahoan/PraxisProject_TactilePerception_WorkingMemory/assets/143092181/0fecdaac-c2b9-435b-adc9-d34177d66bc7)

   - Please be warned that the recogntition capabilities of this UWP is limited, therefore it will be a long list, the same word will have the same pressure value to pick. Case and point:
     
 ![image](https://github.com/sovahoan/PraxisProject_TactilePerception_WorkingMemory/assets/143092181/57215430-4f3f-4127-83a3-e8fa9c2013ed)

 (Handwriting recognition can be improved through **Pen & Windows Ink** settings: Start menu > Devices > Pen & Windows Ink > Get to know my handwriting > Handwriting Personalization) - I don't have this option though.

   - When you want a new fresh canvas, click **Clear**, when clicking this, you will lose previous ink and its data (unless saved - only saving the recognized text and pressure, not handwriting). We can use a screenshot to capture handwriting if needed, or implement **Save and load ink**  (see [Tutorial](https://learn.microsoft.com/en-us/windows/apps/design/input/ink-walkthrough#prerequisites))

*The sound plays when stroke pressure is lower than threshold. File saved will be a list of average pressure of each recognized words (otherwise it'll be too many values)



     


