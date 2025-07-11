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
      <pre class="desktop">
theater                                   collection (level 1)
  > author                                collection (level 2)
    > play                                document
      > act                               fragment (level 1)
        > scene                           fragment (level 2)
          > individual speech             fragment (level 3)
            > stanza ?                    fragment (level 4 ?)
              > verse ?                   fragment (level 4/5 ?)
      </pre>
      <pre class="responsive">
theater             collection level 1
> author            collection level 2
 > play             document
  > act             fragment level 1
   > scene             "     level 2
    > indiv. speech    "     level 3
     > stanza ?        "     level 4 ?
      > verse ?        "     lvl 4/5 ?
      </pre>
      <p>Not all plays have the same editorial structure: some are versified, others not. Each semantic level (act, scene, etc.) does not necessarily coincide with the same level of depth.
        Rather than dividing our editions using the numerical depth index (<code>level</code>), we'll learn to use its semantic descriptor (<code>citeType</code>).
      </p>
      <!-- Table responsive -->
      <div class="table-container desktop mt-5">
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
      </div>
       <!-- Table responsive -->
      <div class="table-container responsive mt-5">
        <table class="table is-hoverable is-fullwidth">
          <thead>
            <tr>
              <th>XPath</th>
              <th>Details</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><code>div[@type="acte"]</code></td>
              <td>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>citeType</b></span>
                  <span><code>act</code></span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>level</b></span>
                  <span>1</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>moliere_avare</b></span>
                  <span>X</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>moliere_dom-juan</b></span>
                  <span>X</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>moliere_tartuffe</b></span>
                  <span>X</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>racine_andromaque</b></span>
                  <span>X</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>racine_phedre</b></span>
                  <span>X</span>
                </div>
              </td>
            </tr>
            <tr>
              <td><code>div[@type="scene"]</code></td>
              <td>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>citeType</b></span>
                  <span><code>scene</code></span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>level</b></span>
                  <span>2</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>moliere_avare</b></span>
                  <span>X</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>moliere_dom-juan</b></span>
                  <span>X</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>moliere_tartuffe</b></span>
                  <span>X</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>racine_andromaque</b></span>
                  <span>X</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>racine_phedre</b></span>
                  <span>X</span>
                </div>
              </td>
            </tr>
            <tr>
              <td><code>sp</code></td>
              <td>
                <div class="is-flex is-justify-content-space-between">
                  <span class="no-min-width"><b>citeType</b></span>
                  <span class="no-min-width"><code>individual_speech</code></span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>level</b></span>
                  <span>3</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>moliere_avare</b></span>
                  <span>X</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>moliere_dom-juan</b></span>
                  <span>X</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>moliere_tartuffe</b></span>
                  <span>X</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>racine_andromaque</b></span>
                  <span>X</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>racine_phedre</b></span>
                  <span>X</span>
                </div>
              </td>
            </tr>
            <tr>
              <td><code>sp/l</code></td>
              <td>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>citeType</b></span>
                  <span><code>verse</code></span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>level</b></span>
                  <span>4</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>moliere_avare</b></span>
                  <span>-</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>moliere_dom-juan</b></span>
                  <span>-</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>moliere_tartuffe</b></span>
                  <span>X</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>racine_andromaque</b></span>
                  <span>X</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>racine_phedre</b></span>
                  <span>X</span>
                </div>
              </td>
            </tr>
            <tr>
              <td><code>sp/p/s</code></td>
              <td>
                <div class="is-flex is-justify-content-space-between">
                  <span class="no-min-width"><b>citeType</b></span>
                  <span class="no-min-width">not defined</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>level</b></span>
                  <span>-</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>moliere_avare</b></span>
                  <span>X</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>moliere_dom-juan</b></span>
                  <span>X</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>moliere_tartuffe</b></span>
                  <span>-</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>racine_andromaque</b></span>
                  <span>-</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>racine_phedre</b></span>
                  <span>-</span>
                </div>
              </td>
            </tr>
          </tbody>
        </table>
      </div>






      <hr>
      <h2>Define editorial segmentation for display</h2>
      <p>
        You may want to consult the plays according to their semantic structure — for example, by act or by scene. This editorial segmentation can be defined for each collection in its JSON configuration file using the <code>editByCiteType</code> parameter.
        Different cases are illustrated in this recipe:
      </p>
      <ul>
          <li>All plays by Racine are segmented by <b>act</b>: <code>editByCiteType: "act"</code></li>
          <li>All plays by Molière are segmented by <b>scene</b>: <code>"editByCiteType": "scene"</code></li>
      </ul>
      <p>Instead of defining the segmentation semantically, you can also specify it numerically using the <code>level</code> value (from the DTS Navigation endpoint), via the <code>editByLevel</code> parameter.
        This feature is demonstrated in the <a href="https://dots.chartes.psl.eu/cookbook/ENCPOS/about">Thesis abstract, case 1</a> recipe.
      </p>

      <h2>Table of contents depth</h2>
      <p>
        Independently of this editorial segmentation, it is possible to define the depth of a document's table of contents (TOC) using
        the <code>tableOfContentDepth</code> query parameter.
      </p>
      <p>
        Independently of this editorial segmentation, it is possible to define the depth of a document's table of contents (TOC) using the <code>tableOfContentDepth</code> query parameter.
        For example, for the plays by Racine, segmented by act (level 1), their TOC are detailed at scene level (level 2).
      </p>
      <p>DoTS-Vue automatically provides a link for each TOC item according to the scenario: fragment link if the level corresponds to the editorial segmentation, anchor if the level is finer than this segmentation.
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
table {
  width:100%;
  text-align: center;
  font-size: 12px;
}
table td,
table th {
  white-space: nowrap;
  text-align: left;
  padding: 0.10rem 0.10rem;
  & > b, > div > span > b {
    color:black;
    font-weight: bolder;
  }
  & > div > span:not(.no-min-width)  {
    min-width: 70%;
  }
}
table td:last-child {
  width:100%;
}
.responsive {
  display: none;
}

@media screen and (max-width: 500px) {
  .desktop {
    display: none;
  }
  .table-container.responsive {
    display: block;
    & > table tr, th {
      border: 1px solid;
    }
    & > table td {
      border-top: none;
      border-bottom: none;
      border-left: 1px solid;
    }
  }
  pre.responsive {
    display: block;
    white-space: pre-wrap;
    width: 100%;
    padding-left: 0.5em;
    padding-right: 0.5em;
  }
}
</style>
