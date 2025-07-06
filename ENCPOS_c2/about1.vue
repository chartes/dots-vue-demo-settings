<template>
  <article class="about">
    <div class="title app-width-padding">Scenario user guide Title</div>
    <div class="about-content app-width-padding">
      <h2>Title 2</h2>
      <h3>Title 3</h3>
      <h4>Synthèse. Cascade de configuration</h4>

      <!-- Code block -->
      <pre>
        default.conf.json (dots-vue)
          > custom.conf.json (dots-vue-demo-settings)
            > dots_cookbook.conf.json
              > encpos.conf.json
                > encpos_1849.json
                > encpos_1971.json
                > encpos_1972.json
      </pre>

      <!-- Table -->
      <div class="table-container mt-5">
        <table class="table is-striped is-hoverable is-bordered is-fullwidth">
          <thead>
            <tr>
              <th>parameter</th>
              <th><code>default</code></th>
              <th><code>custom</code></th>
              <th><code>dots_cookbook</code></th>
              <th><code>encpos</code></th>
              <th> last coll.</th>
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
              <td>tei</td>
              <td>→ (tei)</td>
              <td>
                <code>ENCPOS_1849</code> <code>ENCPOS_1971</code>
              </td>
              <td>
                <a target='_blank' :href=exampleUrl1>{{ example1 }}</a> <a target='_blank' :href=exampleUrl2>{{ example2 }}</a>
              </td>
            </tr>
            <tr>
              <td></td>
              <td></td>
              <td></td>
              <td></td>
              <td></td>
              <td>html</td>
              <td><code>ENCPOS_1972</code></td>
              <td>
                <a target='_blank' :href=exampleUrl3>{{ example3 }}</a>
              </td>
            </tr>
            <tr>
              <td><code>displayMode</code></td>
              <td>card</td>
              <td>card</td>
              <td>→ (card)</td>
              <td>→ (card)</td>
              <td>not relevant</td>
              <td></td>
              <td>
                <a target='_blank' :href=exampleUrl4>Example 4</a>
              </td>
            </tr>
            <tr>
              <td><code>cardCollectionPerPage</code></td>
              <td>5</td>
              <td>5</td>
              <td>→ (5)</td>
              <td>3</td>
              <td>not relevant</td>
              <td></td>
              <td>
                <a target='_blank' :href=exampleUrl5>Example 5</a>
              </td>
            </tr>
            <tr>
              <td><code>editByLevel</code></td>
              <td>1</td>
              <td>1</td>
              <td>→ (1)</td>
              <td>0 (document)</td>
              <td>→ (0)</td>
              <td><code>ENCPOS_1849</code> <code>ENCPOS_1971</code></td>
              <td>
                <a target='_blank' :href=exampleUrl1>{{ example1 }}</a> <a target='_blank' :href=exampleUrl2>{{ example2 }}</a>
              </td>
            </tr>
            <tr>
              <td></td>
              <td></td>
              <td></td>
              <td></td>
              <td></td>
              <td>1 (part)</td>
              <td><code>ENCPOS_1972</code></td>
              <td>
                <a target='_blank' :href=exampleUrl3>{{ example3 }}</a>
              </td>
            </tr>
            <tr>
              <td><code>tableOfContentDepth</code></td>
              <td>5</td>
              <td>5</td>
              <td>→ (5)</td>
              <td>→ (5)</td>
              <td>→ (5)</td>
              <td><code>ENCPOS_1849</code> <code>ENCPOS_1971</code> <code>ENCPOS_1972</code></td>
              <td>
                <a target='_blank' :href=exampleUrl1>{{ example1 }}</a> <a target='_blank' :href=exampleUrl2>{{ example2 }}</a> <a target='_blank' :href=exampleUrl3>{{ example3 }}</a>
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
    const example1 = ref('ENCPOS_1849_04')
    const example2 = ref('ENCPOS_1971_09')
    const example3 = ref('ENCPOS_1972_18')
    const exampleUrl1 = computed(() => `${window.location.origin}${appBaseUrl.value}ENCPOS/document/${example1.value}`)
    const exampleUrl2 = computed(() => `${window.location.origin}${appBaseUrl.value}ENCPOS/document/${example2.value}`)
    const exampleUrl3 = computed(() => `${window.location.origin}${appBaseUrl.value}ENCPOS/document/${example3.value}`)

    console.log('About 3 setup exampleUrl1 : ', exampleUrl1.value)

    watch(props, (newProps) => {
      appBaseUrl.value = newProps.applicationBaseUrl
      console.log('About 3 watch appBaseUrl : ', appBaseUrl.value)
      exampleUrl1.value = `${window.location.origin}${appBaseUrl.value}ENCPOS/document/${example1.value}`
      exampleUrl2.value = `${window.location.origin}${appBaseUrl.value}ENCPOS/document/${example2.value}`
      exampleUrl3.value = `${window.location.origin}${appBaseUrl.value}ENCPOS/document/${example3.value}`
      console.log('About 3 watch exampleUrl1 : ', exampleUrl1.value)
    }, { immediate: true })

    return {
      appBaseUrl,
      example1,
      example2,
      example3,
      exampleUrl1,
      exampleUrl2,
      exampleUrl3
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

