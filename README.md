# App4-Base_Code
This is the base code for App 4 Assignment


consider using a debugging tool called the javaScript Console. It can found in most web browsers developers kits. I can find it by right clicking the app
site and selecting "inspect". This will split the screen with lots of smaller windows. Find the one labeled "console" and watch the console while you
click through the app and it will notify you of the line number of any errors. Be sure to refresh your app from the start. 

If you get this error from the very start ignore it -> Error with Permissions-Policy header: Origin trial controlled feature not enabled: 'interest-cohort'.
  <head> 
      <title>Hello World</title>  
      <meta name="viewport" content="width=device-width, initial-scale=1">
      <meta name="apple-mobile-web-app-capable" content="yes">
      <link rel="stylesheet" href="w3.css">
      <link rel="stylesheet" href="w3-colors-flat.css">
   </head> 


<script>
        var flu_count = 0;//this is the code for establishing the variable of flu.//
        var strep_count = 0;//This code if for establishing the variable of strep.//
//The below functions are to be able to count the number of answers that contribute to flu or strep.//

        function fluAdd(){//changed to fluAdd so that the answers corresponding to flu will add up as a total later//
	    allergy_count = allergy_count + 1;
        }

        function strepAdd(){//changed to strepAdd so that the answers corresponding to strep will add up as a total later//
            cold_count = cold_count + 1;
        }
	
	function result(){
		var allergyPercent = (allergy_count/4)*100;//this is for calculating percent allergy by dividng by the four total questions, and multiplying this by 100.//
		var coldPercent = (cold_count/4)*100;//this is for calulating percent cold, using the same method above//
		var result = document.getElementById("five");//this is so that it replaces the results test final page with the resulting pprobablities.//
		result.innerHTML = "Probability it is allergies =" + allergyPercent + "<br> Probability it is a cold =" + coldPercent;
	}
	//I inserted this line above to showcase the percent allergy and the percent chance of cold.//
	//At first, I had the code above below the other codes for creating the other pages, but that didn't work. So, I moved it here.//
	//It still didn't work, so I tried changed the ID page to five instead of "results" and also adjusted the spacings.//
	//I just moved this entire code on the top above the script; after I moved it, I also adujusted my spacing of the var allergy percent, and it finally produced the results page and the percentages I needed.//
//After all of this, I realized I needed to make sure my ID references on the results page matched the page ID before it//
  </script>

<!--this part of the code below is to set up the pages in the app and sets the website up so that it will show pages within the html body.--> 

<style>	
.body {
     margin: 0em;
}

.page {
    width: 100vw;
    height: 100vh;
    position: fixed;
    top: 0;
    left: -100vw;
    overflow-y: auto;
    z-index: 0;
    background-color: hsl(0,0%,100%);
}

  .page:target {
    left: 0vw;
    z-index: 1;
}
</style>

<body>
<div id="header" class="w3-container w3-flat-carrot">
	<h1>Cold or Allergies?</h1>
</div>
	
<div id="content" class="w3-container">
	<p>Are you feeling like you might have a cold but wonder if it is allergies. Answer a few short questions to find out!</p>
	
	<a href="#one" class="w3-btn w3-grey w3-round"> Get Started </a><!--This code is so that a button can be made and take you to the next page.-->
	
	<p>The following code has been developed by students and/or researchers of the Freshman Research Initiative DIY Diagnostics Stream at The University of Texas at 		Austin.  This code is shared for demonstration purposes and should not be considered a product -- it is for entertainment purposes only. Any user of this code 			does so at their own risk. Members of the DIY Stream, FRI, and The University of Texas system are not liable for anything related to this code.</p>
 	
	<p>THIS CODE SHOULD NOT BE USED TO DIAGNOSE ANY KIND OF MEDICAL CONDITION.</p>

<div class="page" id="one">
	<div id="header" class="w3-container w3-flat-carrot"><!--these are in every question for dividing between the pages and headers-->
		<h1>Question 1</h1>
	</div>
	
    	<div id="content" class="w3-container">
        <p>Are your eyes watery or itchy?</p>  
	<a href="#two" onclick="allergyAdd();" class="w3-btn w3-black">Yes</a><!--This code and the one below is so that a button can be pressed and take you to the next page with matching IDs. It also adds to the total count of questions.-->
	<a href="#two" onclick="coldAdd();" class="w3-btn w3-black">No</a>
    	</div><!--/content-->
</div>

<div class="page" id="two"><!--This part is to identify the page as page two so that the button from page one can be directed to page two.-->
	<div class="w3-container w3-flat-carrot">
		<h1>Question 2</h1>
	</div>
	
	<div id="content" class="w3-container">
		<p>Do you have a fever?</p>
		<a href="#three" onclick="coldAdd();" class="w3-btn w3-black">Yes</a><!--created button to take patient to next question three-->
		<a href="#three" onclick="AllergyAdd();" class="w3-btn w3-black">No</a>
	</div><!--/content-->
</div>	

<div class="page" id="three">
	<div class="w3-container w3-flat-carrot">
		<h1>Question 3</h1>
	</div>
	
	<div id="content" class="w3-container">
		<p>Do you have a sore throat?</p>
		<a href="#four" onclick="coldAdd();" class="w3-btn w3-black">Yes</a><!--created button to take patient to next question four-->
		<a href="#four" onclick="allergyAdd();" class="w3-btn w3-black">No</a>
	</div><!--/I changed each page so that it could go onto the next page. I added this next to the hashtag.-->
</div>	

<div class="page" id="four">
	<div class="w3-container w3-flat-carrot">
		<h1>Question 4</h1>
	</div>
	
	<div id="content" class="w3-container">
		<p>Are youre symptoms seasonal or chronic?</p>
		<a href="#five" onclick="allergyAdd();" class="w3-btn w3-black">Yes</a><!--created button to take pateint to next question five-->
		<a href="#five" onclick="coldAdd();" class="w3-btn w3-black">No</a>
	        </div>
</div>

<div class="page" id="five"><!--This is just the results page so I just added a results button that would jump to final caculations for results.-->
	<div id="content" class="w3-container">
		<button class="w3-btn w3-black" onclick="result();"> Results </button><!--results button here to go to results page-->
		<p id="result"></p>
	</div>
</div>		
<!--I added this page five and made sure there was a button to make it jump to the results page-->
<footer class="w3-bottom w3-container w3-flat-carrot">
	<p>DIY!</p>
</footer>

</body>
</html>
