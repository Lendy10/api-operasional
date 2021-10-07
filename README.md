# api-operasional
Contains user documentation on how to use SOFIA API

SOFIA is a college integrated educational system built by Department of Physics, Universitas Airlangga. Universaly, this system is ready to be scaled both horizontally and vertically to accomodate every single events that take place on college environment. By helicopter view, SOFIA facilitates 3 objectives: Teaching, Audit, and Student Affair.

There are full documentations for developers for this particular project, but because of the sensitivity of the data we can't publish it publicly, otherwise if you are interested on our system you may contact us via available social media. We are very pleased to be able to work together. In this document, we are going to explain the usage of SOFIA API for presence recapitulation, extended document might be published in the future.

<h1>Registration</h1>

<h2>HTTP Request</h2>

...php

POST https://operasional.fisika.fst.unair.ac.id/api/register

...

<h2>Request Body</h2>

...php
{
    "username": "string",
    "email": "email",
    "password": "{your password}"
}
...



