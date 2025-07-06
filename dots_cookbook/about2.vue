<template>
  <article class="about">
    <div class="title app-width-padding">What is DoTS?</div>
    <div class="about-content app-width-padding">
      <h2></h2>
      <p>DoTS is an XQuery implementation of the DTS (<a href="https://distributed-text-services.github.io/specifications/" target="_blank">Distributed Text Services</a>)
        API specification, based on the <a href="https://basex.org/" target="_blank">BaseX</a> XML database software.</p>
      <p>
        DoTS makes it easy to publish sources in XML/TEI according to the FAIR (Findable, Accessible, Interoperable, Reusable) principles.
      </p>
      <p>
        <a href="https://chartes.github.io/dots_documentation/" target="_blank">DoTS Documentation</a>
      </p>
      <p>
        TODO: Crédits, Licence, ENC, Biblissima+
      </p>
      <h2>Capabilities</h2>
      <p>
        Using DoTS, you can
      </p>
      <ul>
        <li>with the DTS Collection endpoint:
          <ul>
            <li>Retrieve lists of collection members.</li>
            <li>Retrieve metadata about individual collection items.</li>
          </ul>
        </li>
        <li>with the DTS Navigation endpoint:
          <ul>
            <li>Retrieve lists of citeable passages within a text.</li>
            <li>Retrieve a range of citeable passages within a text.</li>
            <li>Retrieve metadata about the citation structure of a document.</li>
          </ul>
        </li>
        <li>with the DTS Document endpoint:
          <ul>
            <li>Retrieve a single text passage at any level of the citation hierarchy.</li>
            <li>Retrieve a range of text passages with a clearly defined start and end passage.</li>
            <li>Retrieve an entire text.</li>
          </ul>
        </li>
      </ul>
    </div>
  </article>

</template>
<script>
export default {
  name: 'AboutSecondSection',

  setup() {
  }
}
</script>
<style scoped>
</style>
