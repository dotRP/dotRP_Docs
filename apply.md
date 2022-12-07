---
id: dotRP-Apply
---

# dotRP Apply Bellow


<style>
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

<form onsubmit="handleFormSubmit(event)">
<input type="hidden" name="code" placeholder="GiegdHqaQKE2grIE-yL_ud7F9LBUZpy_ZCWeOTivD-5ZAzFunKRe3Q==" />

  <input type="text" name="DID" placeholder="DiscordID" />
  <input type="hidden" name="catID" placeholder="1027660616481112114"  />
  <input type="hidden" name="DG" placeholder="412414497790361602" />


<input type="hidden" name="STF" placeholder="955262072369868860"  />
  <input type="text" name="CNAME" placeholder="Char Name" />
  <input type="text" name="DESC" placeholder="Around 300 yours about your charater"  />
  <form>
  <input type="radio" name="CUT" id="cut" value="cut" />
  <label for="CUT">I Understand CUT</label><br>
  </form>
<input type="text" name="SM" placeholder="Socials" />
  

  
</form>

<button type="submit">Submit</button>
<script>
  function handleFormSubmit(event) {
    // Prevent the default form submission behavior
    event.preventDefault();

    // Get the form data
    const data = new FormData(event.target);

    // Use the data to make a GET request (or use any other method you want)
    fetch('https://apiv3.m2s.bz/api/dotrpapp?', {
      method: 'GET',
      body: data
    });
  }
</script>