Original App Design Project - README Template
===

# QueueUp

## Table of Contents
1. [Overview](#Overview)
2. [Product Spec](#Product-Spec)
3. [Wireframes](#Wireframes)
4. [Schema](#Schema)

## Overview
### Description
QueueUp, an app to make people wait in the line in a safer environment during these hard times. 

Every store will have an account in this app to let their customers know how many people are there in the store currently, is there a waiting line and how many people are in the line etc. Every customer who wants to go in to the store can check before hands if store is available. As customers go in, store will update their system. 

If the store that customers want to go in has reached its max capacity, the app will put them in a queue for that store and make people wait in their cars or even ath their homes. By creating a virtual queue, the app can help people tp keep their distance from each other and create safer waiting line environment.

### App Evaluation

- **Category:** Lifestyle
- **Mobile:** QueueUp will be primarily used in mobile phones. It may be used on a desktop as well, but the goal is to help users keep track of where they are in line, which is more suitable for mobile.
- **Story:** The app connects customers with businesses and transitions the burden of waiting in line onto a digital platform. Through this app, users can know when to come to a particular business rather than waiting there until its their turn.
- **Market:** Anyone can use this app
- **Habit:** This app can be used quiet often if users are going out frequently. It will be used more on busy places where there is a line.
- **Scope:** After talking with businesses to encourage them to use this app, users can start using this app to keep track of where they are in line.

## Product Spec

### 1. User Stories (Required and Optional)

**Required Must-have Stories**

    * [x] Configuring Parse server
    * [ ] Businesses can login to see how many customers are waiting in line
    * [ ] Businesses will have a QRCode reading mechanism to validate walking in users.
    * [ ] Businesses can add a customer in line 

**Optional Nice-to-have Stories**
* Customer side of the app:
    * Each User will have a unique QRCode assigned to themselves.
    * User logs in to see their line number in each businesses
    * User adds a new business to the QueueUp app to see when their turn will come on the 
    * Users deletes a business if he/she no longer wants to wait in line

* Customer side of the app:
    * If a user forgets to check queue status off the app and tries to walkin to a store at its max capacity, they should be placed into queue automatically by scanning the QRCode of the store.

### 2. Screen Archetypes

* Login
* Register- Users/Businesses sign up to create an account 
   * Upon Download/Reopening of the application, the user is prompted to log in to gain access to their profile information to be properly matched with another person.

### 3. Navigation

**Tab Navigation** (Tab to Screen)

* Home
* Profile
* Settings



**Flow Navigation** (Screen to Screen)
* Log-in -> Account creation if no log in is available and Option if customer/ employee
* Start Queue -> Jumps to Queue
* Profile -> shows name and history
* Settings -> Toggle settings to go to dark mode or chenge color cheme
## Wireframes
<img src="https://i.imgur.com/BVNogHs.png" width=600>

## Schema 
### Models

#### Accounts

##### Business Acconts
| Property | Type     | Description  |
| -------- | -------- | ------------ |
| StoreId  | String | Unique identifier(Possibly QR Code) for this store that allows users to easily to be added to Queue |
| storeName | String | Name of the Store/Business |
| storeQueue | Array | Data structure to save users |
| storeCapacity | Number | Numerical value of store max capacity. |
| currentShoppers | Number | Numerical value that gives current amount of users in the store|
| averageTimeSpent | Number | Descriptive value that tells how much time a user spends here on average. |



#### User Accounts
| Property | Type     | Description  |
| -------- | -------- | ------------ |
| userName     | String     | Name of the user |
| storesInQ     | Array     | A list of stores the user currently is queuing |
| userId     | String     | Unique identifier(Possibly QR Code) for this user to be easily added to store Queues just by getting it scanned by the store |
| userName | String     | Profile Information |
| userLastName | String     | Profile Information |
| userPhone | String     | Profile Information |
| userEmail | String     | Profile Information |


### Networking

#### List of network requests by screen

- Home Screen of User
    - (Read/GET) Get all queues of a customer when a user logs in
    - (Delete) Delete a customer from a Queue

- Home Screen of Businesses
    - (Delete) Delete a customer from a Queue
    - (Delete) Delete a Queue

- Create a Queue Screen on Business Side
    - (Create/POST) Create a new Queue

- Add a Queue Screen on Customer Side
    - (Read/GET) Get the Existing Queue and add it to Customer's home page

Progress
<img src="http://g.recordit.co/7iwugD6GFa.gif"/>
