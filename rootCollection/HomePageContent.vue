<template>
  <article class="about">
    <div class="about-content app-width-padding">
      <h2>Présentation</h2>
      <p>
        DoTS est une implémentation en XQuery de la spécification d'API DTS (<a href="https://distributed-text-services.github.io/specifications/" target="_blank">Distributed Text Services</a>), adossée au logiciel de base de données XML <a href="https://basex.org/" target="_blank">BaseX</a>.
      </p>
      <p>
        Cet outil permet de publier aisément des sources en XML/TEI selon les principes FAIR (Findable, Accessible, Interoperable, Reusable).
      </p>
      <p>Cette implémentation de dots-vue illustre les cas d'exemples des cookbooks DoTs.</p>
    </div>
  </article>

</template>
<script>
export default {
  name: 'HomePageContent',

  setup () {
  }
}
</script>
<style scoped>
#article h2 {
  padding-top: 20px;
  padding-bottom: 20px;
  font-size: 20px;
  font-weight: 500;
  line-height: 33px;
  text-transform: none;
}
</style>
