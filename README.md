# ExpectedBehaviour #

This repo contains the [API definition file](https://github.com/CampFireManager/ExpectedBehaviour/blob/master/apiary.apib) and a set of expected workflows.

The API is defined using [apiary.io](http://apiary.io) and can be tested using their [testing API endpoint](http://campfiremanager.apiary.io)

The expected behaviour is documented in the Wiki. These behaviours should be described using [BDD](http://en.wikipedia.org/wiki/Behavior-driven_development#Behavioral_specifications) style language which can then be slightly re-tooled to create unit tests.

An example of this is:

Story: Access the timetable

In order to participate in the event
As an attendee
I want to be able to see what talks are occurring during the day

Scenario 1: Accessing the timetable without javascript
Given I have not visited the timetable before
And I have a device which does not support javascript
When I visit the event URL
Then I should receive an HTML page with the framework of the timetable and any relevant information to populate that grid

Scenario 2: Accessing the timetable
Given I have not visited the timetable before
When I visit the event URL
Then I should receive an HTML page with the framework of the timetable and any relevant information to populate that grid

Scenario 3: Refreshing the timetable
Given I have visited the timetable previously
And the page is cached
When I visit the event URL
Then the timetable page should request updated talk data and updated presenter details
