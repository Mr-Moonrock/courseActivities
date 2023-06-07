# How Web Works Exercise
## Part One: Solidify Terminology
### In your own terms, define the following terms:

1. What is HTTP?
   Hypertext Transfer Protocol, is the foundation for any data exchange, it is necessary for retrieving any resource, whether that is images, text, videos, scripts, etc.

2. What is a URL?
   Uniform Resource Locators, is comprised of Protocol(http or https), HostName, Port, Resource, Query. 
   Example: https://github.com/orgs/mdn/projects?query=is%3Aopen 
   (protocol= https) :// ( Hostname= github.com) (Port= is not listed in URL),(Resource= /orgs/mdn/projects), (Query= ?query=is%3Aopen)

3. What is DNS?
   Domanin Name System is the equivalent to a phonebook for the Internet. This will help locate the correct internet domain names and translates into Internet Protocol (IP) adresses.

4. What is a query string?
   This is the extra information at the end of a URL. In the example "https://icanhazdadjoke.com/search?term=pirate", it would be the "?term=pirate". This helps locate the specific page/term within a website.

5. What are two HTTP verbs and how are they different?
   GET: requests of the specified source, which only retrieves data.
   HEAD: same as GET, but doesn't retrieve response body.
   POST: sumits information to the specified source and makes changes or other side effects to server. 
   PUT: replaces all current representation of the target resource with request payload
   DELETE: deletes the target resource
   CONNECT: creates a tunnel to target resource
   OPTIONS: describes the communication options for the target resource
   TRACE: performs a message loop-back test along the path to the target resource
   PATCH: applies partial modifications to the target resource

6. What is an HTTP request?
   A request is from client to server. To make a request the client uses components of a URL. Which includes, a request line, a series of http headers, or header field, message body(if needed).

7. What is an HTTP response?
   A response is server to client. The server will send the client the resource or information they're seeking, or inform the client that the task has be completed; or will even give feedback if there was an error while processing the request. 

8. What is an HTTP header? Give a couple examples of request and response headers you have seen.
   A header gives context and/or information on what the response/request was given/recieved. Example: a request message can use headers to specify which media formats is preferred, while a response can indicate which media formats of the returned body.
   I have only seen a 404 response code displayed when mistyping the URL. 

9.  What are the processes that happen when you type “http://somesite.com/some/page.html” into a browser?
    Using DNS, your browser will transfer the name into the IP address. THe browser then makes a request to the specified IP address. The server will send a response, if its successful, it will return with status code 200. The browser makes DOM based off of the HTML, and serches for any additional resources needed (JS,CSS, images, etc). The browser then makes/recieves seperate HTTP requests/responses for each resource needed.

## Part Two: Practice Tools
1. Using curl, make a GET request to the icanhazdadjoke.com API to find all jokes involving the word “pirate”.
   curl -H "Accept: text/plain" "https://icanhazdadjoke.com/search?term=pirate"
Why couldn't the kid see the pirate movie? Because it was rated arrr!
What did the pirate say on his 80th birthday? Aye Matey!
What does a pirate pay for his corn? A buccaneer!
Why do pirates not know the alphabet? They always get stuck at "C".
Why are pirates called pirates? Because they arrr!%

2. Use dig to find what the IP address is for icanhazdadjoke.com
   dig icanhazdadjoke.com
   172.67.198.173 or 104.21.66.15

3. Make a simple web page and serve it using python3 -m http.server. Visit the page in a browser.
    cd creatingServer
❯ python3 -m http.server
Serving HTTP on :: port 8000 (http://[::]:8000/) ...
   



