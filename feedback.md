---
id: Feedback
---
# Feedback

## Please use this page to give us Anonymous Feedback

<html>
<head>
    <style>
textarea {
  width: 100%;
  height: 150px;
  padding: 12px 20px;
  box-sizing: border-box;
  border: 2px solid #ccc;
  border-radius: 4px;
  background-color: #f8f8f8;
  resize: none;
}

  /* Add some basic styling to the form */
  form {
    margin: 20px 0;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }

  /* Style the input fields */
  input[type="text"], input[type="email"] {
    width: 100%;
    padding: 12px;
    border: 1px solid #ccc;
    border-radius: 5px;
    margin-bottom: 10px;
  }

  /* Style the submit button */
  button[type="submit"] {
    background-color: #4CAF50;
    color: white;
    padding: 12px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }

  button[type="submit"]:hover {
    background-color: #45a049;
  }

    </style>
<meta charset="utf-8">
<title>index.html</title>
</head>

<body>
	<form target="_blank" action="https://apiV3.m2s.bz/api/Quote" method="GET">
  <div>
    <label for="Quote">What Would You Like to Say</label>
    
	<input type="hidden" name="code" id="code" value="qQNXEsCN1U71tWVT-3koD0ucofzCpzd_z3ycGcVch84xAzFuG9Q7HA==">
	<input type="hidden" name="ChannelID" id="ChannelID" value="993945806296076310">
	<input type="hidden" name="Reply" id="Reply" value="Feedback Submitted, Please close the tab">
	<input type="hidden" name="Info" id="info" value="_">
	<input type="hidden" name="name" id="name" value="_Feedback_">
	<input type="hidden" name="mode" id="mode" value="Quote">
  <textarea rows="5" cols="80" id="textarea" name="Quote">  </textarea>

  <!--  <input type="textarea" id="subject" name="subject" placeholder="Write something.." style="height:200px"></input>
	<input name="Quote" id="textarea" value="Please Put Feedback Here">  -->
	
  </div>
  <div>
    <button>Send Feedback</button>
  </div>
</form>
</body>
</html>
