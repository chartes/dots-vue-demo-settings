<template>
  <article class="about">
    <div class="title app-width-padding">Settings cascade</div>
    <div class="about-content app-width-padding">
      <h2>Recipe settings overview (Theater)</h2>
      <!-- Code block -->
      <pre>
default.conf.json                     dots-vue
  > custom.conf.json                  dots-vue-demo-settings
    > dots_cookbook.conf.json
      > theater.conf.json
        > moliere.conf.json
        > racine.conf.json
      </pre>
      <p>
        The table below illustrates the cascade for different parameters.
      </p>
      <!-- Table responsive -->
      <div class="table-container desktop mt-5">
        <table class="table is-striped is-hoverable is-bordered is-fullwidth">
          <thead>
            <tr>
              <th>parameter</th>
              <th><code>default</code></th>
              <th>> <code>custom</code></th>
              <th>> <code>dots_cookbook</code></th>
              <th>> <code>theater</code></th>
              <th>> last coll.</th>
              <th>last coll. ids</th>
              <th>example</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><code>mediaTypeEndpoint</code></td>
              <td>tei</td>
              <td>html</td>
              <td>→ (html)</td>
              <td>→ (html)</td>
              <td>→ (html)</td>
              <td><code>racine</code></td>
              <td><a target='_blank' :href=exampleUrl2>Andromaque V</a></td>
            </tr>
            <tr>
              <td></td>
              <td></td>
              <td></td>
              <td></td>
              <td></td>
              <td>tei</td>
              <td><code>moliere</code></td>
              <td><a target='_blank' :href=exampleUrl1>Dom Juan III,3</a></td>
            </tr>
            <tr>
              <td><code>displayMode</code></td>
              <td>card</td>
              <td>card</td>
              <td>→ (card)</td>
              <td>→ (card)</td>
              <td>not relevant</td>
              <td></td>
              <td></td>
            </tr>
            <tr>
              <td><code>cardCollectionPerPage</code></td>
              <td>5</td>
              <td>5</td>
              <td>→ (5)</td>
              <td>→ (5)</td>
              <td>not relevant</td>
              <td><code></code></td>
              <td></td>
            </tr>
            <tr>
              <td><code>editByLevel</code></td>
              <td>1</td>
              <td>1</td>
              <td>→ (1)</td>
              <td>–</td>
              <td>–</td>
              <td><code>moliere</code> <code>racine</code></td>
              <td></td>
            </tr>
            <tr>
              <td><code>editByCiteType</code></td>
              <td><code>null</code></td>
              <td><code>null</code></td>
              <td><code>null</code></td>
              <td><code>scene</code></td>
              <td>→ (<code>scene</code>)</td>
              <td><code>moliere</code></td>
              <td></td>
            </tr>
            <tr>
              <td></td>
              <td></td>
              <td></td>
              <td></td>
              <td></td>
              <td><code>act</code></td>
              <td><code>racine</code></td>
              <td></td>
            </tr>
            <tr>
              <td><code>tableOfContentDepth</code></td>
              <td>5</td>
              <td>5</td>
              <td>→ (5)</td>
              <td>2 (scene level)</td>
              <td>→ (2)</td>
              <td><code>moliere</code></td>
              <td></td>
            </tr>
            <tr>
              <td></td>
              <td></td>
              <td></td>
              <td></td>
              <td></td>
              <td>3 (individual speech level)</td>
              <td><code>racine</code></td>
              <td></td>
            </tr>
          </tbody>
        </table>
      </div>
      <!-- Table responsive -->
      <div class="table-container responsive mt-5">
        <table class="table is-hoverable is-fullwidth">
          <thead>
            <tr>
              <th>parameter</th>
              <th>cascade</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><code>mediaTypeEndpoint</code></td>
              <td>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>default</b></span><span>tei</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>custom</b></span><span>html</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>dots_cookbook</b></span><span>→ (html)</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>theater</b></span><span>→ (html)</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>last coll.</b></span><span>→ (html)</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>last coll. ids</b></span><span><code>racine</code></span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span class="no-min-width"><b>example</b></span>
                  <span class="no-min-width"><a target="_blank" :href="exampleUrl2">Andromaque V</a></span>
                </div>
              </td>
            </tr>
            <tr>
              <td></td>
              <td>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>last coll.</b></span><span>tei</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>last coll. ids</b></span><span><code>moliere</code></span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span class="no-min-width"><b>example</b></span>
                  <span class="no-min-width"><a target="_blank" :href="exampleUrl1">Dom Juan III,3</a></span>
                </div>
              </td>
            </tr>
            <tr>
              <td><code>displayMode</code></td>
              <td>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>default</b></span><span>card</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>custom</b></span><span>card</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>dots_cookbook</b></span><span>→ (card)</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>theater</b></span><span>→ (card)</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>last coll.</b></span><span>not relevant</span>
                </div>
              </td>
            </tr>
            <tr>
              <td><code>cardCollectionPerPage</code></td>
              <td>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>default</b></span><span>5</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>custom</b></span><span>5</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>dots_cookbook</b></span><span>→ (5)</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>theater</b></span><span>→ (5)</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>last coll.</b></span><span>not relevant</span>
                </div>
              </td>
            </tr>
            <tr>
              <td><code>editByLevel</code></td>
              <td>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>default</b></span><span>1</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>custom</b></span><span>1</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>dots_cookbook</b></span><span>→ (1)</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>theater</b></span><span>–</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>last coll.</b></span><span>–</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>last coll. ids</b></span>
                  <span><code>moliere</code><br><code>racine</code></span>
                </div>
              </td>
            </tr>
            <tr>
              <td><code>editByCiteType</code></td>
              <td>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>default</b></span><span><code>null</code></span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>custom</b></span><span><code>null</code></span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>dots_cookbook</b></span><span><code>null</code></span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>theater</b></span><span><code>scene</code></span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>last coll.</b></span><span>→ (<code>scene</code>)</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>last coll. ids</b></span><span><code>moliere</code></span>
                </div>
              </td>
            </tr>
            <tr>
              <td></td>
              <td>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>last coll.</b></span><span><code>act</code></span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>last coll. ids</b></span><span><code>racine</code></span>
                </div>
              </td>
            </tr>
            <tr>
              <td><code>tableOfContentDepth</code></td>
              <td>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>default</b></span><span>5</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>custom</b></span><span>5</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>dots_cookbook</b></span><span>→ (5)</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>theater</b></span><span>2 (scene lvl)</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>last coll.</b></span><span>→ (2)</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>last coll. ids</b></span><span><code>moliere</code></span>
                </div>
              </td>
            </tr>
            <tr>
              <td></td>
              <td>
                <div class="is-flex is-justify-content-space-between">
                  <span class="no-min-width"><b>last coll.</b></span>
                  <span class="no-min-width">3 (indiv. speech lvl)</span>
                </div>
                <div class="is-flex is-justify-content-space-between">
                  <span><b>last coll. ids</b></span>
                  <span><code>racine</code></span>
                </div>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </article>

