
---

### 1. **User-Related Models**

#### 1.1. **Profile Model** (Core User Information)
```json
{
  "Id": "string",                      // Unique identifier for the user
  "Name": "string",                    // Name of the user
  "Phone": "string",                   // Phone number of the user
  "Password": "string",                // Password of the user
  "CreatedAt": "date",                 // Date when the user account was created
  "DateOfBirth": "date",               // Date of birth of the user
  "Image": "string",                   // URL or path to the user's profile image
  "NumberOfBookings": "number",        // Number of bookings made by the user
  "Level": "string",                   // User level (e.g., "beginner", "advanced")
  "Labels": ["string"],                // Labels associated with the user 
  "Role": "string",                    // Role of the user (e.g., "admin", "user")
  "BookingList": ["string"],           // Array of booking IDs made by the user
  "Email": "string",                   // Email address of the user
  "PreferredVenues": ["string"],       // Array of preferred venue IDs
  "LastLogin": "date"                  // Last login timestamp
}
```

**Relationships:**
- `BookingList` → Links to the **Booking Model**.
- `PreferredVenues` → Links to the **Venue Model**.

#### 1.2. **Register Model**
```json
{
  "MobileNumber": "string",            // User's mobile number
  "Password": "string",                // User's password
  "ConfirmPassword": "string",         // Confirmation of the password
  "Email": "string",                   // User's email address
  "Name": "string",                    // User's name
  "DateOfBirth": "date",               // User's date of birth
  "ProfileImage": "string"             // URL or path to the user's profile image
}
```

#### 1.3. **Login Model**
```json
{
  "MobileNumber": "string",            // User's mobile number
  "Password": "string",                 // User's password
  "otp":"number"                       // otp
}
```

#### 1.4. **Users Labels**
```json
{
  "LabelName": "string",               // Ex: LevelD, LevelC, Beginner, Girls, NonFootballEnjoyer, OfferGuy, SundayPreferer
  "id": "number"                       // Ex: 1, 2, 3
}
```

### 2. **Core Business Models**

#### 2.1. **Branch Model**
```json
{
  "Id": "string",                      // Unique identifier for the branch
  "Name": "string",                    // Name of the branch
  "LocationOnMap": {                   // Location coordinates
    "latitude": "number",
    "longitude": "number"
  },
  "Address": "string",                 // Physical address of the branch
  "Image": "string",                   // URL or path to the branch image
  "ContactNumber": "string",           // Main contact number for the branch
  "Email": "string",                   // Branch email address
  "OpeningHours": {                    // Branch operating hours
    "weekdays": "string",
    "weekends": "string",
    "holidays": "string"
  },
  "Venues": ["string"],                // Array of venue IDs belonging to this branch
  "Manager": "string",                 // Foreign key to the user (admin) who manages this branch
  "IsActive": "boolean",               // Whether the branch is currently active
  "CreatedAt": "date",                // When the branch was created
  "UpdatedAt": "date"                 // Last update timestamp
}
```

**Relationships:**
- `Venues` → Links to multiple **Venue Models**
- `Manager` → Links to the **User Model** (admin)

#### 2.2. **Venue Model**
```json
{
  "Id": "string",                      // Unique identifier for the venue
  "Name": "string",                    // Name of the venue
  "BranchId": "string",                // Foreign key to the branch this venue belongs to
  "Location": "string",                // Specific location within the branch
  "ContactNumber": "string",           // Contact number for the venue
  "OpeningHours": "string",            // Opening hours of the venue
  "Facilities": ["string"],            // Array of facilities available at the venue
  "Capacity": "number",                // Maximum capacity of the venue
  "IsActive": "boolean",               // Whether the venue is active
  "Image": "string",                   // URL or path to the venue image
  "PricePerHour": "number"             // Standard price per hour for this venue
}
```

#### 2.3. **Booking Model**
```json
{
  "Id": "string",                      // Unique identifier for the booking
  "UserId": "string",                  // Foreign key to the user who made the booking
  "VenueId": "string",                 // Foreign key to the venue where the booking is made
  "BranchId": "string",                // Foreign key to the branch where the booking is made
  "DateOfStart": "date",               // Start date of the booking
  "DateOfEnd": "date",                 // End date of the booking
  "Status": "string",                  // Status of the booking (e.g., "active", "canceled")
  "AmountOfMoney": "number",           // Amount of money associated with the booking
  "PaymentMethod": "string",           // Payment method used (e.g., "credit card", "Instapay")
  "IsRepetitive": "boolean",           // Whether the booking is repetitive
  "Labels": ["string"],                // Labels associated with the booking (e.g., "academy", "offer")
  "CreatedAt": "date",                 // Date when the booking was created
  "UpdatedAt": "date"                  // Last updated timestamp
}
```

