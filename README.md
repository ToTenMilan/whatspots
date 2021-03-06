# [WHATSPOTS](http://whatspots.herokuapp.com/)

* is an app where skaters from Wroclaw can come and leave a note, where they will be skating today. Note can be left after picking one of the spots ie. 'Zajezdnia', 'Pomorska', 'Renoma' etc.
* Everyone who will come here can check who will hit the exact spot today and also leave a note for others.
* To preserve mess, all notes will be deleted every day at midnight to prepare a fresh new wall for new notes for upcoming day.
* This app should replace groups on facebook, calling and texting to each other to set up at particular spot and encourage skaters to go out more spontaneously.

## Dev diary

* Spots feature has been added
* Comments under spots has been added. For now, I decided to not create `User` model. Logging in just to leave a super short message is not needed at the moment. Instead `Comment` model has `author` column.

* Comments are now deleting automatically every day at midnight with rake task run in background on [heroku scheduler](https://devcenter.heroku.com/articles/scheduler) addon.

* Styling and responsiveness with bootstrap has been added, unnessesary links removed, but create/edit routes are still available to everyone.

* Validations has been added to comments, and UX on show page has been improved little bit, that means if no comments are left for a particular spot than user is informed about that.

* Footer partial has been added.

* Much of styling has been added to almost every part of the page. Ui and UX has also been improved in few places. It looks now little bit more professional.

* Show page modified to be responsive. Some CSS effects added at spots/index view.

* Devise gem has been added, and I've registered to be an admin. Then Devise's registerable module has been turned off so only I can log in and add new spots. That is temporary. In the long run, users should be able to log in and add their spots to some kind of "waiting room" to be accepted by the others and even add new cities.

* Photos on the index page now shows total number of comments left under this photo. This eliminates the need to click on every spot to check if something is there. This should improve UX.
