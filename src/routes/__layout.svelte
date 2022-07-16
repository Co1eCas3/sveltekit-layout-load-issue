<script context="module">
  export async function load() {
    console.log("load");
    return {
      props: { someVar: "I'm a `load()` prop!" },
    };
  }
</script>

<script>
  export let someVar;
  $: console.log("someVar: ", someVar);

  function changeSomeVar() {
    console.log("editing someVar");
    someVar += " changed!";
  }
</script>

<main>
  <header>
    <h1>{someVar}</h1>
    <button on:click={changeSomeVar}>Change the prop</button>
  </header>

  <section>
    <slot />
  </section>
</main>
