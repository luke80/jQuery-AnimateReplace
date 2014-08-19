jQuery-AnimateReplace
==========================

AnimateReplace jQuery plugin
===================
***How to animate something with this plugin***

Steps
-----

1. include the plugin javascript file
2. Define something to replace it with.
   This can either be an existing element, or you can specify HTML code that will be created on the fly.
3. use jquery to select it and animateReplace("flip", [[HTML or jQuery selection]]);
4. Congratulate yourself on a job well-done.


Example
------------------

The following shows an example:

   		<!DOCTYPE html>
   		<html>
   			<head>
   				<meta charset="ISO-8859-1">
   				<title>Basic Flip Thing</title>
   		    <link rel="stylesheet" href="css/animateReplace.jquery.css" type="text/css" />
   				<script src="js/vendor/jquery-2.1.1.js"></script>
   				<script src="js/animateReplace.jquery.js"></script>
   				<script>
   				$(document).ready(function() {
   					$("#flip").bind("click", function() {
   						var newSide	= ($("#side2").length > 0)?$('<span id="side1">Side 1</span>'):$('<span id="side2">Side 2</span>'),
   								tSide		= $("#sides-container").children().first();
   						if(d = tSide.data("plugin_animateReplace")) {
   							newSide.text(newSide.text()+" "+d['_touchCount']);
   						}
   						console.log("click!");
   						tSide.animateReplace("flip", newSide, {"do-debug":["flip","init","init-data","main","put-data"]});
   					});
   				});
   				</script>
   				<style>
   				#side1,#side2 {
					border: 1px solid #ccc;
					display:block;
					height: 600px;
					width: 600px;
				}
				#side1 {
					background-color: green;
					background-image: url("img/campusPhoto1.jpg");
				}
				#side2 {
					background-color: green;
					background-image: url("img/girl.jpg");
				}
				</style>
			</head>
			<body>
				<div id="flip">Flip</div>
				<div id="sides-container">
					<span id="side1">Side 1</span>
					<!-- <div id="side2" class="going-out ">Side 2</div>-->
   				</div>
   				
   		</body>
   </html>