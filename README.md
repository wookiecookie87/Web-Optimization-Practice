## Website Performance Optimization portfolio project
Steps to Optimize pizza.html in views/main.js

1. Change querySelectorAll into getElementsByClassNames. 

2.  In updatePositions(), there is forced synchronious layout warning.
	Inside the forloop  that loop over 'items', they run layout and style over and over again.
	Take out "var phase = Math.sin((document.body.scrollTop / 1250) + (i % 5));" out of the loop
	and set it in a array, then update style in batch over forloop.

3.  Also, we dont need to look for '.mover' everytime we scroll.  Set '.mover' seletors in a global variable
	and reuse.

4. In changePizzaSize(), these is also forced synchronious layout warning.
   Take two lines, 
   		var dx = determineDx(document.querySelectorAll(".randomPizzaContainer")[i], size);
      	var newwidth = (document.querySelectorAll(".randomPizzaContainer")[i].offsetWidth + dx) + 'px';
    outside of forloop. 	

##How to Run the application

# Run in Server
1.  Go to application folder in Terminal and type
    python -m SimpleHTTPServer 8080

2.  In Browser address bar, type,
    localhost:8080

3.  Enjoy the application


# Run in static mode
method 1    Go to application folder in Terminal and type
            oepn 'index.html'
method 2    Go into applciation folder through user interface
            Double click 'index.html'            