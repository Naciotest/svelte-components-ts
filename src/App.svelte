<script lang="ts">
  import { Accordion, AccordionItem } from './lib/components/acoordion';
  import Button from './lib/components/button/button.svelte';

  const items = [
    {title: "item 1", content: "Content 1"},
    {title: "item 2", content: "Content 2"},
    {title: "item 3", content: "Content 3"},
    {title: "item 4", content: "Content 4"},
    {title: "item 5", content: "Content 5"},
  ]
</script>

<header>
  <section>
    <h1>
      <span>Hero layout with</span>
    </h1>
    <p data-ui="outline size">Lorem ipsum dolor sit amet consectetur adipisicing elit. Expedita, voluptatem eveniet illo provident doloribus ab soluta placeat cum assumenda! Magnam explicabo repellendus nostrum corrupti accusantium reprehenderit nobis odit autem eveniet.</p>
    <div class="button-list">
      <Button disabled={true}>Hola</Button>
      <Button variant="primary" disabled={true}>Hola</Button>
    </div>
    <Accordion>
      {#each items as item}
      <AccordionItem>
        <svelte:fragment slot="title">{item.title}</svelte:fragment>
        <small slot="subtitle">Subtitle</small>
        <svelte:fragment slot="content">{item.content}</svelte:fragment>
      </AccordionItem>
      {/each}
    </Accordion>
  </section>
  <picture class="promo-art">
    <img src="https://opendoodles.s3-us-west-1.amazonaws.com/selfie.svg" height="700" width="700" alt="a random doodle">
  </picture>
</header>

<style>
  header {
    display: grid;
    align-items: center;
    grid-template-columns: 1fr 1fr;
    background: var(--surface-1);
  }
  section {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }
  h1 span {
    font-family: Jost, sans-serif;
    font-weight: bold;
    font-size: var(--font-size-fluid-3);
    background-image: linear-gradient(var(--primary), var(--white));
    background-clip: text;
    color: transparent;
  }
  :root {
    --accordion-width: 100%;
  }
</style>
