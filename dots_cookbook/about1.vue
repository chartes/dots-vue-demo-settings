<template>
  <article class="about">
    <div class="title app-width-padding">What is DTS?</div>
    <div class="about-content app-width-padding">
      <h2></h2>
      <p>
        "The Distributed Text Services (DTS) Specification defines an API for working with collections of text as
        machine-actionable data."
      </p>
        <p>
          "Publishers of digital text collections can use the DTS API to help them make their textual data Findable,
          Accessible, Interoperable and Reusable (FAIR)."
        </p>
      <p>
        > <a href="https://distributed-text-services.github.io/specifications/" target="_blank">https://distributed-text-services.github.io/specifications/</a>
      </p>
      <blockquote>
        <p>
          DTS specifies 3 distinct operation endpoints:
        </p>
        <ul>
          <li>Navigation across texts is supported by the <a href="https://distributed-text-services.github.io/specifications/versions/unstable/#collection-endpoint" target="_blank">Collection Endpoint</a></li>
          <li>Navigation within a text is supported by the <a href="https://distributed-text-services.github.io/specifications/versions/unstable/#navigation-endpoint" target="_blank">Navigation Endpoint</a></li>
          <li>Retrieval of complete or partial texts is supported by the <a href="https://distributed-text-services.github.io/specifications/versions/unstable/#document-endpoint" target="_blank">Document Endpoint</a></li>
        </ul>
        <p>
          The Collection and Navigation endpoints return JSON-LD. The Document endpoint is specified to return TEI/XML of the requested text or fragment.
        </p>
      </blockquote>
    </div>
  </article>

</template>
<script>
export default {
  name: 'AboutFirstSection',

  setup() {
  }
}
</script>
<style scoped>
</style>
