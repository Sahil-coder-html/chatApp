
<html>
<head>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css"></link>
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
  <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js"></script>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
	 <title>SV Chat Project</title>
<style>
body{

 background-image:url("https://i.redd.it/qwd83nc4xxf41.jpg");
	  size: cover;
	  repeat:no-repeat;
}

	 button{
	     width: 75px;
	     height: 30px;
	 background-color: #ff0000;
	 border-radius:28%;
	 padding:0px;8px 5px;
	 outline: none;
	 border-color:#ff0000;
	 text-align: center;
	 display: inline-block;
	 }
	 
	 input[type=submit], select {
	     position:fixed;
	 width: 50px;
	 height: 50px;
	 background-color:#23803A;
	 background-size:40px 20px;
	 background-repeat: no-repeat;
	 color: white;
	 border-radius:50%;
     margin-left: 290px;
      margin-top:350px;
	 outline: none;
	 border-color:transparent;
	 position:fixed;
	 bottom:4px;
	 }
	input[type=text],select {
	    width: 288px;
	    height: 40px;
        background-color:#dbdbdb;
        border-radius: 20px;
        padding:8px;
        margin: 8px 0px 10px 0px;
        outline:none;
        border-color:transparent;
        font-size: 18px;
        font-family:arial;
        word-wrap: break-word;
        overflow: auto;
        bottom:-4px;
        position: fixed;
    overflow: break-word;
	}
	
	 ul{
	 width:360px;
	 height:460px;
	 margin-top:-0.5px;
     background-color:transparent;
	 background-repeat: no-repeat;
	 font-family:arial;
	 border-radius:0px;
	 box-sizing:border-box;
	 position:fixed;
     overflow:scroll;
     size:cover;
	 cursor:pointer;
	 margin-bottom:4px; 
	 }
	 
	 ul li {
	   
         display:inline-block;
	     width:280px;
	     height:auto;
	     margin:4px 2px;
	     padding: 10px;
	     background-color:#78ab85;
	     color:black;
	      border-radius:10px;
	     position: relative;
	     word-wrap: break-word;
	     font-size: 20px;
	     align-item:right;
	 }
	 .tpborder{
	     width: 370px; 
	     height: 55px;
	     background-color:#23803A;
         position:fixed;
         margin-bottom:100px;
         margin-left: -8px;
         margin-top: -8px;
	 }
	 p{
	     margin-left: 12px; 
	     font-family:Monospace;
	     font-size: 20px;
	     margin-top:16px;
	     color: #d8e6e1;
	 }
	 select{
	     height:50px;
	     width:110px ;
	     margin-left: -80px;
	     bottom: 508px;
	     background-color:#23803A ;
	 }
	 .Image{
	     margin-left: -70px; 
	    bottom: 505px;
	 }
	  .attach{
	     margin-left:10px;
	 }
	
</style>
 </head>
	 <body bgcolor="black">
	     <div class="tpborder">
		 <p id="myName"></p>
		 </div>
	<!-- The core Firebase JS SDK is always required and must be listed first -->
<script src="https://www.gstatic.com/firebasejs/7.17.1/firebase-app.js"></script>

<!-- The core Firebase JS SDK is always required and must be listed first -->
<script src="https://www.gstatic.com/firebasejs/7.17.1/firebase-database.js"></script>
<!-- TODO: Add SDKs for Firebase products that you want to use
     https://firebase.google.com/docs/web/setup#available-libraries -->
<script src="https://www.gstatic.com/firebasejs/7.17.1/firebase-analytics.js"></script>
<script>
   // Your web app's Firebase configuration
  var firebaseConfig = {
    apiKey: "AIzaSyB1ZQJ3vaC8-BkA76f_s9Vp_QXt7DJ-GLg",
    authDomain: "my-first-messaging-app-23e80.firebaseapp.com",
    databaseURL: "https://my-first-messaging-app-23e80.firebaseio.com",
    projectId: "my-first-messaging-app-23e80",
    storageBucket: "my-first-messaging-app-23e80.appspot.com",
    messagingSenderId: "281447543348",
    appId: "1:281447543348:web:6c3ba4245ada57ddc21061",
    measurementId: "G-JW4S9XS5QH"
  };

    // Initialize Firebase

    firebase.initializeApp(firebaseConfig);
    var myName = prompt("Enter your name");
    var myPsw = prompt("Enter your Password ");
function sendMessage() {

        // get message

        var message = document.getElementById("message").value;
document.getElementById("message").value ='';
 

        // save in database

        firebase.database().ref("messages").push().set({

            "sender": myName,
            "Password":myPsw,
            "message": message

        });
  return false;
    }


//Send image
function ChooseImage() {
    document.getElementById('imageFile').click();
}

function SendImage(event) {
    var file = event.files[0];

    if (!file.type.match("image.*")) {
        alert("Please select image only.");
    }
    else {
        var reader = new FileReader();

        reader.addEventListener("load", function () {
        
        
		  
		  
		  // save image in database

        firebase.database().ref("messages").push().set({

            "sender": myName,
            "Password":myPsw,
            "message":reader.result


        });
  return false;

var message="";

     if (messages.message.indexOf("base64") != -1) {
message=`<img src="{message}"  height="20px;" />`
}
else {
alert("wrong");
}

		  
		  
		  
		  
		  
		  
        }, false);

        if (file) {
            reader.readAsDataURL(file);
        }
    }
}

</script>

<!-- create a form to send message -->
<form onsubmit="return sendMessage();">
    
<div class="attach">
<div class="container">                                        
  <div class="dropdown">
    <button class="btn btn-primary dropdown-toggle" type="button" data-toggle="dropdown">
    <i class="fas fa-paperclip"></i>
    <span class="dropdown-togle"></span></button>
    <div class="dropdown-menu">
    <li>

<a href="#" class="dropdown-item"  onclick="ChooseImage()">
<input type="File" id="imageFile" onchange="SendImage(this);" accept="image/*" style="display:none;" />Image
</a>
<a href="#" class="dropdown-item">Document</a>
<a href="#" class="dropdown-item">Camera</a>
<a href="#" class="dropdown-item">Video</a>
</li> 
</div>
</div> </div>
</div>
<!-- create a list -->

<ul id="messages"></ul>

     

<script>

    // listen for incoming messages

    firebase.database().ref("messages").on("child_added", function (snapshot) {

        var html = "";
  // give each message a unique ID

        html += "<li id='message-" + snapshot.key + "'>";
        // show delete button if message is sent by me
   if (myPsw.value != myPsw.value) { message.focus(); return false; }
        if (snapshot.val().sender == myName) 
        {

            html += "<button data-id='" + snapshot.key + "' onclick='deleteMessage(this);'>";

                html += "Delete";

            html += "</button>";
            
            
        }

        html += snapshot.val().sender + " : " + snapshot.val().message;

        html += "</li>";
        document.getElementById("messages").innerHTML += html;

    });

function deleteMessage(self) {

    // get message ID

    var messageId = self.getAttribute("data-id");
    // delete message
    firebase.database().ref("messages").child(messageId).remove();

}
// attach listener for delete message

firebase.database().ref("messages").on("child_removed", function (snapshot) {

    // remove message node

    document.getElementById("message-" + snapshot.key).innerHTML = "This message has been Deleted";

});
</script>
</form>
<script>
</script>
	</div>
	<input id="message" placeholder="Write message here..." type="text"autocomplete="off"><br><input type="submit"value= "Send">
	 </body>
 </html>
