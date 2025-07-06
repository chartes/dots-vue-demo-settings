<template>
  <article class="about">
    <div class="title app-width-padding">Features covered in this recipe</div>
    <div class="about-content app-width-padding">
      <h2>Data format selection</h2>
      <p>
        By default, when displaying a document or a fragment, the response format of the DTS Document endpoint is XML/TEI.
        DoTS, thanks to the <code>mediaType</code> request parameter, can deliver a document or a fragment in HTML format.
      </p>
      <p>
        For each collection, the JSON configuration file allows you to define the format (XML/TEI or HTML) using the <code>mediaTypeEndpoint</code> parameter.
      </p>
      <p>
        We choose the HTML format. But we don't need to specify it in this collection's configuration file (<code>encpos_c2.conf.json</code>)
        since the setting is already defined by default in the <code>custom.conf.json</code> file : <code>"mediaTypeEndpoint": "html"</code>.
      </p>
      <p>
        To understand this settings cascade, see Overview tab.
      </p>
    </div>
  </article>

</template>
<script>
export default {
  name: 'AboutThirdSection',

  setup () {
  }
}
</script>
<style scoped>
</style>
