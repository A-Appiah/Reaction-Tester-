# Reaction-Tester-
This is some simple code to create a reaction tester. It's not very complex, but feel free to make any changes to make it your own! 

<!doctype html>
<html>
<head>
    <title>Reaction Tester</title>

    <meta charset="utf-8" />
    <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
	
	
</head>

<style>
	#box {
		width:200px;
		height:200px;
		background-color:red;
		display:none;
		position:relative;
	}
	
	body {
		font-family:Verdana, Geneva, sans-serif;
		
	}
	
	.bold {
	
		font-weight:bold;
		
	}

</style>


<body>

	<h1>Test your reactions!</h1>
	
	<p>Click on the boxes and circles as quickly as you can!</p>
	
	<p class="bold">Your Time: <span id="time">0</span>s</p>
		
	<div id="box"</div>
		
		<script type="text/javascript">
		
			function getRandomColor() {
   				var letters = '0123456789ABCDEF'.split('');
    			var color = '#';
    			for (var i = 0; i < 6; i++ ) {
        			color += letters[Math.floor(Math.random() * 16)];
    			}
    			return color;
			}
			
			var clickedTime; var createdTime; var reactionTime;
			
			function makeBox() {
				
				
				var time=Math.random();
			
				time=time*5000;
			
				setTimeout(function() {
				
					if (Math.random()>0.5) {
			
						document.getElementById("box").style.borderRadius="100px";
						
					} else {
						
						document.getElementById("box").style.borderRadius="0";
					
					}
					
					var top=Math.random();
					
					top=top*300;
					
					var left=Math.random();
					
					left=left*500;
					
					document.getElementById("box").style.top=top+"px";
					
					document.getElementById("box").style.left=left+"px";
					
					document.getElementById("box").style.backgroundColor=getRandomColor();
			
					document.getElementById("box").style.display="block";
			
					createdTime=Date.now();
					
				}, time);
				
			}
		
		
			document.getElementById("box").onclick=function() {
			
				clickedTime=Date.now();
							
				reactionTime=(clickedTime-createdTime)/1000;
				
				document.getElementById("time").innerHTML=reactionTime;
								
				this.style.display="none";
				
				makeBox();
			}
			
			makeBox();
		
		</script>
</body>

</html>
