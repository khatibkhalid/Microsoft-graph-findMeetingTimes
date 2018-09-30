# Microsoft-graph-findMeetingTimes

I was working with Microsoft Graph API lately to make some operations on users calendars, and i found that this API does not support the /findMeetingTimes endpoint in an application without a signed in user or a daemon (Client credentials grant flow), which is used to get suggestions for a meeting between an organizer and attendees based on their calendars, you just get Access denied error, as discussed on the following issue:
https://github.com/microsoftgraph/microsoft-graph-docs/issues/559

We could use microsoft outlook API which supports /findMeetingTimes endpoint in backend, but it requires creating a certificate with a private and public keys and getting client_assertion which was not possible for our PROD environment.

So i created this microservice, with an endpoint /findMeetingTimes to get free timeslots of users based on their working hours and events they have in their calendars, so we can choose a time for a meeting without worrying about our attendees if they are free or not.

all what you have to do, is to change the client credentials with your own ones : client id + client secret.

This microservice contains also endpoints to get Token, CalendarView, Events, MailboxSettings ..

If you need any informations about setting up the microservice or creating app on Azure AD, or even using Microsoft graph in other flows, we can discuss that together.
