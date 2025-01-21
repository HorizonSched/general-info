# Software Requirements Specification (SRS)

## Table of Contents
1. [User Management](#user-management)
   - [Profile](#profile-page)
   - [Registration](#register-page)
   - [Login](#login-page)
2. [Core Features](#core-features)
   - [Events & Offers](#events--offers-management-page)
   - [Admin Panel](#admin-panel-page)
   - [Notifications](#notification-page)
3. [System Configuration](#system-configuration)
   - [Settings](#setting-page)
     - [Branding & Contact](#branding--contact)
     - [User Package & Plan](#user-package--plan)
     - [Payment Details](#payment-details)
     - [Venues Management](#venues-management)
     - [Branch Management](#branch-management)
     - [Labels Management](#labels-management)
4. [Social Features](#social-features)
   - [Open Matches](#open-matches-page)
   - [Chat](#chat-page)
5. [Booking System](#booking-system)
   - [Free Slots](#free-slots-page)
   - [Booking Management](#booking-management)

---

# User Management

## Profile Page

### Profile Information
- **Basic Details:**
  - **Name**: User's full name
  - **Phone**: User's phone number
  - **Email**: User's email address
  - **Date of Birth**: User's date of birth
  - **Profile Image**: URL or path to user's profile image

- **User Status:**
  - **Labels**: Associated labels (e.g., "LevelD", "Beginner", "Girls")
  - **Role**: User role (e.g., "admin", "user")
  - **Last Login**: Timestamp of last login

- **Preferences & History:**
  - **Booking List**: Array of booking IDs (with delete/modify capabilities)
  - **Number of Bookings**: Total bookings count

### Profile Management
- **Edit Options:**
  - Profile photo modification
  - Name update
  - Account deletion

## Register Page

### Registration Fields
- **Required Information:**
  - Mobile number
  - Password
  - Confirm password
  - Full name
  - Date of birth
  - Profile image

### Process Flow
1. **Error Handling:**
   - Mobile number duplicate check
   - Validation messages

2. **Post-Registration:**
   - Profile image selection
   - Name confirmation

## Login Page

### Authentication Methods
- **Standard Login:**
  - Mobile number
  - Password
- **Alternative Login if forgot the password:**
  - OTP (One-Time Password)

### Additional Options
- **Navigation Links:**
  - New account creation
  - Password recovery

---

# Core Features

## Events & Offers Management Page

### Post Creation
- **Content Types:**
  - Markdown text formatting
  - Image uploads
  - Event/Offer details

### Event/Offer Details
- **Basic Information:**
  - Type (offer/event)
  - Title
  - Start/End dates
  - Description
  - Images
  - Booking links

- **References:**
  - Branch Name
  - Venue Name
  - Creator Name

### Visibility & Notifications
- **Access Levels:**
  - Admin managementso he can delete notification that sent to users
  - User view access only
- **Notification System:**
  - Real-time updates
  - Action links

## Admin Panel Page

### Dashboard Overview
- **Statistics:**
  - Total bookings
  - Total cancellations
  - Active users

### Bookings Management
- **Booking History:**
  - Past bookings(bookings, cancellations, modifications)
  - Filter options (date, user, venue)

- **Booking Alerts:**
  - Call alerts for no bookings
  - Empty slot notifications

### User Management
- **User List:**
  - All users
  - Blacklist

- **User Filtering:**
  - Name
  - Tags
  - Preferred times

### Analytics & Reporting
- **Top Bookers:**
  - Users with most bookings

- **Admin Booking History:**
  - Top admin bookers

## Notification Page

### Notification System
- **User Notifications:**
  - Empty slot notifications
  - Booking updates

- **Admin Notifications:**
  - Cancellation alerts
  - Booking updates

- **Shared Notifications:**
  - Offers
  - Events

---

# System Configuration

## Setting Page

### Branding & Contact
- **Logo:**
  - Display logo
- **Brand Colors:**
  - Use main colors
- **Contact Number:**
  - Display contact number

### User Package & Plan
- **User's Plan:**
  - Display current plan name
- **Venue and branches Access:**
  - List accessible venues and branches for the user

### Payment Details
- **Payment History:**
  - Display past payments
- **Upcoming Payments:**
  - Display scheduled payments
- **Payment Methods:**
  - List available methods

### Branch Management
- **Branch Information:**
  - Name
  - Location on Map (latitude/longitude)
  - Address
  - Contact Number
  - Opening Hours
  - Image
  - Manager (admin foreign key)
  - IsActive (Switch so admin can hold bookings in venuw if it has been closed or making enhancements or installment)
  - Venues (array of venue IDs)

### Venues Management
- **Venue Information:**
  - Name
  - Branch ID
  - Location
  - Contact Number
  - Opening Hours
  - Facilities
  - Capacity
  - Price Per Hour
  - IsActive
  - Image

### Labels Management
#### User Labels
- **Labels:**
  - User categorization (e.g., "LevelD", "Beginner", "Girls")
  - Unique ID and name

#### Booking Labels
- **Booking Label Information:**
  - Name (e.g., "Offer", "Instapay", "didn't come")
  - Color code

#### Booking Assurance Labels
- **Booking Assurance Label Information:**
  - Name (e.g., "GuaranteedSlot", "FlexibleCancellation")
  - SVG Icon can be shown in the main page beside the holder name to show to the admin the assurance of the booking

 Candidate can can import the bookings list and users list if it has predefined format we tell him (download sample) that the DB accepts and 


---

# Social Features

## Open Matches Page

### Open Matches
- **Match Details:**
  - Player names
  - Time & date

- **Booking Information:**
  - Venue ID
  - Branch ID
  - Players with there images and names if no images chosen show the frist letter of the name in the image placeholder
  - Status its fullfield or not completed yet so users can join

## Chat Page

### Live Chat
- **User Access:**
  - All users

- **Free Slot Notifications:**
  - Automatic messages by the system to notify users about free slots

- **Message Details:**
  - Content
  - Sender ID
  - Sender name
  - Sender role
  - Is system message? 
  - Link

---

# Booking System

## Free Slots Page

### Slot Color Indications
- **Main Theme Color:**
  - Normal bookings
- **Purple:**
  - Academy bookings
- **Green:**
  - Offer-based bookings
- **Orange:**
  - Instapay bookings
- **Dark Black:**
  - No-shows
- **Pink & Sky Blue:**
  - Funday bookings

### Booking Management
- **Booking Information:**
  - User ID
  - Venue ID
  - Branch ID
  - Start/End dates
  - Status
  - Amount
  - Payment method
  - Is repetitive
  - Labels
  - For each booking we should see the time that this booking took this booking lable (Lables od Assurance)
  - Created at
  - Updated at
  - createdFromWeb?


## Booking Process
### Admin Booking Process
- **Time & Date :**
  - Select time and date
- **User Selection:**`
  - Select user from list 
- **New Account Creation:**
  - Quick creation using name and phone number
#### User Search & Filtering
- **Search:**
  - Name
  - Phone number

- **Filtering:**
  - Tags (e.g., "LevelD", "Beginner", "Girls")
  - Preferred times

---
### User Booking Process
- **Time & Date :**
  - Select time and date
-  **Confirm Booking Button :**
  - Click to confirm booking


## Main Pages & Features Page
- **Profile:**
  - Accessible to all users

- **Settings:**
  - Exclusive to admins

- **Chat:**
  - Accessible to all users

- **Open Matches:**
  - Visible and accessible to all users

- **Admin Panel:**
  - Exclusive to admins

- **Notifications Button:**
  - Displays unread notifications

- **Logout Button:**
  - Visible logout option
