# Project-1-_-MIST-4610


























Our Data Model 
Our data model is designed to effectively integrate, store, and analyze data that is necessary to the core operations of our clients Country Club. The model begins with the Members entity, which is the heart of this Country Club and is what provides profit and development for our client. 
The Members' entities consist of an identification number unique to each member, as well as the members first and last name, their phone number, street address, and method of payment. Each member can bring in many guests. Members can make many reservations for different events and facilities. The Guests entity outlines important information for each guest that comes to visit the country club. The entity assigns a unique ID number to each guest, as well as outlines the guest's first and last name, phone number, and address. Members and Guests form a many to many relationship, as a member can have many guests, and a guest can be connected to many members. This is portrayed by the Member_Has_Geusts entity. 

 Method of payment is crucial in understanding how the specific member is funding their country club experience and is extremely important to the profitability of the country club. A member can have one form of direct payment, however this can be changed if the member desires. This brings us to the next entity, this being Payment Methods. A payment method has a unique integer ID associated with it, as well as a name, ranging from debit and credit cards to venmo and other online transactional services. A payment method can be associated with many members. 

To efficiently and effectively organize their operations, it is important that reservations made by members are kept track of. This is why we created a reservation entity. In this entity, reservations are given a unique ID number, as well as a time and date for when the reservation is for. Each reservation occupies a single event and facility, and each reservation entry can only belong to one member. 

Next, events are what drive the country club experience for our client, and it is crucial that these events are kept organized. Our Events entity gives each event a unique identification number, as well as outlines the event name, event date, and event time. An event can belong to many different reservations made by members. Various events are also part of various different facilities, forming a many to many relationship. This is seen by the Events_has_Facilties entity.  The Facilities entity outlines facilities of the country club where various events may be held. This entity consists of a unique facility ID number, facility name, capacity of each facility, and the condition of the facility. Each facility can be a part of many different events. Furthermore, each facility can hold many reservations. A facility also has many different amenities. Amenities are part of facilities, and aid in bringing unique features to the country club, ranging from spas and gyms to swimming pools and tennis courts. The amenity entity supplies each amenity with a unique ID number and the name of the amenity itself. 

	The staff of the country club is a key part of the operations for our client. The staff entity assigns a unique ID number to each staff member, as well as their first name, last name, phone number, address, position, and salary. Each staff member can be a part of one facility, and each facility can have many staff members. This creates a one to many relationship between the two entities. 

	Finally, Membership tiers are important to assessing what the member has access to at the course and what they are paying to be a part of the country club. Membership Tiers entity gives each tier a unique ID number, as well as outlines the tier name and the cost of the tier, which is on a weekly basis of payment. Members can belong to many memberships, and Membership tiers can belong to many different members, creating a many to many relationship. This can be seen by the Members_has_MembershipTiers entity. 





































Data Dictionary 

Table 1: Members 
Column Name
Description
Data Type
Size
Format
Key
MemberID
Unique sequential number identifying each member of the golf club
INT




PK
MemberFname
First name of the member
VARCHAR
45





MemberLname
Last name of the member
VARCHAR
45




PhoneNumber
Phone number of the member
VARCHAR
45




Address
Street address of the member
VARCHAR
45




PaymentMethodID
FK - Payment_Methods; identifies which payment methods are used by the member
INT




FK - Payment_Methods







Table 2: Reservations 
Column Name
Description
Data Type
Size
Format
Key
ReservationID
Unique sequential number identifying the reservation
INT




PK
ReservationDate
Date of the reservation
DATE


mm-dd-yyyy


ReservationTime
Time of the reservation on the reservation date
DATETIME
5
hh:mi:ss


EventID
FK - Events; identifies which event the reservation is associated with
INT




FK - Events
Facility ID
FK - Facilities; identifies which golf club facility the reservation is associated with
INT




FK - Facilities
MemberID
FK - Members; Identifies which member of the golf club the reservation is associated with 
INT




FK - Members


Table 3: Payment Methods
Column Name
Description
Data Type
Size
Format
Key
PaymentMethodID
Unique sequential number identifying the payment method
INT




PK
MethodName
Name of the payment method 
VARCHAR
45







Table 4: Guests
Column Name
Description
Data Type
Size
Format
Key
GuestID
Unique sequential number identifying the guest
INT




PK
GuestFname
First name of the guest
VARCHAR
45




GuestLname
Last name of the guest
VARCHAR
45




GuestPhoneNumber
Phone number of the guest
VARCHAR
45




GuestAddress
Home address of the guest
VARCHAR
45












Table 5:Events
Column Name
Description
Data Type
Size
Format
Key
EventID
Unique sequential number identifying the event
INT




PK
EventName
Indicates the name of the event
VARCHAR
45




EventDate
Indicates the date of the event 
DATE


mm-dd-yyyy


EventTime
Indicates the time of the event on the date of the event
DATETIME


hh:mi:ss





Table 6: Facilities
Column Name
Description
Data Type
Size
Format
Key
FacilityID
Unique sequential number identifying the facility of the golf club
INT




PK






FacilityName
The name of the facility
VARCHAR
45




Capacity
The maximum number of people (or the capacity) that the facility can hold 
VARCHAR
45




Condition
A brief description of the condition of the facility including recent and planned renovations and issues to be addressed
VARCHAR
45







Table 7: Amenities 
Column Name
Description
Data Type
Size
Format
Key
AmenityID
Unique sequential number identifying the amenity item offered by the golf club
INT




PK
AmenityName
Name of the amenity offered by the golf club
VARCHAR
45




FacilityID
FK - Facilities; indicates which facility is associated with the amenity 






FK - Facilities

