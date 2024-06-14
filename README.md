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

2. Prerequisites:
   - A computer (or virtual machine) that can run Windows 10 or Windows 11
   - Virtual Studio 2019 and RS2 SDK or up, see [Developer](https://developer.microsoft.com/en-us/windows/downloads/)
   - Depending on your configuration, you might have to install the Microsoft.NETCore.UniversalWindowsPlatform NuGet package.
   - Enable **Developer Mode** in your system
   - Digital pen and tablet
  
3. 
