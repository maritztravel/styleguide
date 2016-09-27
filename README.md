# styleguide

All examples can be found here: https://plnkr.co/users/maritzdev

* Promises
	* Example 1 - (PlunkerName: **Component + Service with Promises**)
		* Very simple app with one component and one service. Component uses service to call github api and show some data in the template. The service is written so that it returns the promise from angular's $http service and does nothing else. We call the service from the component using the THEN,  CATCH, and FINALLY pattern. This allows for the flattening of the async processes. It makes the code much more readable.
	* Example 2 - (PlunkerName: **Chaining Promises**)
		* This shows how you can add a return statement that returns a promise in the first THEN, which allows you to simply chain on another THEN to handle the promise from the second async call. This flattens the code view when issuing multiple async calls so the code can be read as though it is almost synchronous. Only sticky issue is if you want to handle errors differently for each async call then you need a catch on each call and one final one at the end to catch any failure.

