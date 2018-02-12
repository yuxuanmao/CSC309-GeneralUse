#DOM vs BOM
The BOM (Browser Object Model) consists of the objects navigator, history, screen, location, and document which are children of window. In the document, node is the DOM (Document Object Model), the document object model, which represents the contents of the page. 

[BOM](){
	[document](DOM, current HTML page){
		[Properties](){
			[anchors](The anchors collection returns a collection of all <a> elements in the document that have a name attribute){
				document.anchors
			}
			[body](The body property sets or returns the document's body){
				document.body
			}
			[cookie](The cookie property sets or returns all name/value pairs of cookies in the current document){
				document.cookie
			}
			[domain](The domain property returns the domain name of the server that loaded the current document){
				document.domain
			}
			[forms](The forms collection returns a collection of all <form> elements in the document){
				document.forms
				// sorted as they appear in the source code.
			}
			[images](The images collection returns a collection of all <img> elements in the document){
				document.images
				// will not return a collection of <input> with type="image"
			}
			[links](The links collection returns a collection of all links in the document){
				document.links
				// if not such elements then return nothing
			}
			[referrer](The referrer property returns the URL of the document that loaded the current document){
				document.referrer
			}
			[title](The title property sets or returns the title of the current document (the text inside the HTML title element)){
				document.title
			}
			[URL](The URL property returns the full URL of the current HTML document){
				document.URL
			}
		}
	}
	[history](List of pages user has visited)
	[location](URL of current page)
	[navigator](info about the browser)
	[screen](Screen area occupied by the browser)
	[window](The browser window, Top level object in the BOM){
		[alert](if you want to make sure information comes through to the user. user has to click ok to proceed.){
			window.alert("sometext")
		}
		[confirm](if you want the user to verify or accept something, user has to click either ok or cancel){
			if(window.confirm("press a button")){
				txt = "you pressed ok";
			}else{
				txt = "you pressed cancel";
			}
		}
		[prmpt](if you want the user to input a value before entering a page. user enter ok or cancel after input){
			var person = prompt("Please enter your name", "Harry Potter");
			// prompt("sometext", "defaultText")
			if(person == null || person == ""){
				txt = "user cancelled";
			}else{
				txt = "Hello " + person; 
			}
		}
		[setInterval](repeats a given function at every given time interval){
			var myVar = setInterval(myTimer, 1000);
			function myTimer(){
				var d = new Data();
				document.getElementById("demo").innerHTML = d.toLocaleTimeString();
			}
		}
		[setTimeout](executes a function, after waiting a specified number of milliseconds){
			<button onclick="setTimeout(myFunction, 3000)">Try it</button>
			<script>
			function myFunction(){
				alert('Hello');
			}
			</script>
		}
		[clearInterval](stops the executions of the function specified in the setInterval method){
			<p id="demo"></p>
			<button onclick="clearInterval(myVar)">Stop time</button>
			<script>
			var myVar = setInterval(myTimer, 1000);
			function myTimer() {
			    var d = new Date();
			    document.getElementById("demo").innerHTML = d.toLocaleTimeString();
			}
			</script> 
		}
		[ClearTimeout](stops the execution of the function specified in setTimeout method){
			<button onclick="myVar = setTimeout(myFunction, 3000)">Try it</button>
			<button onclick="clearTimeout(myVar)">Stop it</button>
		}
		[open](opens a new browser window){
			window.open(URL, name, specs, replace);
			[URL](optional URL)
			[name](optional){
				[_blank](loaded to new window default)
				[_parent](loaded to the parent frame)
				[_self](replace current URL)
				[_top](replace URL of framesets may be loaded)
				[name](name of window)
			}
		}
		[close](cloese the current window){
			function openWin() {
			    myWindow = window.open("https://www.w3schools.com", "_blank", "width=200, height=100");
			}
			function closeWin() {
			    myWindow.close();
			} 
		}
		[blur](used to remove focus from a radio button){
			document.getElementById("myRadio").blur();
		}
		[focus](used to give focus to a radio button){
			document.getElementById("myRadio").focus();
		}
		[moveBy](moves a window a specified number of pixels relative to its current coordinates){
			window.moveBy(x, y);
		}
		[moveTo](resizes a window by the specified amount, relative to its current size){
			resizeBy(width, height);
		}
		[resizeBy](resizes a window by the specified amount, relative to its current size){
			resizeBy(width, height);
		}
		[resizeTo](resizes a window to the specified width and height){
			window.resizeTo(width, height);
		}
		[scrollBy](scrolls the document by the specified number of pixels){
			window.scrollBy(xnum, ynum);
		}
		[scrollTo](scrolls the document to the specified coordinates){
			window.scrollTo(xpos, ypos);
		}
	}
}

[cookie](){
	Cookies are data, stored in small text files, on your computer.
	When a web server has sent a web page to a browser, the connection is shut down, and the server forgets everything about the user.
	Cookies were invented to solve the problem "how to remember information about the user":
		⋅ When a user visits a web page, his name can be stored in a cookie.
    	⋅ Next time the user visits the page, the cookie "remembers" his name.

}