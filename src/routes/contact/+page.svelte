<svelte:head>
  <title>Me contate</title>
</svelte:head>

<h1>Contato</h1>

<form action="mailto:alessandrabellosoares@gmail.com" method="GET">
    <label for="email">Email:</label> <br>
    <input name="email" type="email"> <br>
    <label for="subject">Subject:</label> <br>
    <input name="subject" type="text"> <br>
    <label for="body">Body:</label> <br>
    <textarea name="body"></textarea> <br>
    <button>Submit</button>
</form>