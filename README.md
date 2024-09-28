# SQLmurder-mystery
Solution for the SQL Murder Mystery Game.  

Retrieve Crime Scene Report
SELECT *
FROM crime_scene_report;

Filter Crime Scenes by Type
SELECT *
FROM crime_scene_report WHERE type = "murder";

Narrow Down Crime Scenes by Date and City
SELECT *
FROM crime_scene_report WHERE type = "murder"
AND date = "20180115" AND city = "SQL City";

Explore Persons Involved
SELECT * FROM person;

Identify First Witness's Location
SELECT *
FROM person
WHERE address_street_name = "Northwestern Dr" ORDER BY address_number DESC;

Locate Second Witness by Name and Address
SELECT *
FROM person
WHERE name LIKE '%Annabel%'
AND address_street_name = "Franklin Ave";

Review Witness Interviews
SELECT *
FROM interview
WHERE person_id IN ("14887", "16371");

Check Gym Check-Ins using Clues
SELECT *
FROM get_fit_now_check_in WHERE membership_id LIKE '48Z%'
AND check_in_date = "20180109";

Verify Gender and Car Plate Number
SELECT *
FROM drivers_license WHERE gender = "male"
AND plate_number LIKE '%H42W%';

Gather Additional Details on Persons
SELECT *
FROM person
WHERE license_id IN ("423327", "664760");

Finalize Suspect Identification
SELECT *
FROM get_fit_now_member
WHERE person_id IN ("51739", "67318");

Confirm Solution in the Database
INSERT INTO solution VALUES (1, 'Jeremy Bowers'); SELECT value FROM solution;

Review The Murderer's Interview
SELECT *
FROM interview
WHERE person_id = "67318";

Identify Tesla Model S Owners
SELECT *
FROM drivers_license WHERE gender = "female"
AND hair_color = "red"
AND height BETWEEN 65 AND 67 AND car_make = "Tesla"
AND car_model = "Model S";

Retrieve Personal Details of Potential Suspects
SELECT *
FROM person
WHERE license_id IN ("202298", "291182", "918773");

Determine SQL Symphony Concert Attendees
SELECT person_id,
event_name,
COUNT(*) AS event_count
FROM facebook_event_checkin
WHERE person_id IN ("78881", "90700", "99716") GROUP BY person_id, event_name;

Confirm The Culprit
INSERT INTO solution VALUES (1, 'Miranda Priestly'); SELECT value FROM solution;
