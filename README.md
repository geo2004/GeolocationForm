# GeolocationForm
This repo is an implementation of a HTML Form which has ability to store the data in Google Sheets, thanks to Google App Scripts Service. Other than storing the response data in GSheets, this form is also enable to extract devices location using Browser built-in Geolocation Call. 

Here are the steps to how to use the code. 
1. Create a New Google Sheets Spreadsheet. Give a meaningful and consistent header such as the image below: 

![image](https://user-images.githubusercontent.com/46329778/227413536-eb9b4882-be0a-4298-aed6-0d0eb3dce275.png)

2. Share it as public (anyone with the link) and set the anyone as Editor. 

3. From the GSheets Menu, go to Extension > App Scripts. 

4. Delete the initial function, and copy/paste the GoogleAppScripts file in this repo. 
5. Pay attention to SheetName constructor, the SheetName should be matched with the Sheet Name (equivalent with tab name in MS Excel, do not confuse it with Gsheet filename) you are working on. 

5. Run the Initial Setup Function. Image description as follow. 

![image](https://user-images.githubusercontent.com/46329778/227414040-2a91bec7-66f1-40a0-b9f4-ed3ebd7763af.png)

Because the script has not been approved by Google, you will get a prompt asking for your permission before you can proceed. For the script to have the proper rights to update your form, you must first click the "show advanced" text, then click <"Script Name>." In essence, this is just another permission request, like the ones you see when you add new plugins or modules to your regular Google workspace items. Once you have completed this step, move on to step 6.

6. Add trigger from the Script. 

Select the project "Triggers" from the sidebar and then click the Add Trigger button.

In the show up window, select the following options:

Choose which function to run: doPost ;
Choose which deployment should run: Head ;
Select event source: From spreadsheet ;
Select event type: On form submit ;

![image](https://user-images.githubusercontent.com/46329778/227414747-6f99c330-ad51-4a12-bff4-e1c16cf73336.png)

then, Click SAVE. 

7. Publish The Project 

Now your project is ready to publish. Hit the Deploy button and New Deployment from the drop-down.

Click the "Select type" icon and select Web app.

In the form that appears, select the following options:

Description: Geolocation (The description text is free to modify as you want)
Web app → Execute As: Me
Web app → Who has access: Anyone
Then click Deploy.

Save the Web App URL before you are moving to the next step. 


8. Create The HTML Form. 

build your own HTML form as you wish (see the example.html in this repo for a basic example of the form). The most important part in the HTML Form creation is on the Input Field, make sure the Input Name Tags is matched with the GSheets Headers. 

second, Add the Geolocation Request Function inside the <script> tags, and point the captured data to the HTML input fields, 

Third, place the Web App URL in Step 7 to the Form Action tag. 

The looks of example HTML in this repo is like this below: 

![image](https://user-images.githubusercontent.com/46329778/227415593-0dd97d86-74fd-43a1-9c3c-a82fd846ab32.png)

When you hit the Get Location Button, browser or device will ask about your device location, if you approve it, latitude and longitude values will automatically be populated in the respective fields, all other fields can be typed manually, when you are done, hit the Send button, the data will be send to GSheets. 


Here is the example of inputted data in GSheets
         
![image](https://user-images.githubusercontent.com/46329778/227415654-60138363-39e2-4f4a-ba95-87b0e0d1fd81.png)
         
------------------------------------------------------------------------------------------------------
         
## I also added some additional feature in the form such as capability to upload file to GDrive, insert the geolocation to EXIF metadata of the uploaded files and some more at this repo [GeolocationForm v2](https://github.com/geo2004/GeolocationForm-v2)


