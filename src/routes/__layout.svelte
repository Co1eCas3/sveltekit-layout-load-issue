<script context="module">
  export async function load() {
    return {
      props: { someVar: "something" },
    };
  }
</script>

<script>
  export let someVar;
</script>

<main>
  <header>
    <h1>{someVar}</h1>
    <button on:click={() => (someVar += " else")}>Change somevar</button>
  </header>

  <section>
    <slot />
  </section>
</main>
