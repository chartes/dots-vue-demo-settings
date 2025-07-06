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
      <!-- Table -->
      <div class="table-container mt-5">
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
    </div>
  </article>

</template>
<script>
import { ref, watch, computed } from 'vue'
import { useRoute } from 'vue-router'
import router from '@/router'

export default {
  name: 'AboutThirdSection',
  props: {
    applicationBaseUrl: {
      type: String,
    },
  },
  setup (props) {
    const route = useRoute()
    const appBaseUrl = ref(props.applicationBaseUrl)
    console.log('About 3 setup route : ', route)
    console.log('About 3 setup window.location.origin : ', window.location.origin)
    console.log('About 3 setup router.currentRoute : ', router.currentRoute)
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
.table-container {
  text-align: center;
  font-size: 12px;
}
.table-container td,
.table-container th {
  padding: 0.10rem 0.10rem;
}
</style>

