<template>
  <article class="about">
    <div class="title app-width-padding">Editorial segmentation</div>
    <div class="about-content app-width-padding">
      <h2>Collection, play, act, scene, individual speech, line</h2>
      <p>
        The aim is to be able to describe, quote and republish : a play, an act, a scene, a indivudual speech, possibly a stanza or a verse.
      </p>
      <p>
        The hierarchy is as follows:
      </p>
      <pre>
theater                                   collection (level 1)
  > author                                collection (level 2)
    > play                                document
      > act                               fragment (level 1)
        > scene                           fragment (level 2)
          > individual speech             fragment (level 3)
            > stanza ?                    fragment (level 4 ?)
              > verse ?                   fragment (level 4/5 ?)
      </pre>
      <p>Not all plays have the same editorial structure: some are versified, others not. Each semantic level (act, scene, etc.) does not necessarily coincide with the same level of depth.
        Rather than dividing our editions using the numerical depth index (<code>level</code>), we'll learn to use its semantic descriptor (<code>citeType</code>).
      </p>

      <table class="table is-striped is-hoverable is-bordered is-fullwidth">
          <thead>
            <tr>
              <th>XPath</th>
              <th><code>citeType</code></th>
              <th>level</th>
              <th>moliere_avare</th>
              <th>moliere_dom-juan</th>
              <th>moliere_tartuffe</th>
              <th>racine_andromaque</th>
              <th>racine_phedre</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><code>div[@type="acte"]</code></td>
              <td><code>act</code></td>
              <td>1</td>
              <td>X</td>
              <td>X</td>
              <td>X</td>
              <td>X</td>
              <td>X</td>
            </tr>
            <tr>
              <td><code>div[@type="scene"]</code></td>
              <td><code>scene</code></td>
              <td>2</td>
              <td>X</td>
              <td>X</td>
              <td>X</td>
              <td>X</td>
              <td>X</td>
            </tr>
            <tr>
              <td><code>sp</code></td>
              <td><code>individual_speech</code></td>
              <td>3</td>
              <td>X</td>
              <td>X</td>
              <td>X</td>
              <td>X</td>
              <td>X</td>
            </tr>
            <tr>
              <td><code>sp/l</code></td>
              <td><code>verse</code></td>
              <td>4</td>
              <td>-</td>
              <td>-</td>
              <td>X</td>
              <td>X</td>
              <td>X</td>
            </tr>
            <tr>
              <td><code>sp/p/s</code></td>
              <td>not defined</td>
              <td>-</td>
              <td>X</td>
              <td>X</td>
              <td>-</td>
              <td>-</td>
              <td>-</td>
            </tr>
          </tbody>
      </table>





      <hr>
      <h2>Define editorial segmentation for display</h2>
      <p>
        <b>Découpage à l’acte</b>
      </p>
      <p>
        <b>Découpage à la scène</b>
      </p>
      <h2>Table of contents depth</h2>
      <p>
        Independently of this editorial segmentation, it is possible to define the depth of a document's table of contents (TOC) using
        the <code>tableOfContentDepth</code> query parameter.
      </p>
      <p>
        <b>TODO</b>
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
