<template>
  <article class="home">
    <div class="home-content app-width-padding">
      <h1>ENCPOS – Periodical case 1</h1>
      <h2>Volume as collection, article as document</h2>
      <p>
        A periodical is a regular, collective publication, such as the annual proceedings of a conference. Here we take the example of the École des Chartes' annual publication of thesis abstracts.
      </p>
      <p>
      <a href="https://chartes.github.io/dots_documentation/cookbook/periodical/#cas-1-un-article-est-un-document" target="_blank">This recipe (ENCPOS)</a> illustrates one way of publishing a periodical, with an XML/TEI file for each abstract. The annual volume of abstracts is a collection.
      </p>
      <!--
      <p>
        {{ dtsCollDescription ? dtsCollDescription : 'No DTS API collection description available' }}
      </p>
      <p>
        {{ customCollDescription ? customCollDescription : 'No homePageSettings.collectionDescription available' }}
      </p>
      -->
    </div>
  </article>

</template>
<script>
import { ref, watch } from 'vue'

export default {
  name: 'HomePageContent',
  props: {
    dtsCollectionDescription: {
      type: String,
      required: false
    },
    customCollectionDescription: {
      type: String,
      required: false
    }
  },
  setup (props) {
    const dtsCollDescription = ref(props.dtsCollectionDescription)
    const customCollDescription = ref(props.customCollectionDescription)

    watch(props, async (newProps) => {
      dtsCollDescription.value = newProps.dtsCollectionDescription
      customCollDescription.value = newProps.customCollectionDescription
    }, { deep: true, immediate: true })

    return {
      dtsCollDescription,
      customCollDescription
    }
  }
}
</script>
<style scoped>
.home {
  font-family: "Barlow", sans-serif;
}
.home h1 {
  padding-top: 20px;
  padding-bottom: 20px;
  text-align: left;
  font-size: 25px;
  font-weight: 500;
  line-height: 33px;
  text-transform: none;
  color: var(--text-color);
}
.home h2 {
  padding-top: 20px;
  padding-bottom: 20px;
  text-align: left;
  font-size: 20px;
  font-weight: 500;
  line-height: 33px;
  text-transform: none;
}
.home p {
  text-align: left;
  text-indent: 0;
}
</style>
