<template>
  <article class="about">
    <div class="about-content app-width-padding">
      <h1>DoTS Cookbook Demo</h1>
      <h2>Building a consultation frontend with DoTS-Vue</h2>
      <p>The <a href="https://github.com/chartes/dots-vue" target="_blank">DoTS-Vue</a> application allows for easily publishing online collections of texts available through a <a href="https://github.com/chartes/dots" target="_blank">DoTS</a> DTS endpoint.</p>
      <p>For this demonstration, we are using the <a href="https://chartes.github.io/dots_documentation/cookbook/" target="_blank">DoTS cookbook</a> designed to showcase how to share collections of texts via the <a href="https://distributed-text-services.github.io/specifications/" target="_blank">DTS API</a>.</p>
      <p>The DTS endpoint used is accessible here: <a href="https://dots.chartes.psl.eu/demo/api/dts/">https://dots.chartes.psl.eu/demo/api/dts/</a></p>
<!--
      <hr/>
      <p>On peut imprimer ici la description inscrite dans la réponse d’API du endpoint <a href="https://dots.chartes.psl.eu/demo/api/dts/collection">Collection</a> en appelant <code>dtsCollDescription</code> :</p>
      <blockquote>
        <p>
          {{ dtsCollDescription ? dtsCollDescription : 'No DTS API collection description available' }}
        </p>
      </blockquote>
      <hr/>
      <p>On peut imprimer ici la description inscrite dans le fichier de settings de la collection (<code>collectionDescription</code>) en appelant <code>customCollDescription</code> :</p>
      <blockquote>
        <p>
          {{ customCollDescription ? customCollDescription : 'No homePageSettings.collectionDescription available' }}
        </p>
      </blockquote>
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
.about {
  font-family: "Barlow", sans-serif;
}
.about h1 {
  padding-top: 20px;
  padding-bottom: 20px;
  text-align: left;
  font-size: 25px;
  font-weight: 500;
  line-height: 33px;
  text-transform: none;
  color: var(--text-color);
}
.about h2 {
  padding-top: 20px;
  padding-bottom: 20px;
  text-align: left;
  font-size: 20px;
  font-weight: 500;
  line-height: 33px;
  text-transform: none;
}
.about p {
  text-align: left;
  text-indent: 0;
}
</style>
