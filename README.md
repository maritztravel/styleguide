# styleguide

All examples can be found here: https://plnkr.co/users/maritzdev

* Promises
	1) PlunkerName: Component + Service with Promises
		* Very simple app with one component and one service. Component uses service to call github api and show some data in the template. The service is written so that it returns the promise from angular's $http service and does nothing else. We call the service from the component using the THEN,  CATCH, and FINALLY pattern. This allows for the flattening of the async processes. It makes the code much more readable. 