</template>
<script>
import { ref, watch, computed } from 'vue'

export default {
  name: 'AboutThirdSection',
  props: {
    applicationBaseUrl: {
      type: String,
    },
  },
  setup (props) {
    const appBaseUrl = ref(props.applicationBaseUrl)
    console.log('About 3 setup window.location.origin : ', window.location.origin)
    console.log('About 3 setup appBaseUrl : ', appBaseUrl)
    const example1 = ref('moliere_dom-juan?refId=a3-s3')
    const example2 = ref('racine_andromaque?refId=a5')
    // http://localhost:5173/ENCPOS_c2/document/ENCPOS_1971_c2?refId=ENCPOS_1971_12
    const exampleUrl1 = computed(() => `${window.location.origin}${appBaseUrl.value}theater/document/${example1.value}`)
    const exampleUrl2 = computed(() => `${window.location.origin}${appBaseUrl.value}theater/document/${example2.value}`)

    console.log('About 3 setup exampleUrl1 : ', exampleUrl1.value)

    watch(props, (newProps) => {
      appBaseUrl.value = newProps.applicationBaseUrl
      console.log('About 3 watch appBaseUrl : ', appBaseUrl.value)
      exampleUrl1.value = `${window.location.origin}${appBaseUrl.value}ENCPOS/document/${example1.value}`
      exampleUrl2.value = `${window.location.origin}${appBaseUrl.value}ENCPOS/document/${example2.value}`
      console.log('About 3 watch exampleUrl1 : ', exampleUrl1.value)
    }, { immediate: true })

    return {
      appBaseUrl,
      example1,
      example2,
      exampleUrl1,
      exampleUrl2
    }
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
    min-width: 60%;
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

