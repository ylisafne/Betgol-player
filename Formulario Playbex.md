# API End Point
| Enviroment | Base URL | Path | Token |
|----------|----------|----------|-----|
| DEV | https://dev.betgolperu.com | /util/crm/lead | send in private message
| PRD | https://betgolperu.com | /util/crm/lead | send in private message


# Datos de Formulario

## Form Example (inputs names is required like an example)

```
<form id="contactForm">
    <div class="form-field">
      <label for="name">Subject</label>
      <input id="name" name="name" type="text" required>
    </div>
    <div class="form-field">
      <label for="phone">Phone</label>
      <input id="phone" name="phone" type="tel">
    </div>
    <div class="form-field">
      <label for="email">Email</label>
      <input id="email" name="email_from" type="email">
    </div>
    <div class="form-field">
      <label for="city">City</label>
      <input id="city" name="city" type="text">
    </div>
    <div class="form-field">
      <label for="company">Company</label>
      <input id="company" name="partner_name" type="text">
    </div>
    <div class="form-field">
      <label for="description">Message</label>
      <textarea id="description" name="description"></textarea>
    </div>
    <button type="submit">Send</button>
  </form>
```

## Javascript 
Best Practice: First, ensure that your JavaScript code is properly adjusted. Then, minify or obfuscate it to safeguard your logic and prevent unauthorized access.
```
<script>
    const form = document.getElementById("contactForm");
	const baseUrl = "https://dev.betgolperu.com"
	//Begin User only for example
	const msgBox = document.getElementById("message");
	//end User only for example
	
    form.addEventListener("submit", async (e) => {
      e.preventDefault();
      msgBox.style.display = "none";

      // Construye payload desde el form
      const fd = new FormData(form);
      const payload = Object.fromEntries(fd.entries());

      const myHeaders = new Headers();
      myHeaders.append("Content-Type", "application/json");
      // Warning: Do not hardcode your API tokens or credentials directly in the source code. this example works only on DEV enviroment
      myHeaders.append("Authorization", "Bearer tokenHere"); 
      
      const requestOptions = {
        method: "POST",
        headers: myHeaders,
        body: JSON.stringify(payload),
        redirect: "follow"
      };

      try {
        const response = await fetch(baseUrl + "/util/crm/lead", requestOptions);
        const data = await response.json().catch(() => ({}));
        const result = data.result || data;
		
		//Begin show example box
        msgBox.style.display = "block";
		//end show example box
        if (result.ok) {
			// Code to run on success
          msgBox.className = "success";
          msgBox.textContent = `✅ Lead creado con ID ${result.id}`;
          form.reset();
        } else {
			// Code to run on failed
          msgBox.className = "error";
          msgBox.textContent = `❌ Error: ${result.error || "No se pudo enviar"}`;
        }
      } catch (err) {
		// Code to run on error
        msgBox.style.display = "block";
        msgBox.className = "error";
        msgBox.textContent = "❌ Error de conexión con el servidor";
        console.error(err);
      }
    });
</script>
```



## Full example 
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Create CRM Lead (Postman style)</title>
  <style>
    body { font-family: Arial, sans-serif; padding: 20px; max-width: 600px; margin: auto; }
    .form-field { margin-bottom: 15px; }
    label { display: block; margin-bottom: 5px; font-weight: bold; }
    input, textarea { width: 100%; padding: 8px; box-sizing: border-box; }
    button { padding: 10px 20px; cursor: pointer; }
    #message { margin-top: 15px; padding: 10px; display: none; }
    #message.success { background: #e6ffe6; color: #006600; }
    #message.error { background: #ffe6e6; color: #990000; }
  </style>
</head>
<body>
  <h1>Contact Form → Odoo Lead</h1>

  <form id="contactForm">
    <div class="form-field">
      <label for="name">Subject</label>
      <input id="name" name="name" type="text" required>
    </div>
    <div class="form-field">
      <label for="phone">Phone</label>
      <input id="phone" name="phone" type="tel">
    </div>
    <div class="form-field">
      <label for="email">Email</label>
      <input id="email" name="email_from" type="email">
    </div>
    <div class="form-field">
      <label for="city">City</label>
      <input id="city" name="city" type="text">
    </div>
    <div class="form-field">
      <label for="company">Company</label>
      <input id="company" name="partner_name" type="text">
    </div>
    <div class="form-field">
      <label for="description">Message</label>
      <textarea id="description" name="description"></textarea>
    </div>
    <button type="submit">Send</button>
  </form>

  <div id="message"></div>

  <script>
    const form = document.getElementById("contactForm");
	const baseUrl = "https://dev.betgolperu.com"
	//Begin User only for example
	const msgBox = document.getElementById("message");
	//end User only for example
	
    form.addEventListener("submit", async (e) => {
      e.preventDefault();
      msgBox.style.display = "none";

      // Construye payload desde el form
      const fd = new FormData(form);
      const payload = Object.fromEntries(fd.entries());

      const myHeaders = new Headers();
      myHeaders.append("Content-Type", "application/json");
      // Warning: Do not hardcode your API tokens or credentials directly in the source code. this example works only on DEV enviroment
      myHeaders.append("Authorization", "Bearer tokenHere"); 
      
      const requestOptions = {
        method: "POST",
        headers: myHeaders,
        body: JSON.stringify(payload),
        redirect: "follow"
      };

      try {
        const response = await fetch(baseUrl + "/util/crm/lead", requestOptions);
        const data = await response.json().catch(() => ({}));
        const result = data.result || data;
		
		//Begin show example box
        msgBox.style.display = "block";
		//end show example box
        if (result.ok) {
			// Code to run on success
          msgBox.className = "success";
          msgBox.textContent = `✅ Lead creado con ID ${result.id}`;
          form.reset();
        } else {
			// Code to run on failed
          msgBox.className = "error";
          msgBox.textContent = `❌ Error: ${result.error || "No se pudo enviar"}`;
        }
      } catch (err) {
		// Code to run on error
        msgBox.style.display = "block";
        msgBox.className = "error";
        msgBox.textContent = "❌ Error de conexión con el servidor";
        console.error(err);
      }
    });
    </script>
</body>
</html>

```
