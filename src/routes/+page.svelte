<svelte:head>
  <title>Alessandra Belló: Personal site and portfolio</title>
</svelte:head>

<h1>Alessandra Belló Soares</h1>

<script>
  import { onMount } from "svelte";

  let githubData = null;
  let loading = true;
  let error = null;

  onMount(async () => {
      try {
          const response = await fetch("https://api.github.com/users/AlessandraBello");
          githubData = await response.json();
      } catch (err) {
          error = err;
      }
      loading = false;
  });

  let profileData = fetch("https://api.github.com/users/AlessandraBello");
</script>

{#await profileData}
  <p>Loading...</p>
{:then response}
  {#await response.json()}
    <p>Decoding...</p>
  {:then data} 
    <section>
      <h2>My Github Stats</h2>
      <dl>
        <dt>Followers</dt>
        <dd>{data.followers}</dd>
        <dt>Following</dt>
        <dd>{data.following}</dd>
        <dt>Public Repos</dt>
        <dd>{data.public_repos}</dd>
      </dl>
    </section>
  {:catch error}
    <p class="error">Something went wrong: {error.message}</p>
  {/await}
  {:catch error}
    <p class="error">Something went wrong: {error.message}</p>
{/await}
<img src = "Alecaca.jpg" alt = "My dog" width="400">

<p>Graduanda em Ciência de Dados e Inteligência Artificial pela Fundação Getulio Vargas e técnica em administração pelo IFRS - Campus Canoas. </p>

<p>Desde pequena gostava muito de matemática e fui 4 vezes medalhista da OBMEP. Comecei a minha trajetória acadêmica no IFRS - Campus Canoas, onde pude ter os primeiros contatos com uma formação profissional e participar de atividades extra-curriculares. Em 2022 entrei na UFRGS para cursar estatística e no final do ano, como reconhecimento pelas medalhas obtidas, fui convidada pelo Programa Seleção de Talentos do CDMC para estudar na FGV - RJ com bolsa de estudos integral. Optei por vir para o Rio de Janeiro pois aqui eu estaria mais próxima do mercado de trabalho, além de ter contato maior com a área de programação.</p> 
        
<p>No ano de 2023 realizei um intercâmbio para Londres, onde estudei inglês por 3 semanas. Durante o intercâmbio fiquei em uma casa de família, onde tive contato direto com a cultura e rotina dos hosts.</p>
        
<p>Possuo inglês intermediário e conhecimento de pacote Office, Python, C++ e SQL. Gosto de conhecer novas culturas e lugares, sou empática e ágil para resolver problemas.</p>