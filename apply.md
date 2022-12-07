---
id: dotRP-Apply
---

# dotRP Apply




<form onsubmit="handleFormSubmit(event)">
  <input type="hidden" name="code" placeholder="GiegdHqaQKE2grIE-yL_ud7F9LBUZpy_ZCWeOTivD-5ZAzFunKRe3Q==" />
  <input type="text" name="DID" placeholder="DiscordID" />
  <input type="hidden" name="catID" placeholder="1027660616481112114"  />
  <input type="hidden" name="DG" placeholder="412414497790361602" />
  <input type="hidden" name="STF" placeholder="955262072369868860"  />
  <input type="text" name="CNAME" placeholder="Char Name" />
  <input type="text" name="DESC" placeholder="Around 300 words about your charater"  />
  <input type="radio" name="CUT" id="cut" value="cut" />
  <label for="CUT">I Understand CUT</label><br>
  <input type="text" name="SM" placeholder="Socials" />

<button type="submit">Submit</button>  
</form>


<script>
  function handleFormSubmit(event) {
    // Prevent the default form submission behavior
    event.preventDefault();

    // Get the form data
    const data = new FormData(event.target);

    // Use the data to make a GET request (or use any other method you want)
    fetch('https://api.dotroleplay.com/api/dotrpapp?', {
      method: 'GET'
    });
  }
</script>  
