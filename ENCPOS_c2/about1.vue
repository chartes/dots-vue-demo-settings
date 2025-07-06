<template>
  <article class="about">
    <div class="title app-width-padding">Collection, document, fragment: editorial segmentation</div>
    <div class="about-content app-width-padding">
      <h2>Thesis abstract as a fragment</h2>
      <p>
        In this case, the publisher wishes to emphasize the material structuring of the corpus: each year is a volume considered as a document.
        Consequently, each position becomes a fragment of this document.
      </p>
      <p>
        The hierarchy is as follows:
      </p>
      <pre>
encpos_c2                   collection (level 1)
  > year                    document
    > abstract              fragment (level 1)
      > section             fragment (level 2, i.e. part)
        > sub-section       fragment (level 3, i.e. chapter)
      </pre>
      <p>NB. The editorial structure of this recipe (Thesis abstract, case 2) offers less flexibility than the other (Thesis abstract, case 1).
        With a single level 1 collection, we don't have the option of defining specific settings for each annual volume (document, not collection).
      </p>
      <h2>Define editorial segmentation for display</h2>
      <p>
        The various fragments (abstract, part, chapter) of each volume are declared in the endpoint Navigation response, for example:
        <a href="https://dots.chartes.psl.eu/demo/api/dts/navigation?resource=ENCPOS_1972_c2&down=-1" target="_blank">https://dots.chartes.psl.eu/demo/api/dts/navigation?resource=ENCPOS_1972_c2&down=-1</a>
      </p>
      <p>
        Would you like to consult the all annual volume on a single page? Or do you want to browse by abstract, part or chapter?
        You can define this editorial segmentation for each collection in its JSON configuration file, using the <code>editByLevel</code> parameter.
      </p>
      <p>
        In this recipe, we choose to leaf through the collection at the thesis abstract level.
      </p>
      <h2>Table of contents depth</h2>
      <p>
        Independently of this editorial segmentation, it is possible to define the depth of a document's table of contents (TOC) using
        the <code>tableOfContentDepth</code> query parameter.
      </p>
      <p>
        No need to define this depth level for our collection (<code>encpos_c2.conf.json</code>), since we inherit the setting
        defined in the project's default configuration in <code>custom.conf.json</code>: <code>"tableOfContentDepth": 5</code>
      </p>
    </div>
  </article>

</template>
<script>
export default {
  name: 'AboutSecondSection',

  setup () {
  }
}
</script>
<style scoped>
</style>
