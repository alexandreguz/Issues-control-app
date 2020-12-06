# Issues-control-app

This project was copied from :https://medium.com/codingthesmartway-com-blog/pure-javascript-building-a-real-world-application-from-scratch-5213591cfcd6
for the purpose of learnig how to add and manage data in local storage.

# Steps of the code:
## 1
The first thing we’re going to implement is the code which is needed to retrieve issues from the Local Storage. We do that we adding function fetchIssues().
This function runs when the app is loaded to bring the data from local storage. If that's nothing in local storage nothing will be retrieved - returns "null".

## 2
An event listener is added to retrieve the form's inpunts when submit button is clicked.

## 3
saveIssue function will "listen" the event and will take the values of the form, and create a new object for the "new issue" retrieved from the form.
Also "JSON.stringify" the object and add it to local storage. If is the first issue created will also create an array where the objects will be saved.
Reset the form inputs and calls fetchIssues(). Now, for sure will have the data added just now to local storage with the listener of submit button.
If is not the first time fetchIssues() will bring all the data from local storage looping trough the items in the array where the objects are stored.
To avoid repeat the issues in the app is used -> issuesList.innerHTML = ''; to empty all the issues thats showed in the app.

## 4
Finaly we have function to close or delete the issue. Close function receives the id of the issue that was closed and loops trough the issues in local storage
to find the same id and set it to status closed, set again to local storage and call the fetchIssues() function to change the users view.
Delete is similar to close. The diference is that rather than just change the status it uses the splice function to delete the issue, set the change in local storage and fetch again.