**Relationships:**
- `UserId` → Links to the **User Model**.
- `VenueId` → Links to the **Venue Model**.
- `BranchId` → Links to the **Branch Model**.

#### 2.4. **Events/Offers Model**
```json
{
  "Id": "string",                      // Unique identifier for the event/offer
  "Type": "string",                    // Type of the post (e.g., "offer", "event")
  "Title": "string",                   // Title of the event/offer
  "DateOfStarting": "date",            // Start date of the event/offer
  "DateOfEnding": "date",              // End date of the event/offer
  "CreatedAt": "date",                 // Date when the event/offer was created
  "Content": "string",                 // Content or description of the event/offer
  "Image": "string",                   // URL or path to the image associated with the event/offer
  "LinkToBook": "string",              // Link to book or RSVP for the event/offer
  "BranchId": "string",                // Foreign key to the branch where the event/offer is hosted
  "BranchName": "string",              // Name of the branch where the event/offer is hosted
  "VenueId": "string",                 // Foreign key to the venue where the event/offer is hosted
  "CreatedBy": "string"                // Foreign key to the user/admin who created the event/offer
}
```
**Relationships:**
- `VenueId` → Links to the **Venue Model**.
- `BranchId` → Links to the **Branch Model**.
- `CreatedBy` → Links to the **User Model** (admin or user who created the event/offer).

#### 2.5. **Open Matches Model**
```json
{
  "Id": "string",                      // Unique identifier for the match
  "Date": "date",                      // Date of the open match booking
  "VenueId": "string",                 // Foreign key to the venue where the match will take place
  "BranchId": "string",                // Foreign key to the branch where the match will take place
  "Players": "array",                  // Array of player IDs participating in the match
  "IsCompleted": "boolean",            // Whether the match has been completed
  "BookingId": "string",               // Foreign key to the booking associated with the match
  "CreatedBy": "string",               // Foreign key to the user/admin who created the match
  "Status": "string",                  // Status of the match (e.g., "scheduled", "in progress", "fulfilled")
  "CurrentPlayers": "array"            // Current number of players joined
}
```

**Relationships:**
- `VenueId` → Links to the **Venue Model**.
- `BranchId` → Links to the **Branch Model**.
- `Players` → Links to the **User Model** (array of player IDs).
- `BookingId` → Links to the **Booking Model**.
- `CreatedBy` → Links to the **User Model**.

### 3. **Supporting Models**

#### 3.1. **Notification Model**
```json
{
  "Id": "string",                      // Unique identifier for the notification
  "Content": "string",                 // Content of the notification
  "CreatedAt": "date",                 // Date when the notification was created
  "Type": "string",                    // Type of notification (e.g., "cancellation", "new booking")
  "Icon": "string",                    // Icon associated with the notification type
  "IsRead": "boolean",                 // Whether the notification has been read
  "Link": "string",                    // Link associated with the notification (e.g., to book a slot)
  "UserId": "string",                  // Foreign key to the user who receives the notification
  "RelatedBookingId": "string",        // Foreign key to the related booking (if applicable)
  "RelatedEventId": "string"           // Foreign key to the related event/offer (if applicable)
}
```

**Relationships:**
- `UserId` → Links to the **User Model**.
- `RelatedBookingId` → Links to the **Booking Model**.
- `RelatedEventId` → Links to the **Events/Offers Model**.

#### 3.2. **Chat Message Model**
```json
{
  "Id": "string",                      // Unique identifier for the message
  "Content": "string",                 // Content of the message
  "Time": "date",                      // Time when the message was sent
  "SenderId": "string",                // Foreign key to the sender (user or admin)
  "SenderName": "string",              // Name of the sender
  "SenderRole": "string",              // Role of the sender (e.g., "admin", "user")
  "IsSystemMessage": "boolean",        // Whether the message is a system-generated message
  "Link": "string"                     // Link included in the message (e.g., to book a slot)
}
```

**Relationships:**
- `SenderId` → Links to the **User Model**.

#### 3.3. **Free Slots Page Model**
```json
{
  "BookingId": "string",               // Unique identifier for the booking
  "DateOfStart": "date",               // Start date of the booking
  "DateOfEnd": "date",                 // End date of the booking
  "HolderId": "string",                // Foreign key to the user who holds the booking
  "HolderName": "string",              // Name of the booking holder
  "Status": "string",                  // Status of the booking (e.g., "active", "canceled")
  "LabelsIDs": ["string"],             // Labels associated with the booking (e.g., "academy", "offer")
  "VenueId": "string",                 // Foreign key to the venue associated with the booking
  "AmountOfMoney": "number",           // Amount of money associated with the booking
  "AssuranceLabelsIDs": ["string"],    // Assurance labels (e.g., "guaranteed", "tentative")
  "NumberOfSessionsInMonth": "number", // Number of sessions in the month (for academy bookings)
  "IsBookingFull": "boolean",          // Whether the booking is full (for open matches)
  "IsRepetitive": "boolean",           // Whether the booking is repetitive
  "DayOfWeek": "string"                // Day of the week for the booking
}
```

