RESTful Booker API Performance Testing with JMeter

About This Project

This is my first performance testing project using Apache JMeter.

I used JMeter to test the RESTful Booker API and check how the API works when many users send requests at the same time.

In this project, I tested the main booking API operations:

Create Token

Get Booking ID

Create Booking

Get Booking

Update Booking

Partial Update Booking

Delete Booking

Tool I Used

Apache JMeter 5.6.3

RESTful Booker API

Java

My JMeter Test Plan

My test plan has one Thread Group.

I configured it with:

Number of Users: 200

Ramp-up Time: 1 second

Loop Count: 1

Same User on Each Iteration: Enabled

This means JMeter will try to start 200 users within 1 second and each user will run the test once.

API Tests

1. Create Token

First, I create a token for authentication.

The token is needed for some booking operations.

2. Get Booking ID

I get a booking ID from the API.

I can use this booking ID in the next requests.

3. Create Booking

I send a request to create a new booking.

I check whether the API creates the booking successfully.

4. Get Booking

I use the booking ID to get the booking information.

I check whether the API returns the booking details correctly.

5. Update Booking

I update the booking information.

I check whether the booking is updated successfully.

6. Partial Update Booking

Here I update only some information of the booking instead of updating everything.

7. Delete Booking

Finally, I delete the booking.

I check whether the booking is deleted successfully.

JMeter Structure

My test plan looks like this:

Thread Group
│
├── Create Token
│   ├── Create Token
│   ├── View Results Tree
│   └── Summary Report
│
├── Get Booking ID
│   ├── Get Booking ID
│   ├── View Results Tree
│   └── Summary Report
│
├── Create Booking
│   ├── Create Booking
│   ├── View Results Tree
│   └── Summary Report
│
├── Get Booking
│   ├── Get Booking
│   ├── View Results Tree
│   └── Summary Report
│
├── Update Booking
│   ├── Update Booking
│   ├── View Results Tree
│   └── Summary Report
│
├── Partial Update Booking
│   ├── Partial Update Booking
│   ├── View Results Tree
│   └── Summary Report
│
├── Delete Booking
│   ├── Delete Booking
│   ├── View Results Tree
│   └── Summary Report
│
├── View Results Tree
└── Summary Report

How I Run the Test

From JMeter

Open Apache JMeter.

Open my .jmx file.

Check the Thread Group settings.

Click the Start button.

Check the results in Summary Report.

If I need to check a particular request, I use View Results Tree.

What I Check in the Results

After running the test, I check some basic performance information.

Average

This shows the average response time of the requests.

Minimum

This shows the fastest response time.

Maximum

This shows the slowest response time.

Throughput

This shows approximately how many requests the API can process.

Error %

This shows how many requests failed.

For example:

Average: 500 ms
Minimum: 200 ms
Maximum: 1500 ms
Error: 0%

This means the API requests took around 500 ms on average and no requests failed.

Why I Used 200 Users

I used 200 users because I wanted to see how the API behaves when many users send requests at almost the same time.

This is a simple load test.

Later, I can try different numbers of users such as:

10 users

50 users

100 users

200 users

500 users

This will help me understand how the API behaves as the number of users increases.

Project Goal

The goal of this JMeter test plan is to establish a repeatable
performance-testing process for the RESTful Booker API and identify how
the API behaves under increasing levels of concurrent traffic.
