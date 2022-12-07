---
id: dotRP-Apply
---

# dotRP Apply

<style>
  /*Add some basic styling to the form*/
  form {
    margin: 20px 0;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
  }
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

  /*Style the input fields*/
  input[type="text"], input[type="email"] {
    width: 100%;
    padding: 12px;
    border: 1px solid #ccc;
    border-radius: 5px;
    margin-bottom: 10px;
  }

  /*Style the submit button*/
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

<form action="https://api.dotroleplay.com/api/dotrpapp?" method="get" onsubmit="redirectToThankYouPage()">
<form onsubmit="handleFormSubmit(event)">
  <input type="hidden" name="code" value="GiegdHqaQKE2grIE-yL_ud7F9LBUZpy_ZCWeOTivD-5ZAzFunKRe3Q==" />
  <input type="text" name="DID" placeholder="DiscordID" />
  <input type="hidden" name="catID" value="1027660616481112114"  />
  <input type="hidden" name="DG" value="412414497790361602" />
  <input type="hidden" name="STF" value="955262072369868860"  />
  <input type="text" name="CNAME" placeholder="Char Name" />
  <textarea rows="5" cols="80" id="textarea" name="desc">"Around 300 words about your character"</textarea>
  <input type="radio" name="CUT" id="cut" value="cut" />
  <label for="CUT">I Understand CUT</label><br>
  <input type="text" name="SM" placeholder="Socials" />

<button type="submit">Submit</button>  
</form>
<script>
  function redirectToThankYouPage() {
    window.location = "https://docs.dotroleplay.com";
  }
</script>
