<script context="module">
  export async function load() {
    console.log("load");
    return {
      props: { someVar: "something" },
    };
  }
</script>

<script>
  export let someVar;
  $: console.log("someVar: ", someVar);

  function changeSomeVar() {
    console.log("editing someVar");
    someVar += " else;";
  }
</script>

<main>
  <header>
    <h1>{someVar}</h1>
    <button on:click={changeSomeVar}>Change somevar</button>
  </header>

  <section>
    <slot />
  </section>
</main>
