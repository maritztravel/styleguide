# styleguide

> All examples can be found here: https://plnkr.co/users/maritzdev

> **NOTE:** if any of these examples don't work check out the **[github rate limit api](https://api.github.com/rate_limit)** to make sure the calls are succeeding. 

* **Component vs (Controller + Directive + Template)**
	* **[Component vs Controller](https://plnkr.co/edit/QRmBKp?p=preview)**
		* This app has one component, one controller, and one service (mocking a ajax call). Functionality-wise the controller and the component are almost identical. One difference is that the component wraps its controller with the template vs the standalone controller which is linked to an existing template by putting ng-controller attribute on it. The component simply has to name the html tag in spinal-case (i.e. &lt;mtc-component&gt;&lt;/mtc-component&gt;) and the component name in camelCase (i.e. mtcComponent) and then you have a sort of ready-to-go directive. Another nice feature of the component is that we can use the built-in $onInit lifecycle hook to kick off the startup function(s) vs the controller which simply has the startup function(s) at the bottom of the controller. 
	* **[Component Bindings](https://plnkr.co/edit/RCesTW?p=preview)**
		* Shows simple way to break up functionality into sub-components. The communication, is this case, between components happens with a ONE-WAY BINDING.
	* **[Component Bindings - Parent](https://plnkr.co/edit/kg13Z3?p=preview)**
		* The communication, is this case, between components happens by having a REQUIRE of the parent component in the child component. This gives the child component access to everything in the parent component's scope.

* **Promises**
	* **[Component + Service with Promises](https://plnkr.co/edit/ZWtX4B?p=preview)**
		* Very simple app with one component and one service. Component uses service to call github api and show some data in the template. The service is written so that it returns the promise from angular's $http service and does nothing else. We call the service from the component using the THEN,  CATCH, and FINALLY pattern. This allows for the flattening of the async processes. It makes the code much more readable.
	* **[Chaining Promises](https://plnkr.co/edit/2oLQhi?p=preview)**
		* This shows how you can add a return statement that returns a promise in the first THEN, which allows you to simply chain on another THEN to handle the promise from the second async call. This flattens the code view when issuing multiple async calls so the code can be read as though it is almost synchronous. Only sticky issue is if you want to handle errors differently for each async call then you need a catch on each call and one final one at the end to catch any failure.
	*  **[$q.all to Resolve all Promises at Once](https://plnkr.co/edit/BrtIuo?p=preview)**
		* Here we do one call to fetch a list of 30 users then we loop thru those 30 and immediately make a call forEach to get the user details. But we want to wait until all the responses are returned until we show the list so we use $q.all() and pass in the array of promises to be resolved. After each individual call is resolved the main promise is resolved. 

