<template>
  <article class="about">
    <div class="title app-width-padding">What is DoTS-Vue?</div>
    <div class="about-content app-width-padding">
      <h2></h2>
      <p>
        DoTS-Vue is a frontend application to browse a DTS DoTS endpoint.
      </p>
      <p>
        DoTS-Vue is a frontend application, based on the JavaScript framework <a href="https://vuejs.org/" target="_blank">vue.js</a>, to browse a DTS DoTS endpoint.
DoTS-vue helps editors and researchers display text collections published through DoTS in a modern web application.
      </p>
      <p>
        DoTS-vue was released under the MIT license by the Mission projets numériques of the <a href="https://www.chartes.psl.eu/" target="_blank">École nationale des chartes – PSL</a>, with financial support from the digital infrastructure <a href="https://projet.biblissima.fr/" target="_blank">Biblissima+</a>.
      </p>
      <h2>Capabilities</h2>
      <p>
        With DoTS-vue, you can:
      </p>
      <ul>
        <li>Define the editorial segmentation used to display texts in each collection — either by structural level or semantic division (e.g., acts, scenes).</li>
        <li>Set the depth of a document’s table of contents.</li>
        <li>Choose the format in which a document is displayed: XML/TEI (default) or HTML.</li>
        <li>Style the API response using the default TEI Consortium CSS stylesheet, or apply your own custom CSS.</li>
        <li>Select which collections to display — or exclude those you don't want to show.</li>
      </ul>
    </div>
  </article>

</template>
<script>
export default {
  name: 'AboutThirdSection',

  setup() {
  }
}
</script>
<style scoped>
</style>
