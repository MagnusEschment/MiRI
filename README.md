# MiRI - Android/iOs/web application for patient assessment at Emergency Rooms
Digitalizinting patient assessment to reduce patient numbers and thus decrease waiting times at the Emergency Room (ER) at MRI - Klinikum München rechts der Isar in Munich, Germany. This is made possible through implementation of hardware including software application to increase patient satisfaction and relocation in the emergency room.


## Things used in this project:

### Software:
XCode IDE: https://developer.apple.com/xcode/ <br/>
Flutter: https://flutter.dev/docs/get-started/install <br/>
Figma: https://www.figma.com

### Hardware: 
MacOS based solution *(our solution)* : iPad with no further requirements<br/>
Windows based solution: tablet or computer with no further requirements

Avoiding theft: Properly mounting hardware by using table-top mounted, wall-mounted, or floor-mounted kiosks with security fasteners (star screws and key locks). If a non-mounted table-top tablet or kiosk is used, theft can be eliminated by putting the devices in close proximity to staff – ideally on the same countertop where the paper sign-in sheet was previously located.

Small ticket printer: Right next to it, it is necessary to mount or attach a small printer which prints a small ticket for the patient with his personal waiting ID as well as a personal password.

## Story:
MiRI is a software and hardware solution which was developed by students of Technical University Munich during the Tech Challenge in the winter semester 2020/2021 for the hospital MRI Klinikum München rechts der Isar. MRI has stated the challenge to improve the patient journey and patient experience to which MiRI is the perfect answer for. This guide will step by step explain how this prototype was built in order to recreate it. 

### What is MiRI?

The underlying problem at MRI is the low customer satisfaction of people who are treated there. Local field research, internet research, interviews with patients and medical staff as well as further surveys pointed out that this is caused by non-transparent waiting times in the ER. These occur because 50-75% of all ER patients are wrongly in the ER due to lack of knowledge (e.g. where to go), because of special occasions (e.g. weekend, holiday) or false expectations (to get treatment faster than at specialists or family doctors). 

MiRI is an iOS application on a stationary iPad placed noticeable close to the ER entrance which allows the patient to get a quick digital patient assessment when arriving at the Emergency room in a hospital and is embedded in the hospital check-in process.Therefore, MiRI includes a smart learning algorithm which weights answers of questions designed by doctors. Based on the answers, the waiting time is estimated. Over time, the data will be saved anonymously and analyzed in order to create new models to predict waiting times even more precisely. How this works, will later be explained in detail. 

