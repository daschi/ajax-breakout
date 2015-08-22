##AJAX Breakout

- AJAX, short for asynchronous JavaScript and XML, is a group of interrelated Web development techniques used on the client-side to create asynchronous Web applications.

- Without AJAX
![Alt text](/no-ajax.png "Without Ajax")

- With AJAX
![Alt text](/ajax.png "With Ajax")

##Seven Steps:
1. Trigger the event

  - on click of a button
  ```
  $("#eyed").on("click", function(e){
  e.preventDefault
  })
  ```

2. Stop the default event

  - Prevent traditional get/post/put/delete request
  - For example, if Facebook like button will not refresh the whole page, instead, it prevent default and go into the AJAX process.

3. Send the request

  - Use AJAX to send request to the server from the client.
  - Hitting the GET/POST route without refreshing the page.

4. Receive the request on the server (process the request)

  - Server sends response to AJAX.

5. Send back the response to the client
6. Interpret response with javascript
7. Change the dom