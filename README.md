# Jam Tracker

This is a Java Spring boot application for simulating backend of Jam tracker application. It simulates process of Creating new Jams, adding jam entries, rating the Jam entries and detecting jams duplicates with entry subbmission time. 


## Entities
- Jam - name, theme, startsAt, EndsAt
- Entry -> Jam - title, playUrl, submittedAt
- Rating -> Entry, score 1-5, comment, createdAt

## Relations

## Rules
- name is unique → 409. endsAt must be after startsAt → 400.
- Unknown jam → 404. Title unique within its jam → 409. No submissions outside the jam's dates → 409. submittedAt is set by the server, never by the client.
- Unknown entry → 404. score is 1 to 5 → 400.
## Endpoints

- GET     /api/jams                     a page of jams
- POST    /api/jams                     create one
- GET     /api/jams/{id}
- PUT     /api/jams/{id}                replace
- DELETE  /api/jams/{id}

- GET     /api/jams/{jamId}/entries    a page of one jam's entries
- POST    /api/jams/{jamId}/entries   create a entry for jam
- GET     /api/entries                       a page of all entries, each with its jam's name
- GET     /api/entries/{id}
- DELETE  /api/entries/{id}
- GET     /api/entries/top-rated             books ranked by average review

- GET     /api/entries/{entryId}/reviews
- POST    /api/entries/{entryId}/reviews

## Later
- teams
- tags
- voting window
- comments on ratings