![alt text](https://user-images.githubusercontent.com/46497859/105819758-e2e1c480-5fb8-11eb-9dc0-56dbdd3ea63c.png)

### How does MiRI work: 
MiRI is implemented in the regular check-in process at the ER, however intervenes before the patient check-ins with his patient data. It is important to note that MiRI only applies for patients who are able to fill out our the survey on their own. Patients that enter with obvious signs of life threatening situations as well as with the ambulance are excluded.
Therefore, when the patient arrives at the ER at the end of the assessment, an estimated approximate waiting time is displayed. This waiting time as well as the categorized patient condition is backed up by medical staff who usually welcomes the patient anyway. Furthermore, after seeing the minimum waiting time, the patient has the option to view alternative treatment options (if applicable) as well as to book doctors’ appointments or find the next pharmacy. Based on the waiting time and other treatment options, the patient then has the ability to make the best possible decision to stay or to receive alternative treatment. MiRI will help relocate the patients, save costs for hospitals as well as make efficient use of the health care system. 

### Advantages of MiRI:

*For patients: <br/>*
MiRI provides many advantages for patients. Through it’s fast assessment, it is time efficient and effective. Additionally, it provides transparency over waiting times, as well as flexibility for the patient, because the patient is able to go outside for some fresh air or grab a quick coffee, while having the waiting time displayed in the digital waiting room on his own device. MiRI satisfies the information need of the patient on the one hand through giving the estimated waiting time, on the other through providing additional information on alternative treatment options - so the patient is able to make the best possible decision for his health and his preferences. This can result in relieving staff because questions regarding the waiting time and alternatives won’t be asked as much anymore. 

*For hospitals: <br/>*
MiRI also has several advantages for the hospital. Through providing information on alternative treatment options with less waiting times, MiRI helps relocating patients who are not in need of emergency care. This reduces not only the overall number of ER patients but also decreases costs for the hospital by up to 46%. Furthermore, this lowers the risk of spreading infectious diseases especially within the Covid-19 pandemic and structures the waiting rooms. 


## Build:

### Preparation:
*How to recreate MiRI iOS application:<br/>*
When starting to build a prototype it is advisable to begin with thinking of how the user will use the app and on which device. For several reasons we decided to use an iPad application on a stationary iPad placed in the ER. Therefore, we created user interfaces on Canva to see what our iPad app design will look like. Then we recreated this design on Figma. We decided to keep the design clean and simple for several reasons:

* The app has to be intuitive and therefore self explanatory.
* It should be able to be used by anyone so it has to be easy to understand without any distractions. 
* The assessment has to be short.


To understand the user interfaces and the basic logic of the application, we have inserted them here (please also find the prototype on Figma):<br/>
https://www.figma.com/file/Van7VUQZtdmn9jtwJeNovL/Miri?node-id=0%3A1 

![alt text](https://user-images.githubusercontent.com/46497859/105746552-de2cfa00-5f3f-11eb-9a2b-aa4ac66a695c.png)


### Complete overview over all screens used in MiRI: 

Remark: The high number of screens exists because MiRI has to be adaptive to the situation of the patient. It has to have questions for the specific inquiry of the patient or display the different waiting times for the patient accordingly. 


The different screens will be explained in detail in the order of how they will be shown to the user.

1. *WelcomeScreens:* The *WelcomeScreen* in the app greets the user who then can intuitively click on the Next button. The next screens will provide further instructions and also explain that data security rules are met. <br/>

![alt text](https://user-images.githubusercontent.com/46497859/105745811-f8b2a380-5f3e-11eb-9bdb-da594ef452fb.png)

2. *MenuScreen* The *MenuScreen* lets the user choose from different options. The *HealthAssessment* will start the actual assessment. Apart from this option, the user can also choose from *Procedures* and *Instructions*. When clicking on *Procedures* the users get more information about basic hospital procedures (the hospitals decide which information they would like to provide here and can be adjusted for any hospital). The *Instructions* button will provide information on how to fill out the survey and call a medical eemployee for help if needed.<br/>

![alt text](https://user-images.githubusercontent.com/46497859/105745882-0e27cd80-5f3f-11eb-8923-49d544236524.png)

3. *HealthAssessment:* The answers to all questions asked in the *HealthAssessment* have individual weighting criteria which has a direct impact on the estimation of waiting time. Thus depending on what the patient clicks, the waiting time is estimated. The questions were designed with the help of medical experts to determine waiting times as precisely as possible and also give alert when symptoms of life threatening conditions like a stroke occur. The detailed algorithm will be explained later.<br/>

![alt text](https://user-images.githubusercontent.com/46497859/105749028-2c8fc800-5f43-11eb-9d21-f6a954b40140.png) <br/>

![alt text](https://user-images.githubusercontent.com/46497859/105745921-17b13580-5f3f-11eb-875a-e60017b475ac.png)

4. *IDScreens:* First, the app shows the personal ID and personal password on the printing Screen. This anonymous ID is used later on for the waiting queue while the password is used for special patient related activities such as deleting the own spot in the waiting queue. In the meantime the printer, which is attached to the patient assessment terminal prints a small card with personal ID and password. <br/>
The next screen gives further instructions and tells the patient that a medical expert will come soon to pick him/her up for a personal verification of the results. <br/>

![alt text](https://user-images.githubusercontent.com/46497859/105745968-2566bb00-5f3f-11eb-83b4-87025c8808a0.png)

5. *WaitingTimeScreen:* When clicking next the waiting time is calculated and displayed. This waiting time screen is the central node for further usage for the patient. A QR code leads to the virtual waiting room on the mobile phone, while the digital waiting room button leads to a short overview of the waiting room on the Ipad itself. <br/>
The alternative treatment button is connected to a second menu displaying other treatment options. At last, the finished button resets the Ipad as well as all data is stored so the next patient is not able to see the sensitive personal data.<br/>
When implementing the digital waiting room, then the QR Code will lead to a landing page with simply displays the numbers in line dependent from the waiting times. These numbers as well as the respective waiting times are entered by the medical staff after the back-up assessment and adjust automatically when time passes by.<br/>

![alt text](https://user-images.githubusercontent.com/46497859/105746043-3ca5a880-5f3f-11eb-81c9-a8fddc34fe05.png)

6. *AlternativeMenuScreen:* This Screen allows the patients to get more information about alternative options as well as book appointments at specialists and family doctors but also to locate pharmacies. The emergency hotline button which has an educational purpose because a lot of patients don’t know about the hotline 116117 for emergency cases in Germany.<br/> 

![alt text](https://user-images.githubusercontent.com/46497859/105746083-4af3c480-5f3f-11eb-9780-1bd867448cfc.png)

7. *TheVirtualWaitingRoom:* The virtual waiting room will be displayed as a landing page on the mobile phone which can be optionally accessed through scanning the QR-Code on the *WaitingTimeScreen*. It displays the waiting line as well as the respective times. It also has to services which can be used with the personal ID and password which were printed out for the patient earlier in the process. When entering the ID together with the password it is possible to postpone the treatment slot if you will be too late for your treatment time or to delete your spot complete and remove it from the waiting queue. 

![alt text](https://user-images.githubusercontent.com/46497859/105746125-59da7700-5f3f-11eb-8531-60067ce3dbbc.png)

### The weighting of the questions: 

As previously mentioned, the questions in the questionnaire have different purposes. There are the basic questions which only purpose is to collect demographic data which can be later used for further analysis (e.g. at what time which age group is primarily arriving at the ER). Then there are the questions which are used for the calculation of the waiting time and thirdly also specific trigger questions which trigger very fast or immediate treatment.<br/>
In general it is also important to notice that MiRI is only used for patients in the ER which do not suffer very severe conditions. Patients arriving with the ambulance or patients arriving on their own with very big pain are treated directly and do not have to do this pre-check in process.

Following questions are used for the calculation of waiting time: <br/>
* When did the symptoms occur? -> The shorter the time frame, the faster the treatment (ranging from one hour to three or more hours)
* Do you fill this out by yourself? -> if: “No, because I am medically not able to” then treatment time is reduced by 30 min to one hour
* What kind of pain do you have? -> if: “Bigger flesh wound” or “High fever” then treatment time is reduced by 30 min to one hour
* How strong is your pain subjectively? -> if “No pain” then treatment time is increased by 30 min

Following questions work as trigger question and result in very fast or immediate treatment because the are symptoms for a life threatening conditions such as a stroke: <br/>
* Do you experience any of the given symptoms (part1)
* Do you experience any of the given symptoms (part2)

Furthermore, MiRI aims to prevent waiting longer than 4 hours. If the waiting time for a patient is approaching this limit a notification is sent to the hospital so that they are notified of the long waiting time. Secondly the patient has certainly been informed about the long waiting time so the patient had the option to leave or to book a doctor’s appointment but willingly choose the longer treatment time in the hospital.

### *Basic assumptions:*

According to doctors, patients who are indeed able to fill out the survey themselves, require no immediate action and thus wait at least 2 hours if the waiting room is full. 


### Outlook:

Over time, the algorithm learns and thus also estimates the times more precisely. This includes also estimations based on different times of the day as well as different days. 



## Code:

![alt text](https://user-images.githubusercontent.com/46497859/105746583-e9802580-5f3f-11eb-8573-38fa438a66b4.png)

*Note: This is exemplary code in Java only that should illustrate how the logic for the calculation of waiting time would be implemented.

### Flutter Code:

This is the flutter code for the main method and the first two screens two illustrate how our app was implemented from the figma prototype which focus on the design part to the actual app that was created.

The main method starts when launching the app:<br/>
![alt text](https://user-images.githubusercontent.com/46497859/105819999-3eac4d80-5fb9-11eb-8600-485736dbd6d0.png)

This class is run by the main method:<br/>
![alt text](https://user-images.githubusercontent.com/46497859/105820274-a6629880-5fb9-11eb-8533-980b8f377c22.png)


This is the code which visualizes the first two screens and also implements the routing between the screens (going to the respective screen when clicking on the respective button):<br/>
![alt text](https://user-images.githubusercontent.com/46497859/105822064-e0349e80-5fbb-11eb-88f6-01ab9d65a645.png)

![alt text](https://user-images.githubusercontent.com/46497859/105822127-f6425f00-5fbb-11eb-9088-c71848872940.png)


## Final remarks

This project was created within a short and limited time frame and thus does not include a final product, but a product that has one working feature. 

## Credits: Team SMAG of Tech Challenge WS2020/21

Selina Graf: selina.graf@tum.de<br/>
Magnus Eschment: magnus.eschment@tum.de<br/>
Almira Kahya: kahyaalmira@gmail.com<br/>
Gizem Sirmali: gizemmsir@gmail.com<br/>


For any questions regarding the approach, application and coding as well as the description, please do not hesitate to contact us. 





