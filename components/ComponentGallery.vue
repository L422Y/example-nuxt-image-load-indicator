<template>
  <section>
    <article id="images">
      <template v-for="x in '12q34567890qwertyuiopasdfghjkl'">
        <SwiftImg
          :src="`https://cataas.com/cat/cute?${x}&width=100&height=100`"
          width="100"
          height="100"
        />
      </template>
    </article>
  </section>
</template>
<style>
article#images {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  justify-content: center;
}
</style>