**Relationships:**
- `HolderId` → Links to the **User Model**.
- `VenueId` → Links to the **Venue Model**.
- `AssuranceLabelsIDs` → Links to the **Booking Assurance Labels**.
- `LabelsIDs` → Links to the **Booking Labels**.

### 4. **Administrative Models**

#### 4.1. **Admin Panel Model**
```json
{
  "Id": "string",                      // Unique identifier for the admin panel entry
  "Overview": {
    "TotalBookings": "number",         // Total number of bookings across all branches
    "TotalCancellations": "number",    // Total number of canceled bookings
    "TotalRevenue": "number",          // Total revenue across all branches
    "ActiveUsers": "number"            // Number of active users this month
  },
  "BookingStatistics": {
    "Daily": {
      "Labels": ["string"],            // Array of dates (e.g., ["2025-01-19", "2025-01-20"])
      "Bookings": ["number"],          // Array of booking counts per day
      "Revenue": ["number"],           // Array of revenue per day
      "Cancellations": ["number"]      // Array of cancellations per day
    },
    "Weekly": {
      "Labels": ["string"],            // Array of week ranges (e.g., ["Week 1", "Week 2"])
      "Bookings": ["number"],          // Array of booking counts per week
      "Revenue": ["number"],           // Array of revenue per week
      "Cancellations": ["number"]      // Array of cancellations per week
    },
    "Monthly": {
      "Labels": ["string"],            // Array of months (e.g., ["Jan 2025", "Feb 2025"])
      "Bookings": ["number"],          // Array of booking counts per month
      "Revenue": ["number"],           // Array of revenue per month
      "Cancellations": ["number"]      // Array of cancellations per month
    }
  },
  "VenuePerformance": {
    "MostBooked": {
      "VenueId": "string",             // Foreign key to the most booked venue
      "BookingCount": "number",        // Number of bookings for this venue
      "Revenue": "number"              // Revenue generated by this venue
    },
    "VenueUtilization": [              // Array of venue utilization data
      {
        "VenueId": "string",           // Foreign key to venue
        "UtilizationRate": "number",   // Percentage of time venue is booked
        "PeakHours": ["string"],       // Array of peak booking hours
        "AverageBookingDuration": "number" // Average duration of bookings in hours
      }
    ]
  },
  "UserAnalytics": {
    "TopBookers": [                    // Array of top booking users
      {
        "UserId": "string",            // Foreign key to user
        "BookingCount": "number",      // Number of bookings made
        "TotalSpent": "number"         // Total amount spent
      }
    ],
    "UserCategories": {                // Distribution of user types
      "Regular": "number",             // Count of regular users
      "VIP": "number",                 // Count of VIP users
      "New": "number"                  // Count of new users this month
    }
  },
  "AcademyStatistics": {
    "SessionsThisMonth": "number",     // Number of academy sessions this month
    "ActiveStudents": "number",        // Number of active academy students
    "RevenueBreakdown": {
      "Labels": ["string"],            // Array of academy programs
      "Revenue": ["number"]            // Revenue per program
    },
    "AttendanceRate": "number"         // Average attendance rate for academy sessions
  },
  "RecentActivities": [                // Array of recent activities
    {
      "activityType": "string",        // Type of activity (e.g., "booking", "cancellation")
      "timestamp": "date",             // When the activity occurred
      "details": "string",             // Additional details about the activity
      "userId": "string",              // Foreign key to user who performed the activity
      "venueId": "string",             // Related venue if applicable
      "amount": "number"               // Related amount if applicable
    }
  ],
  "LastUpdated": "date"                // Last time statistics were updated
}
```

**Relationships:**
- `Overview` → Links to the **Overview Model**.
- `BookingStatistics` → Links to the **Booking Statistics Model**.
- `VenuePerformance` → Links to the **Venue Performance Model**.
- `UserAnalytics` → Links to the **User Analytics Model**.
- `AcademyStatistics` → Links to the **Academy Statistics Model**.
**Chart Types Supported:**
1. Line Charts:
   - Booking trends over time
   - Revenue trends over time
   - Cancellation trends over time

2. Bar Charts:
   - Venue performance comparison
   - Admin performance comparison
   - Bookings by time of day

3. Pie Charts:
   - Distribution of bookings across venues
   - Revenue distribution

4. Heat Map:
   - Popular booking hours
   - Peak days visualization

5. Timeline:
   - Recent activities visualization

**Key Visualization Features:**
- All arrays are synchronized for X-Y plotting
- Time-series data for trend analysis
- Comparative data for bar charts
- Hierarchical data for drill-down charts

