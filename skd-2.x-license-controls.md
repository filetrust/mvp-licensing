# SDK 2.x License Controls 

 

## User Story 57226 – Identify approach to extend existing kill switch to a file process time limited based kill switch 

The plan is to use an encrypted file that will control how long a SDK can be used and what features are available to the client, 

 

##License file Description  

The plan is to use an encrypted file that will contain: 

- Expiry Date  
- Version of SDK to which it applies 
- ID number relating to the client that the license was created for 
- Optional Flags that switch certain features on and off 

The encryption will use a “two key encryption algorithm” with the Core code holding one of the keys 

Core Support will look for a specific hidden file in installed directory (or perhaps other commonly accessible locations in Linux and or Windows) 

The file will be created by either a small command-line app (for testing) or a web-based license manager  

Initially, if license is not found, then no limits to operation - **NB This would be a deprecated feature in the future**

If license is found not matching SDK or past expiry the date then operation stops 
 

## Command Line License Generator  

A commandline tool will allow developers to create test licenses for internal use. 

It will have options to set  

- Expiry Date  
- Version of SDK to which it applies 
- ID number relating to the client that the license was created for 
- Optional Flags that switch certain features on and off - TBD – or future feature – comments please 

Possible optional use of path to an sdk library to self determine the sdk version 

Our commandline tool will be updated with each release of SDK so that internally they can share the same encryption key (although, we will need to keep the license manager up to date too) 


## Web interface driven License Manager 

The license file will be obtained for clients through an online License Manager 

### User Side 

Users will be able to 
- Create an account 
- Select a product license package based on 
  - Length of license 
  - Features available  
    - Camera groups? 
    - Export/Import 
    - Text Search 
    - Archive Support 
- Chose delivery mechanism 
- Pay for that license 

### Admin Side 

Glasswall Admin will be able to: 

Create  accounts for clients (including internal ones) 

- Select a product license package based on 
  - Length of license 
  - Features available  
    - Camera groups? 
    - Export/Import 
    - Text Search 
  - Archive Support 
- Chose delivery mechanism 
- Invoice for that license 
- Get license for free – internal test use 
- Update the list of SDK Versions and their associated keys 
