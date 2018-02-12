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
		[Methods](){
			[getElementById](returns the element that has the ID attribute with the specified value. Returns null if no elements with the specified ID exists.){
				<!DOCTYPE html>
				<html>
				<body>
				<p id="demo">Click the button to change the text in this paragraph.</p>
				<button onclick="myFunction()">Try it</button>
				<script>
				function myFunction() {
				    document.getElementById("demo").innerHTML = "Hello World";
				}
				</script>
				</body>
				</html>
			}
			[getElementsByName](returns a collection of all elements in the document with the specified name, the value of the name attribute as a NodeList object.){
				document.getElementsByName(name)
			}
			[getElementsByTagName](returns a collection of all elements in the document with the specified tag name, as a NodeList object.){
				document.getElementsByTagName(tagname)
			}
			[close](closes the output stream previously opened with the document.open method, and displays the collected data in this process.){
				<script>
				function myFunction() {
				    document.open();
				    document.write("<h1>Hello World</h1>");
				    document.close();
				}
				</script>
			}
			[open](opens an output stream to collect the output from any document.write or document.writeln methods.){
				document.open(MIMEtype, replace)
				//MIMEtype = type of document. default is text/html
				//replace = the history entry from the document which opened this document
			}
			[write](writes HTML expressions or JavaScript code to a document.){
				document.write(exp1, exp2, exp3, ...)
			}
			[writeln](identical to the document.write method, with the addition of writing a newline character after each statement.){
				document.writeln(exp1, exp2, exp3, ...)
			}
			[createElement](creates an Element Node with the specified name.){
				<!DOCTYPE html>
				<html>
				<body>
				<p>Click the button to make a BUTTON element with text.</p>
				<button onclick="myFunction()">Try it</button>
				<script>
				function myFunction() {
				    var btn = document.createElement("BUTTON");
				    var t = document.createTextNode("CLICK ME");
				    btn.appendChild(t);
				    document.body.appendChild(btn);
				}
				</script>
				</body>
				</html>
			}
			[createTextNode](creates a Text Node with the specified text.)
			[appendChild](appends a node as the last child of a node.){
				var node = document.createElement("LI");                 // Create a <li> node
				var textnode = document.createTextNode("Water");         // Create a text node
				node.appendChild(textnode);                              // Append the text to <li>
				document.getElementById("myList").appendChild(node);     // Append <li> to <ul> with id="myList"
			}
			[insertBefore](inserts a node as a child, right before an existing child, which you specify.){
				var newItem = document.createElement("LI");       // Create a <li> node
				var textnode = document.createTextNode("Water");  // Create a text node
				newItem.appendChild(textnode);                    // Append the text to <li>
				var list = document.getElementById("myList");    // Get the <ul> element to insert a new node
				list.insertBefore(newItem, list.childNodes[0]);  // Insert <li> before the first child of <ul>
			}
			[removeChild](removes a specified child node of the specified element.){
				node.removeChild(node)
			}
			[replaceChild](replaces a child node with a new node.){
				node.replaceChild(newnode, oldnode)
			}
		}
		[Traversal](){
			[firstChild|lastChild](Start/end of this node’s list of children){
				var x = document.getElementById("myList").firstChild.innerHTML;
			}
			[childNodes](Array of all this node’s children. The nodes in the collection are sorted as they appear in the source code and can be accessed by index numbers. The index starts at 0. Whitespace inside elements is considered as text, and text is considered as nodes. Comments are also considered as nodes.){
				var c = document.body.childNodes;
			}
			[nextSibling|previousSibling](Neighbouring nodes with the same parent.){
				<li id="item1">Coffee (first li)</li><li id="item2">Tea (second li)</li>
				....
				var x = document.getElementById("item1").nextSibling.innerHTML;
				// -> Tea (second li)
			}
			[parentNode](Node that contains this node){
				<ul>
				  <li id="myLI">Coffee</li>
				  <li>Tea</li>
				</ul>
				.....
				var x = document.getElementById("myLI").parentNode.nodeName;
				document.getElementById("demo").innerHTML = x;
				//-> UL
			}
		}
	}
	[history](List of pages user has visited){
		[Properties](){
			[history.length]()
		}
		[Methods](){
			[back](loads the previous URL in the history list.){
				<button onclick="goBack()">Go Back</button>
				<script>
				function goBack() {
				    window.history.back();
				}
				</script>
			}
			[forward](loads the next URL in the history list.){
				history.forward()
			}
			[go](loads a specific URL from the history list.){
				history.go(number|URL)
				// The parameter can either be a number which goes to the URL within the specific position (-1 goes back one page, 1 goes forward one page), or a string.
			}
		}
	}
	[location](URL of current page){
		[Properties](){
			[location.host](sets or returns the hostname and port of a URL.)
			[location.hostname](sets or returns the hostname of a URL.)
			[location.href](sets or returns the entire URL of the current page.)
			[location.pathname](sets or returns the pathname of a URL.)
			[location.port](sets or returns the port number the server uses for a URL.)
			[location.protocol](sets or returns the protocol of the current URL, including the colon, : .)
			[location.search](sets or returns the querystring part of a URL, including the question mark. The querystring part is the part of the URL after the question mark. This is often used for parameter passing.)
		}
		[Methods](){
			[assign](loads a new document.){
				location.assign("https://www.w3schools.com");
			}
			[reload](used to reload the current document.  does the same as the reload button in your browser.){
				location.reload(forceGet)
				//forceGet = optional Specifies the type of reloading: false(default), true
			}
			[replace](replaces the current document with a new one. removes the URL of the current document from the document history, meaning that it is not possible to use the "back" button to navigate back to the original document.){
				location.replace(newURL)
			}
		}
	}
	[navigator](info about the browser){
		[Properties](){
			[navigator.appName](returns the name of the browser.)
			[navigator.appVersion]()
			[navigator.browserLanguage]()
			[navigator.cookieEnabled]()
			[navigator.platform]()
			[navigator.userAgent]()
		}
	}
	[screen](Screen area occupied by the browser){
		[Properties](){
			[screen.availheight]()
			[screen.availWidth]()
			[screen.colorDepth]()
			[screen.height]()
			[screen.width]()
			[screen.pixelDepth]()
		}
	}
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

#JQuery
[JQuery](A JavaScript library whose purpose is to make it easier to manipulate the DOM. The jQuery syntax is tailor-made for selecting HTML elements and performing some action on the elements.){
	[syntax](){
		$(selector).action()
		⋅ $: define/access jQuery
		⋅ (selector): query HTML elements
		⋅ action(): action to be performed on the elements
		[examples](){
			$(this).hide() - hides the current element.
			$("p").hide() - hides all <p> elements.
			$(".test").hide() - hides all elements with class="test".
			$("#test").hide() - hides the element with id="test".
			$("[href]").action() - do action to all elements with href attributes
			$("a[target='_blank']").action() -  Selects all <a> elements with a target attribute value equal to "blank"
			$(‘tr:even') - select all even <tr> elements
		}
	}


}