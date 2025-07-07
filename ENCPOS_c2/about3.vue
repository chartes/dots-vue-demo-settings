<template>
  <article class="about">
    <div class="title app-width-padding">Settings cascade</div>
    <div class="about-content app-width-padding">
      <h2>Recipe settings overview (Thesis abstract, case 2)</h2>
      <!-- Code block -->
      <pre>
default.conf.json (dots-vue)
  > custom.conf.json (dots-vue-demo-settings)
    > dots_cookbook.conf.json
      > encpos_c2.conf.json
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
              <th>> <code>encpos_c2</code></th>
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
              <td>
                <a target='_blank' :href=exampleUrl1>refId=ENCPOS_1971_12</a>
              </td>
            </tr>
            <tr>
              <td><code>displayMode</code></td>
              <td>card</td>
              <td>card</td>
              <td>→ (card)</td>
              <td>list (no choice)</td>
              <td>
                <a target='_blank' :href=exampleUrl2>refId=ENCPOS_1972_18</a>
              </td>
            </tr>
            <tr>
              <td><code>cardCollectionPerPage</code></td>
              <td>5</td>
              <td>5</td>
              <td>→ (5)</td>
              <td>not relevant</td>
              <td></td>
            </tr>
            <tr>
              <td><code>editByLevel</code></td>
              <td>1</td>
              <td>1</td>
              <td>→ (1)</td>
              <td>→ (1)</td>
              <td>
                <a target='_blank' :href=exampleUrl1>refId=ENCPOS_1971_12</a>
              </td>
            </tr>
            <tr>
              <td><code>tableOfContentDepth</code></td>
              <td>5</td>
              <td>5</td>
              <td>→ (5)</td>
              <td>→ (5)</td>
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
    const example1 = ref('ENCPOS_1971_c2?refId=ENCPOS_1971_12')
    const example2 = ref('ENCPOS_1972_c2?refId=ENCPOS_1972_18')
    // http://localhost:5173/ENCPOS_c2/document/ENCPOS_1971_c2?refId=ENCPOS_1971_12
    const exampleUrl1 = computed(() => `${window.location.origin}${appBaseUrl.value}ENCPOS_c2/document/${example1.value}`)
    const exampleUrl2 = computed(() => `${window.location.origin}${appBaseUrl.value}ENCPOS_c2/document/${example2.value}`)

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

