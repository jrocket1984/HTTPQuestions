## HTTP Questions

__URLs__

* Name all of the parts of the url that you can remember. 
In your own words describe what they do.

```
-The URL is the uniform resource locator.  
-protocol, like http://, https://, ftp, etc.  The 's' in https means that the website is secure for passwords, etc.  
-domain, wich is the website name, like www.google.com.
-port-This is usually an automatically assigned port number.  80 is the default for http, but most people leave out the port number, and 443 is for https.
-path- it is a file path that is on the web server after the port but comes before the query, which is usually starts with a ?. A path coud be something like /file/directory.html.
-query string- it is the list of arguments that may modify the request but begins after the ? mark.
-anchor tag- identifies and 'a' # link that you can click on the page to jump on.
```  


* Name the pieces of the following urls:
	* `https://www.google.com/`
	
```
'https://' is the protocol and is a secure one with the 's' added. 'www.google.com' is the domain name.
```
	
	* `https://workbook.galvanize.com/cohorts/41/learning_experiences/367`
	
```
'https://' is the protocol and is a secure one with the 's' added. 'workbook.galvanize.com' is the domain name. '/cohorts/41/learning_experiences/367' is the file path on the web server that comes after the port.
```
	
	* `http://locahost:5000/animals/puppies?onlycute=1&size=medium#firstpuppy`
	
```
	'https://' is the protocol and is a secure one without the 's' added, meaning it is not secure.
``` 
	
	* `https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#4xx_Client_Error`
	
```
'https://' is the protocol and is a secure one with the 's' added. 'en.wikipedia.org' is the domain, or website name. '/wiki/List_of_HTTP_status_codes#4xx_Client_Error' is the path for the file name on the webpage.
```  
	
* Can a server use more than 1 port?

```
	Yes, computers can run multiple servers with multiple ports. Like having different doors into a house.
```

* Why is https different than http?

```
the 's' on https adds a security measure that prevents people's passwords and provate information from being shared openly in the console. The 'http' does not have this security feature.
```

* How does a server interpret the following url's query paramter.  What data structure does it create on the server?

```
http://locahost:5000/animals?puppies=fido&puppies=max&puppies=moxie
```

__HTTP Request/Response__

* Name at least 4 http verbs

```
GET, POST, PUT, DELETE.
```

* What is each verb useful for in your own words

```
GET is basically a simple request to receive information from a server.
```

* What does idempotent mean?

```
It means that multiple, identical requests will behave the same and have the same effect as a single request.  PUT and DELETE methods are supposedly idempotent. 
```

* Name the 5 http status code ranges.  What are they used for in general?

```
The five ranges are 100 through 500.  In the 100's range, this status code is informational and makes requests to receive fro the server and continue processes.
The 200's range indicates the action requested by the client was a success.  The 300's range indicates redirection and that the user must take additional action to complete the request.  The 400's range is the infamous error, usually the 404 error message and most likely because of a mistake by the user.  The 500's range indicates a servor error of some sort.  It could be that the server is overloaded or that there is an internal server error, etc.	
```


* If a server returns a http status code of 301 and a location of `https://www.google.com/`, what does the browser do?

```
301 tells the user that the website has moved permanently and that it will redirect the user to a given URL, like google.com in this case.
```

* For the following HTTP headers, decide if the following header is used for requests, responses or both:
	* Accept
	
	```
	It is used for both.
	```
	
	* Content-type
	
	```
	More so for requests since it is normally used in GET requests.
	```
	
	* User-agent
	
	```
	Typically used for requests.
	```
	
	* Set-cookies
	
	```
	Used for requests.
	```
	
	* Cache-control
	
	```
	Response header sometimes used for generating an expiration time.  
	```
	
	* Cookie
	
	```
	Usually used to request information from a user.
	```
	
* Is the following a http request or response?  How do you know for each?

```
This first one is a response because in an HTTP response the first line HTTP/1.1 200 OK is a status line.  
```
```
The second one is a request because it uses the verb DELETE to request a deletion of a post-man token in the g22-students.herokuapp.com list of student objects.   
```


```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
Vary: Accept
Content-Type: text/html; charset=utf-8
Content-Length: 722
ETag: W/"2d2-Wu0We9N5g35FXWY+gOATLA"
Date: Tue, 08 Mar 2016 20:37:11 GMT
Connection: keep-alive

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="/style.css">
    <title>Student Roster</title>
  </head>
  <body>
    <main>
      <h1>Student Roster</h1>
      
        <section>
          <h3>Daenerys Targaryen</h3>
          <span>Student Id: nys8fbohl</span>
          <h4>Hobby: Motherhood</h4>
          <img src="https://i.imgur.com/KlycRG5.jpg" alt="Daenerys Targaryen" />
        </section>
      
        <section>
          <h3>Tyrion Lannister</h3>
          <span>Student Id: njehukbohe</span>
          <h4>Hobby: Traveling</h4>
          <img src="https://i.imgur.com/fFMusdC.png" alt="Tyrion Lannister" />
        </section>
      
    </main>
  </body>
</html>
```

```
DELETE /students/n1vmyrw3x HTTP/1.1
Host: g22-students.herokuapp.com
Accept: application/json
Cache-Control: no-cache
Postman-Token: 0041e3c3-efdb-f0c3-b2f4-2d79f6d0f44b
```

__JSON__

* Describe what JSON is.  What is it used for.

```
JSON stands for JavaScript Object Notation. It is very similar in notation to Javascript but its data is only a string that represents objects and arrays. Unlike Javascript, JSON must be parsed for it to have any meaning.  
```

* Convert the following map into a javascript object then console log the age.



```
{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}
```

```
var companyObj = JSON.parse('{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}');
console.log(companyObj.age);
```


* Convert the following to a javascript object.  Console log each company name.

```
{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
}
```
```
var myObj = JSON.parse('{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
}');
myObj.Companies.map(function(el,index,array){console.log(el.company)});
Github
Airbnb
Square
Dropbox
```



* The following is javascript.  Convert the object to a string and console log it.

```
var myObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};
```
```
var newObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};
var newJSON = JSON.stringify(newObj);
console.log(newJSON);
{"company":"Galvanize","age":3,"categories":"Education"}
```
man 

__MISC__

* Describe what DNS is.

```
DNS stands for Domain Name system. It is a bunch of servers that looks up an IP address for a site like google.com.
```

* In the terminal, type `man curl`.  Look at the man page for curl.  What do the following flags do? `-v`, `-X`.  (Hint: to search for a string, type `/` then the text you want, then enter.  To quit the man page, type `q`).

```
man curl pulled up the definition for curl, which is a tool to transfer data from or to a server, using one of many protocols.  -v is part of three options in the libcurl(3) command.  for -X, When  combined  with -X, --request <command>, this option can be used to send an UIDL command instead, so the user may use the  email's  unique  identifier  rather than it's message id to
make the request.
```

* What is TCP/IP?  How does it interact with HTTP?

```
TCP stands for Transmission Control Protocol. It makes sure data gets to and from servers quickly.  IP stands for Internet Protocol. It is basically the same as addresses on the internet.   HTTP is basically a web server and a client.  The client opens a port, like http opens on the default of 80.  From the GET command you receive the date, time, and HTML for the webpage.  The  HTML is located in the data storage of the TCP.  
```

* Does HTTP break the data that is being sent into small packets?  If not, what protocol is responsible for it?

```
No, HTTP deals with communication between webpages.  TCP is responsible for breaking down the data into small packets and then reassembling them when they arrive somewhere else.  IP deals with the communication of the packets between computers.  
```