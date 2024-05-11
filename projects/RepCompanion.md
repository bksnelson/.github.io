---
layout: project
type: project
image: img/RepCompanion/uh-repcompanion.png
title: "Rep Companion: Gym Buddy Finder"
date: 2024
published: true
labels:
  - Group project
  - Javascript
  - Bootstrap
  - React
  - Meteor 
  - MongoDB
  - Uniforms
summary: "Group project gym buddy finding website."
---

Rep Companion serves as a virtual community where users can find like-minded individuals to share their fitness goals and activities. It enables users to create profiles, join event groups, and manage personal schedules. The integration of Meteor and React ensures real-time responsiveness, while MongoDB provides a flexible database structure, and Uniforms facilitate streamlined form management, enhancing the user experience and interface design. My contribution to the project was mainly focused on data management and incorporating it into the website's overall functionality.
[Rep Companion Page](https://uh-repcompanion.github.io/)

<div class="row justify-content-center">
    <img style="width: 600px" alt="" class="pe-4" src="../img/RepCompanion/home.png">
</div>


#### Database Architecture and Collections:
At the heart of the Rep Companion is MongoDB, a flexible and scalable database that supports our dynamic content and queries. MongoDB is instrumental in managing various data aspects of the platform through several collections:

- Profiles Collection: This primary collection is for storing comprehensive user data. It includes basic personal information, fitness preferences, social links, and more. This collection forms the foundation for user profiles on the platform.
- Events Collection: Manages all data related to fitness events available for users to join. This collection records information about each event, including the date, location, and description. This collection is key for users looking to engage in group fitness activities, and for event owners to manage these events effectively.
- Schedules Collection: Supports personal scheduling features, allowing users to plan and manage their fitness activities. Each entry in this collection links to user profiles, and can include recurring personal workouts, or other planned activities, providing a comprehensive view of a user's fitness agenda.
- ProfilesInterests, ProfilesTags, ProfilesEvents, ProfilesSchedules: These combined collections greatly enhance the functionality of the Profiles Collection by linking profiles to specific interests, tags (workout skill level), event participation, and schedule days, respectively. They are integral for implementing detailed and efficient search and filtration mechanisms, enabling users to find other users with shared interests or specific attributes.

Each of these collections is designed to not only store data  but to interact seamlessly with the others, such as querying for user profiles based on multiple criteria or updating event details in real-time. This architecture ensures that Rep Companion remains efficient, scalable, and capable of supporting a growing community of fitness enthusiasts.

#### Filtration of Profiles:
Filtration is a vital feature of the website, allowing users to find potential gym buddies based on shared interests or specific tags. This is primarily facilitated by the combined collections:

- ProfilesInterests: Enables users to filter potential connections based on common fitness interests.
- ProfilesTags: Allows for the categorization of profiles by skill level.
- ProfileSchedules: Enables users to find other users with the same workout days.

These collections ensure that the filtration process is both efficient and relevant, fetching data dynamically based on user queries and preferences.
<div class="row justify-content-center">
    <img width="600px" alt="" class="pe-4" src="../img/RepCompanion/profiles.png">
</div>

#### Event Finding and its Collection:
Event management is another critical aspect of the website, supported by the Events Collection. This collection records details about fitness events, including dates, locations, and descriptions. The ProfileEvents Collection is used to handle event participation, where each profile is tied to a specific event in the Event Collection. Users can find events that match their interests and the real-time capabilities of Meteor ensure that event listings and event participation are always up-to-date and responsive to user interactions.
<div class="row justify-content-center">
    <img width="600px" alt="" class="pe-4" src="../img/RepCompanion/events.png">
</div>
#### Personal Schedule and Its Collection:
The Schedules Collection underpins the personal scheduling feature, allowing users to manage their fitness activities. Each user’s schedule is personalized and includes recurring personal workouts. The ProfilesSchedules Collection keeps track of each user’s scheduled day, which is used in the profile filtration and is displayed on the user’s profile. This feature is integral to helping users plan their fitness routines effectively, ensuring they can maximize their time and commitment to fitness.
<div class="row justify-content-center">
    <img width="600px" alt="" class="pe-4" src="../img/RepCompanion/schedule.png">
</div>
#### Management of Data through Meteor Methods
Data integrity and secure interaction are maintained through Meteor methods, which handle all data operations on the server side. These methods ensure that user inputs, such as profile updates, event registrations, and schedule modifications, are processed securely and efficiently. 
