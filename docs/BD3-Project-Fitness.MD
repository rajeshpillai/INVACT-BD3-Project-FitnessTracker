.

Delete an activity by its ID.

Delete all activities of a specific type.

Data Structure

We will use the following initial data structure for our fitness tracker:

let activities = [
  { activityId: 1, type: 'Running', duration: 30, caloriesBurned: 300 },
  { activityId: 2, type: 'Swimming', duration: 45, caloriesBurned: 400 },
  { activityId: 3, type: 'Cycling', duration: 60, caloriesBurned: 500 }
];


Note: Don’t forget to add:

let cors = require('cors');

app.use(cors());


Endpoint 1: Add an Activity

Objective: Add a new activity to the tracker.

Query Parameters:

activityId (integer)

type (string)

duration (integer)

caloriesBurned (integer)

Tasks: Implement a function to push a new activity to the activities array.

API Call:

<http://localhost:3000/activities/add?activityId=4&type=Walking&duration=20&caloriesBurned=150>


Expected Output:

{
        activities: [
          { 'activityId': 1, 'type': 'Running', 'duration': 30, 'caloriesBurned': 300 },
          { 'activityId': 2, 'type': 'Swimming', 'duration': 45, 'caloriesBurned': 400},
          { 'activityId': 3, 'type': 'Cycling', 'duration': 60, 'caloriesBurned': 500 },
          { 'activityId': 4, 'type': 'Walking', 'duration': 20, 'caloriesBurned': 150 }
        ]
}


Endpoint 2: Sort Activities by Duration

Objective: Sort activities by their duration in ascending order.

Query Parameters: None

Tasks: Implement a function to sort the activities array by duration.

API Call:

<http://localhost:3000/activities/sort-by-duration>


Expected Output:

{
        activities: [
          { 'activityId': 1, 'type': 'Running', 'duration': 30, 'caloriesBurned': 300 },
          { 'activityId': 2, 'type': 'Swimming', 'duration': 45, 'caloriesBurned': 400},
          { 'activityId': 3, 'type': 'Cycling', 'duration': 60, 'caloriesBurned': 500 }
        ]
}


Endpoint 3: Filter Activities by Type

Objective: Filter activities by their type.

Query Parameters:

type (string)

Tasks: Implement a function to filter the activities array by type.

API Call:

<http://localhost:3000/activities/filter-by-type?type=Running>


Expected Output:

{
        activities: [
   { 'activityId': 1, 'type': 'Running', 'duration': 30, 'caloriesBurned': 300 }
        ]
}


Endpoint 4: Calculate Total Calories Burned

Objective: Calculate the total calories burned for all activities.

Query Parameters: None

Tasks: Implement a function to sum the total calories burned for all activities.

API Call:

<http://localhost:3000/activities/total-calories>


Expected Output:

{ 'totalCaloriesBurned': 1200 }


Endpoint 5: Update Activity Duration by ID

Objective: Update the duration of an activity identified by its ID.

Query Parameters:

activityId (integer)

duration (integer)

Tasks: Implement a function to find and update the duration of an activity in the activities array.

API Call:

<http://localhost:3000/activities/update-duration?activityId=1&duration=35>


Expected Output:

{
        activities: [
          { 'activityId': 1, 'type': 'Running', 'duration': 35, 'caloriesBurned': 300 },
          { 'activityId': 2, 'type': 'Swimming', 'duration': 45, 'caloriesBurned': 400 },
          { 'activityId': 3, 'type': 'Cycling', 'duration': 60, 'caloriesBurned': 500 },
        ]
}


Endpoint 6: Delete Activity by ID

Objective: Delete an activity from the tracker by its ID.

Query Parameters:

activityId (integer)

Tasks: Implement a function to filter out an activity from the activities array by its ID.

API Call:

<http://localhost:3000/activities/delete?activityId=2>


Expected Output:

{
        activities: [
  { 'activityId': 1, 'type': 'Running', 'duration': 30, 'caloriesBurned': 300 },
  { 'activityId': 3, 'type': 'Cycling', 'duration': 60, 'caloriesBurned': 500 },
        ]
}


Endpoint 7: Delete Activities by Type

Objective: Delete all activities of a specific type from the tracker.

Query Parameters:

type (string)

Tasks: Implement a function to filter out all activities of a specific type from the activities array.

API Call:

<http://localhost:3000/activities/delete-by-type?type=Running>


Expected Output:

{
        activities: [
  { 'activityId': 2, 'type': 'Swimming', 'duration': 45, 'caloriesBurned': 400 },
  { 'activityId': 3, 'type': 'Cycling', 'duration': 60, 'caloriesBurned': 500 }
        ]
}


Summary

In this lesson, you will implement a series of endpoints to manage a fitness tracker. You will:

Add activities to the tracker using the GET /activities/add endpoint.

Sort activities by duration using the GET /activities/sort-by-duration endpoint.

Filter activities by type using the GET /activities/filter-by-type endpoint.

Calculate the total calories burned using the GET /activities/total-calories endpoint.

Update the duration of an activity using the GET /activities/update-duration endpoint.

Delete an activity by ID using the GET /activities/delete endpoint.

Delete activities by type using the GET /activities/delete-by-type endpoint.

By the end of this lesson, you should be comfortable performing basic CRUD operations and sorting/filtering activities based on their properties. Good luck and happy coding!