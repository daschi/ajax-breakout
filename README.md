##AJAX Breakout

- AJAX, short for asynchronous JavaScript and XML, is a group of interrelated Web development techniques used on the client-side to create asynchronous Web applications.

- Without AJAX
![Alt text](/no-ajax.png "Without Ajax")

- With AJAX
![Alt text](/ajax.png "With Ajax")

####Things you will learn today
  - A very basic AJAX concept
  - Steps to do a basic AJAX call
  - Don't worry if you cannot follow thru today, you will learn from your teacher(s) again and you can always refer to this readme again.

####Seven Steps:
1. Trigger the event

  - on click of a button
  ```
  $("#eyed").on("click", function(e){

  })
  ```

2. Stop the default event

  - Prevent traditional get/post/put/delete request
  - For example, if Facebook like button will not refresh the whole page, instead, it prevent default and go into the AJAX process.
  ```
  $("#eyed").on("click", function(e){
    e.preventDefault();
  })
  ```

3. Send the request

  - Use AJAX to send request to the server from the client.
  - Hitting the GET/POST route without refreshing the page.
  ```
  $("#eyed").on("click", function(e){
    e.preventDefault();
  })
  ```

4. Receive the request on the server (process the request)

  - Server sends response to AJAX.
  ```
  $("#eyed").on("click", function(e){
    e.preventDefault();

    $.ajax({
      url:      url,      // Which Sinatra route to hit
      method:   method,   // GET/POST/PUT/DELETE, to specify the route you are hitting.
      data:     data,     // Data being sent to the route, if it's a GET route, we don't need this, because we are not sending in any data.
      dataType  "json"    // dataType expected from server
    })
  })
  ```

5. Send back the response to the client

  ```
  $("#eyed").on("click", function(e){
    e.preventDefault();

    var request = $.ajax({
      url:      url,      // Which Sinatra route to hit
      method:   method,   // GET/POST/PUT/DELETE, to specify the route you are hitting.
      data:     data,     // Data being sent to the route, if it's a GET route, we don't need this, because we are not sending in any data.
      dataType  "json"    // dataType expected from server
    })

    request.done(function(responseData){
    
    })
  
    request.fail(function(responseData){
     console.log("Failed, FIX IT!")
    })
  })
  ```
6. Interpret response with javascript
  ```
  $("#eyed").on("click", function(e){
    e.preventDefault();

    var request = $.ajax({
      url:      url,      // Which Sinatra route to hit
      method:   method,   // GET/POST/PUT/DELETE, to specify the route you are hitting.
      data:     data,     // Data being sent to the route, if it's a GET route, we don't need this, because we are not sending in any data.
      dataType  "json"    // dataType expected from server
    })

    request.done(function(responseData)){
    console.log(responseData); // You can see the responseData in console to decide how you want to maniplate the DOM
    }
  
    request.fail(function(responseData){
     console.log("Failed, FIX IT!")
    })
  })
  ```
7. Change the dom
  ```
  $("#eyed").on("click", function(e){
    e.preventDefault();

    var request = $.ajax({
      url:      url,      // Which Sinatra route to hit
      method:   method,   // GET/POST/PUT/DELETE, to specify the route you are hitting.
      data:     data,     // Data being sent to the route, if it's a GET route, we don't need this, because we are not sending in any data.
      dataType  "json"    // dataType expected from server
    })

    request.done(function(responseData)){
    console.log(responseData); // You can see the responseData in console to decide how you want to maniplate the DOM
    $('eyed').innerHTML(responseData);   // Depends on how you want to manuiplate the DOM
    }
  
    request.fail(function(responseData){
     console.log("Failed, FIX IT!")
    })
  })
  ```