### 5. **Label and Classification Models**

#### 5.1. **Booking Labels**
```json
{
  "id": "number",                      // Unique identifier for the label (Ex: 1, 2, 3)
  "name": "string",                    // Name of the label (Ex: "Offer", "instapay", "didn't come")
  "color": "string"                    // Color code for the label (Ex: "#FF5733", "#33FF57", "#3357FF")
}
```

#### 5.2. **Booking Assurance Labels**
```json
{
  "id": "number",                      // Unique identifier for the assurance label (Ex: 101, 102, 103)
  "name": "string",                    // Name of the assurance label (Ex: "GuaranteedSlot", "FlexibleCancellation", "PrioritySupport")
  "SVGIcon": "string"                  // SVG icon associated with the label (Ex: "<svg>...</svg>", "icon-guaranteed.svg")
}
```

### 6. **Tracking and History Models**

#### 6.1. **History Logs**
```json
{
  "bookingID": "number",                         // (Ex: 101, 102, 103)
  "HolderName": "string",                        // Name of the The Holder whose the booking is with his name.
  "HowMakedThisChange": "string",                // Name of the The Persone made the change , Admin or Holder
  "createdAt": "string",                         // timestamp
  "typeOfChange": "string",                      // new , update , cancel
  "CauseOfCancelation":"string"                  // if cancelation happend what is the cause [optional]
}
```

---

### Summary of Relationships:

#### Core Model Relationships:

1. **Branch Model** (Core Business Entity):
   - Contains → Multiple Venues (one-to-many)
   - Has → One Manager (one-to-one with User/Admin)
   - Referenced by → Events/Offers (one-to-many)
   - Tracked in → History (one-to-many)
   - Has → Location and Operating Hours
   - Manages → Revenue and Performance Stats
   - Tracks → Academy Sessions (one-to-many)

2. **User Model** (Central Entity):
   - Creates → Bookings (one-to-many)
   - Receives → Notifications (one-to-many)
   - Participates in → Open Matches (many-to-many)
   - Has → One Profile (one-to-one)
   - Creates/Participates in → Events/Offers (many-to-many)
   - Can Manage → Branches (one-to-many, if admin)
   - Tracked in → History (one-to-many)
   - Has → User Labels (many-to-many)
   - Sends → Chat Messages (one-to-many)
   - Requires → Authentication (OTP/Password)

3. **Venue Model** (Business Asset):
   - Belongs to → One Branch (many-to-one)
   - Has → Multiple Bookings (one-to-many)
   - Hosts → Events/Offers (one-to-many)
   - Hosts → Open Matches (one-to-many)
   - Tracked in → History (one-to-many)
   - Has → Facilities and Capacity
   - Has → Operating Hours
   - Maintains → Price Information
   - Shows in → Free Slots (one-to-many)

4. **Booking Model** (Transaction):
   - Made by → One User (many-to-one)
   - Uses → One Venue (many-to-one)
   - Associated with → One Branch (through Venue)
   - Generates → Notifications (one-to-many)
   - Tracked in → History (one-to-many)
   - Has → Booking Labels (many-to-many)
   - Has → Payment Information
   - Can be → Repetitive (recurring bookings)
   - Links to → Open Matches (one-to-one, optional)

5. **Events/Offers Model** (Business Activity):
   - Hosted at → One Venue (many-to-one)
   - Belongs to → One Branch (many-to-one)
   - Created by → One User (many-to-one)
   - Has → Multiple Participants (many-to-many with Users)
   - Tracked in → History (one-to-many)
   - Generates → Notifications (one-to-many)
   - Has → Booking Link (optional)

6. **History Model** (Tracking System):
   - Tracks → User Activities (many-to-one)
   - Tracks → Branch Performance (many-to-one)
   - Tracks → Venue Usage (many-to-one)
   - Tracks → Booking Records (many-to-one)
   - Tracks → Event Participation (many-to-one)
   - Maintains → Audit Trail
   - Supports → Analytics and Reporting
   - Records → Cancellation Causes

#### Supporting Model Relationships:

7. **Notification Model**:
   - Belongs to → One User (many-to-one)
   - Can Reference → Bookings (many-to-one)
   - Can Reference → Events (many-to-one)
   - Has → Type and Icon
   - Contains → Action Links

8. **Admin Panel Model**:
   - Aggregates → Branch Statistics
   - Monitors → Venue Performance
   - Tracks → User Analytics
   - Manages → Academy Statistics
   - Records → Recent Activities
   - Provides → Revenue Reports
   - Analyzes → Booking Patterns
   - Tracks → User Categories

9. **Labels Models**:
   - User Labels → Applied to Users (many-to-many)
   - Booking Labels → Applied to Bookings (many-to-many)
   - Booking Assurance Labels → Applied to Bookings (many-to-many)
