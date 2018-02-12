#DOM vs BOM
The BOM (Browser Object Model) consists of the objects navigator, history, screen, location, and document which are children of window. In the document, node is the DOM (Document Object Model), the document object model, which represents the contents of the page. 

[BOM](){
	[document](DOM, current HTML page)
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
			
		}
	}
}

