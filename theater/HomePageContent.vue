<template>
  <article class="about">
    <div class="about-content app-width-padding">
      <h1>Theater</h1>
      <h2>Publish collections of plays</h2>
      <p>
        <a href="https://chartes.github.io/dots_documentation/cookbook/theater/" target="_blank">This recipe</a> details the possibilities offered by DoTS for publishing plays.
      </p>
      <p>
        The aim is to be able to describe, quote and republish : an act, a scene, a turn of speech, possibly a stanza or verse.<br>
        For research purposes, we can also automatically extract all the turns of speech of a given character.
      </p>
      <p>
        Here, we take the example of plays by Molière and Racine.
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
