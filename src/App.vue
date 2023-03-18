<script>
  import Header from './components/Header.vue'
  import Footer from './components/Footer.vue'

  export default {
    name:"App",
    components: { Header, Footer },
    data() {
    return {
      from_name: "",
      from_firstname: "",
      email_id: "",
      message: "",
    };
  },

  methods: {
    sendMail() {
      const params = {
        from_name: this.from_name,
        from_firstname: this.from_firstname,
        email_id: this.email_id,
        message: this.message,
      };
      emailjs
      .send("service_mketqjv", "template_n7jp4ch", params)
    },
  },
};
</script>

<style>
  .welcome{
    @apply relative text-slate-300 
  }
  .welcome::before{
    @apply content-['Portfolio']
    absolute text-Blanc border-r-2 border-Blanc 
    overflow-hidden animate-animate 
  }

  .container {
  overflow: hidden;
  display: flex;
}
.txt {
  white-space: nowrap;
  animation: scrollTxt 10s linear infinite;
}

@keyframes scrollTxt {
  0%{
    transform: translate(-10%, 0);
  }
  100% {
    transform: translate(10%, 0);
  }
}
</style>

<template>
<div class="text-white bg-black font-sublima">
  <Header/>
  <h1 class="welcome text-Noir text-center pt-80 text-3xl md:text-4xl lg:text-4xl xl:text-4xl">Portfolio</h1>
  <h2 class="animate__animated animate__backInLeft text-center lg:ml-96 xl:ml-96 font-bold text-2xl md:text-3xl lg:text-3xl xl:text-3xl rounded-lg">Maxime Mercier</h2>
    <div class="grid grid-cols-2 space-x-4 mt-60">
      <h3 class="text-left ml-5 font-bold sm:text-sm md:text-base lg:text-xl xl:text-xl">2023</h3>
      <div class="grid grid-cols-2">
        <h3 class="text-right ml-5 font-bold sm:text-sm md:text-base lg:text-lg xl:text-xl">Contact :</h3>
        <a href="mailto:maxime.mercier@edu.univ-fcomte.fr" class="text-left ml-2 hover:underline sm:text-sm md:text-base lg:text-lg xl:text-xl">maxime.mercier@edu.univ-fcomte.fr</a>
      </div>
    </div>

    <h2 id="presentation" class="mt-60 ml-10 md:ml-20 lg:ml-20 xl:ml-20 font-bold text-2xl md:text-3xl lg:text-3xl xl:text-3xl">Présentation</h2>

    <div class="grid grid-flow-row-dense grid-cols-[repeat(auto-fit,minmax(350px,2fr))] pb-10">
      <div class="grid grid-rows-2 justify-center mt-36">
        <img class="row-span-3 flex w-2/3 md:w-2/3 lg:w-max xl:w-max" src='./assets/Moi.svg' alt="">
          <div class="mt-20 pl-5">
            <button class="w-2/3 md:w-2/3 lg:w-80 xl:w-80  rounded-lg border-Blanc border-4 h-16 font-bold text-xl hover:bg-Blanc hover:text-black"><a href="../public/CV.pdf" target="_blank">Voir mon CV</a></button>
          </div>
      </div>
      <div class="grid grid-rows-5 grid-flow-row mr-5">
        <h3 class="mt-12 ml-5 lg:mt-20 xl:mt-20 font-sublima lg:text-lg xl:text-xl">Etudiant en 2e année au sein du département MMI de Montbéliard.</h3>
        <h3 class="font-sublima ml-5 sm:mt-5 md:mt-3 lg:text-lg xl:text-xl">Spécialisé dans la Communication Web et l’Expérience Utilisateur (UX), je développe la stratégie de communication afin de trouver les meilleures méthodes de référencement pour les différents sites à ma charge.</h3>
        <h3 class="mt-8 ml-5 font-sublima font-bold lg:text-lg xl:text-xl">Grâce à cela, la notoriété de ces derniers est nettement plus grande au sein du grand public.</h3>
        <h3 class="mt-5 ml-5 font-sublima lg:text-lg xl:text-xl">Ayant donc d’ores et déjà réaliser des projets collectifs, il m’est désormais naturel de communiquer de façon efficace et régulière avec mes collaborateurs ainsi qu’avec le commanditaire du projet.</h3>
        <h3 class="mt-5 ml-5 font-sublima lg:text-lg xl:text-xl">En plus de cela, je procède à d’autres créations telles que des maquettes graphiques, ainsi que l’intégration de sites Web responsives, statiques comme dynamiques.</h3>
      </div>
    </div>

    <h2 id="competences" class="mt-60 ml-10 md:ml-20 lg:ml-20 xl:ml-20 font-bold text-2xl md:text-3xl lg:text-3xl xl:text-3xl">Mes compétences</h2>

    <div class="py-36 px-20">
      <h2 class="rounded-lg border-Blanc text-center text-Noir bg-Blanc justify-center border-8 font-bold text-xl py-1 relative flex flex-grow flex-col items-center self-stretch">Communication Web</h2>
    </div>

    <div class="grid grid-flow-row-dense grid-cols-[repeat(auto-fit,minmax(350px,2fr))] pb-10">
      <div class="relative m-auto flex w-4/5 flex-col items-center justify-center pb-10">
        <div class="relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Noir border-8 border-Blanc py-5">
          <h3 class="flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Blanc text-xl">Communication Social Media</h3>
        </div>
        <div class="pt-5">
          <div class="container relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Blanc px-10 py-2">
            <h4 class="txt flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Noir text-xs md:text-sm lg:text-base xl:text-base">Gestion des publications - Modérations de la communauté</h4>
          </div>
        </div>
      </div>
      <div class="relative m-auto flex w-4/5 flex-col items-center justify-center pb-10">
        <div class="relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Noir border-8 border-Blanc py-5">
          <h3 class=" flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-xl text-Blanc">Stratégie de communication</h3>
        </div>
        <div class="pt-5">
          <div class="container relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Blanc px-10 py-2">
            <h4 class="txt flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Noir text-xs md:text-sm lg:text-base xl:text-base">Optimiser la mise en avant des projets pour le grand public</h4>
          </div>
        </div>
      </div>
    </div>

    <div class="grid grid-flow-row-dense grid-cols-[repeat(auto-fit,minmax(350px,2fr))]">
      <div class="relative m-auto flex w-4/5 flex-col items-center justify-center pb-10">
        <div class="relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Noir border-8 border-Blanc py-5">
          <h3 class="flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Blanc text-xl">Elaboration de Référencement SEO</h3>
        </div>
        <div class="pt-5">
          <div class="container relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Blanc px-10 py-2">
            <h4 class="txt flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Noir text-xs md:text-sm lg:text-base xl:text-base">Optimisation pour les moteurs de recherches</h4>
          </div>
        </div>
      </div>
      <div class="relative m-auto flex w-4/5 flex-col items-center justify-center pb-10">
        <div class="relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Noir border-8 border-Blanc py-5">
          <h3 class="flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-xl text-Blanc">Structuration de projets</h3>
        </div>
        <div class="pt-5">
          <div class="container relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Blanc px-10 py-2">
            <h4 class="txt flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Noir text-xs md:text-sm lg:text-base xl:text-base">Gestion des tâches - Echanges avec le commanditaire</h4>
          </div>
        </div>
      </div>
    </div>

    <div class="grid grid-flow-row-dense grid-cols-[repeat(auto-fit,minmax(350px,2fr))]">
      <div class="relative m-auto flex w-4/5 flex-col items-center justify-center pb-10">
        <div class="relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Noir border-8 border-Blanc py-5">
          <h3 class="flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Blanc text-xl">Confection de cahier des charges</h3>
        </div>
        <div class="pt-5">
          <div class="container relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Blanc px-10 py-2">
            <h4 class="txt flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Noir text-xs md:text-sm lg:text-base xl:text-base">Expliquer et Argumenter sur le potentiel des projets aux clients</h4>
          </div>
        </div>
      </div>
      <div class="relative m-auto flex w-4/5 flex-col items-center justify-center pb-10">
        <div class="relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Noir border-8 border-Blanc py-5">
          <h3 class="flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Blanc text-xl">Veille informatique</h3>
        </div>
        <div class="pt-5">
          <div class="container relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Blanc px-10 py-2">
            <h4 class="txt flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Noir text-xs md:text-sm lg:text-base xl:text-base">Consultation des tendances du web, Comprendre les nouveaux besoins des utilisateurs</h4>
          </div>
        </div>
      </div>
    </div>

    <div class="relative m-auto flex w-2/5 flex-col items-center justify-center pb-10">
        <div class="relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Noir border-8 border-Blanc py-5">
          <h3 class="flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-xl text-Blanc">Utilisation d'outils collaboratifs</h3>
        </div>
        <div class="pt-5 flex items-center justify-center w-1/6 md:w-1/12 lg:w-1/12 xl:w-1/12 space-x-5">
          <img src="./assets/Logo_drive.png" alt="">
          <img src="./assets/Logo_docs.png" alt="">
          <img src="./assets/Logo_slides.png" alt="">
          <img src="./assets/Logo_sheets.png" alt="">
          <img src="./assets/Logo_forms.png" alt="">
        </div>
        <div class="pt-5">
          <div class="container relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Blanc px-10 py-2">
            <h4 class="txt flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Noir text-xs md:text-sm lg:text-base xl:text-base">Google Drive, Docs, Slides, Sheets, Forms</h4>
          </div>
        </div>
      </div>
    

    <div class="py-36 px-20">
      <h2 class="rounded-lg border-Blanc text-Noir bg-Blanc justify-center border-8 font-bold text-xl py-1 relative flex flex-grow flex-col items-center self-stretch">Design Graphique</h2>
    </div>

    <div class="grid grid-flow-row-dense grid-cols-[repeat(auto-fit,minmax(350px,2fr))] pb-10">
      <div class="relative m-auto flex w-4/5 flex-col items-center justify-center pb-10">
        <div class="relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Noir border-8 border-double border-Blanc py-5">
          <h3 class="flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Blanc text-xl">Création de maquettes</h3>
        </div>
        <div class="pt-5 flex items-center justify-center w-1/6 md:w-1/12 lg:w-1/12 xl:w-1/12 space-x-5">
          <img src="./assets/Logo_Figma.png" alt="">
        </div>
        <div class="pt-5">
          <div class="container relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Blanc px-10 py-2">
            <h4 class="txt flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Noir text-xs md:text-sm lg:text-base xl:text-base">Donner un aperçu du futur site, présentation pour les clients</h4>
          </div>
        </div>
      </div>
      <div class="relative m-auto flex w-4/5 flex-col items-center justify-center pb-10">
        <div class="relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Noir border-8 border-double border-Blanc py-5">
          <h3 class="flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-xl text-Blanc">Réalisations audiovisuelles</h3>
        </div>
        <div class="pt-5 flex items-center justify-center w-1/6 md:w-1/12 lg:w-1/12 xl:w-1/12 space-x-5">
          <img src="./assets/Logo_OBS.png" alt="">
          <img src="./assets/Logo_DaVinci.png" alt="">
        </div>
        <div class="pt-5">
          <div class="container relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Blanc px-10 py-2">
            <h4 class="txt flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Noir text-xs md:text-sm lg:text-base xl:text-base">Réalisation de vidéos avec gestion images et son / Montage vidéo</h4>
          </div>
        </div>
      </div>
    </div>
      <div class="relative m-auto flex w-2/5 flex-col items-center justify-center pb-10">
        <div class="relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Noir border-8 border-double border-Blanc py-5">
          <h3 class="flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Blanc text-xl">Réalisations de contenus visuels</h3>
        </div>
        <div class="pt-5 flex items-center justify-center w-1/6 md:w-1/12 lg:w-1/12 xl:w-1/12 space-x-5">
          <img src="./assets/Logo_photoshop.png" alt="">
          <img src="./assets/Logo_illustrator.png" alt="">
          <img src="./assets/Logo_indesign.png" alt="">
        </div>
        <div class="pt-5">
          <div class="container relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Blanc px-10 py-2">
            <h4 class="txt flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Noir text-xs md:text-sm lg:text-base xl:text-base">Elaboration de logos, affiches...</h4>
          </div>
        </div>
      </div>

      <div class="py-36 px-20">
        <h2 class="rounded-lg text-center border-Blanc text-Noir bg-Blanc justify-center border-8 font-bold text-xl py-1 relative flex flex-grow flex-col items-center self-stretch">Développement Web</h2>
      </div>

    <div class="grid grid-flow-row-dense grid-cols-[repeat(auto-fit,minmax(350px,2fr))] pb-10">
      <div class="relative m-auto flex w-4/5 flex-col items-center justify-center pb-10">
        <div class="relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Noir border-8 border-dashed border-Blanc py-5">
          <h3 class="flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Blanc text-xl">Intégration de sites Web</h3>
        </div>
        <div class="pt-5 flex items-center justify-center w-1/6 md:w-1/12 lg:w-1/12 xl:w-1/12 space-x-5">
          <img src="./assets/Logo_html.png" alt="">
          <img src="./assets/Logo_css.png" alt="">
          <img src="./assets/Logo_vue.png" alt="">
          <img src="./assets/Logo_typescript.png" alt="">
        </div>
        <div class="pt-5">
          <div class="container relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Blanc px-10 py-2">
            <h4 class="txt flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Noir text-xs md:text-sm lg:text-base xl:text-base">Langages utilisés : HTML/CSS, VueJS, TypeScript</h4>
          </div>
        </div>
      </div>
      <div class="relative m-auto flex w-4/5 flex-col items-center justify-center pb-10">
        <div class="relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Noir border-8 border-dashed border-Blanc py-5">
          <h3 class="flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-xl text-Blanc">Utilisation de logiciels OpenSource</h3>
        </div>
        <div class="pt-5 flex items-center justify-center w-1/6 md:w-1/12 lg:w-1/12 xl:w-1/12 space-x-5">
          <img src="./assets/Logo_VSCode.png" alt="">
          <img src="./assets/Logo_Wordpress.png" alt="">
          <img src="./assets/Logo_Github.svg" alt="">
          <img src="./assets/Logo_Supabase.png" alt="">
          <img src="./assets/Logo_Firebase.png" alt="">
        </div>
        <div class="pt-5">
          <div class="container relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch bg-Blanc px-10 py-2">
            <h4 class="txt flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Noir text-xs md:text-sm lg:text-base xl:text-base">Visual Studio Code, Wordpress, Github, Supabase, Firebase</h4>
          </div>
        </div>
      </div>
    </div>

    <h2 id="creations" class="mt-60 mb-20 ml-10 md:ml-20 lg:ml-20 xl:ml-20 font-bold text-2xl md:text-3xl lg:text-3xl xl:text-3xl">Mes créations</h2>

    <div class="grid grid-flow-row-dense grid-cols-[repeat(auto-fit,minmax(350px,2fr))] pb-10">
      <a href="http://vieuxcomme9.mercier-maxime.com" target="_blank"><div class="relative m-auto flex w-4/5 flex-col items-center justify-center pb-10 h-60 md:h-72 lg:h-96 xl:h-96">
        <div class="relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch border-8 rounded-lg border-Blanc py-5 group">
          <h3 class="z-10 flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Blanc text-lg md:text-xl lg:text-2xl xl:text-2xl">Vieux Comme 9</h3>
          <img src="./assets/vieux_comme_9.png" alt="" class="absolute w-full h-full z-0 opacity-0 group-hover:opacity-30 duration-1000 ">
          <div class="z-10 flex justify-center  ">
            <img class="w-1/3 md:w-1/3 lg:w-2/3 xl:w-2/3" src="./assets/Logo_Vieux_Comme_9.svg" alt="">
          </div>
        </div>
      </div>
    </a>     
    <div class="relative m-auto flex w-2/5 flex-col items-center justify-center pb-10">
      <h3 class="font-sublima text-center text-base lg:text-lg xl:text-xl">Projet traitant d'un festival musical, réalisé avec gestion de base de données sur Firebase</h3>
      <h4 class="font-sublima mt-5 text-center text-sm lg:text-sm xl:text-base"><i>(Création / Modification / Suppresion d'éléments)</i></h4>
      </div>
    </div>

    <div class="grid grid-flow-row-dense grid-cols-[repeat(auto-fit,minmax(350px,2fr))] pb-10">
      <a href="https://tiktak.mercier-maxime.com" target="_blank"><div class="relative m-auto flex w-4/5 flex-col items-center justify-center pb-10 h-60 md:h-72 lg:h-96 xl:h-96">
        <div class="relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch border-8 rounded-lg border-Blanc py-5 group">
          <img src="./assets/tik_tak.png" alt="" class="absolute w-full h-full z-0 opacity-0 group-hover:opacity-30 duration-1000 ">
          <div class="z-10 flex justify-center  ">
            <img class="w-1/3 md:w-1/3 lg:w-2/3 xl:w-2/3" src="./assets/Logo_Tik_Tak.svg" alt="">
          </div>
        </div>
      </div>
    </a>     
    <div class="relative m-auto flex w-2/5 flex-col items-center justify-center pb-10">
      <h3 class="font-sublima text-center text-base lg:text-lg xl:text-xl">Site ayant pour thème, la création, la modification ainsi que la suppression de montres entièrement personnalisables</h3> 
      <h4 class="font-sublima mt-5 text-center text-sm lg:text-sm xl:text-base"><i>(Gestion des données avec Supabase)</i></h4>   
      </div>
    </div>

    <div class="grid grid-flow-row-dense grid-cols-[repeat(auto-fit,minmax(350px,2fr))] pb-10">
      <a href="https://aidealareussite.fr" target="_blank"><div class="relative m-auto flex w-4/5 flex-col items-center justify-center pb-10 h-60 md:h-72 lg:h-96 xl:h-96">
        <div class="relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch border-8 rounded-lg border-Blanc py-5 group">
          <h3 class="z-10 flex-shrink-0 flex-grow-0 self-stretch text-center font-bold text-Blanc text-lg md:text-xl lg:text-2xl xl:text-2xl">Aide à la réussite</h3>
          <img src="./assets/aide_a_la_reussite.png" alt="" class="absolute w-full h-full z-0 opacity-0 group-hover:opacity-30 duration-1000 ">
          <div class="z-10 flex justify-center">
            <img class="pt-10 w-1/3 md:w-1/3 lg:w-2/3 xl:w-2/3" src="./assets/Logo_Aide_reussite.svg" alt="">
          </div>
        </div>
      </div>
    </a>     
    <div class="relative m-auto flex w-2/5 flex-col items-center justify-center pb-10">
      <h3 class="font-sublima text-center text-base lg:text-lg xl:text-xl">Projet collectif réalisé afin de convenir à un programme d'accompagnement d'étudiants en difficulté scolaire.</h3> 
      <h4 class="font-sublima mt-5 text-center text-sm lg:text-sm xl:text-base"><i>(Réalisation de la communication et SEO)</i></h4>      
      </div>
    </div>
    
    <div class="grid grid-flow-row-dense grid-cols-[repeat(auto-fit,minmax(350px,2fr))] pb-10">
      <a href="https://honeyst.mercier-maxime.com" target="_blank"><div class="relative m-auto flex w-4/5 flex-col items-center justify-center pb-10 h-60 md:h-72 lg:h-96 xl:h-96">
        <div class="relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch border-8 rounded-lg border-Blanc py-5 group">
          <img src="./assets/honeyst.png" alt="" class="absolute w-full h-full z-0 opacity-0 group-hover:opacity-30 duration-1000 ">
          <div class="z-10 flex justify-center">
            <img class="w-1/3 md:w-1/3 lg:w-2/3 xl:w-2/3" src="./assets/Logo_Honeyst.jpg" alt="">
          </div>
        </div>
      </div>
    </a>     
    <div class="relative m-auto flex w-2/5 flex-col items-center justify-center pb-10">
      <h3 class="font-sublima text-center text-base lg:text-lg xl:text-xl">Site e-commerce permettant la consultation ainsi que l'achat des produits disponibles dans la boutique.</h3>   
      <h4 class="font-sublima mt-5 text-center text-sm lg:text-sm xl:text-base"><i>(Réalisé avec WordPress et plugin WooCommerce)</i></h4>       
      </div>
    </div>

    <div class="grid grid-flow-row-dense grid-cols-[repeat(auto-fit,minmax(350px,2fr))] pb-10">
      <a href="https://youtu.be/E6jd8HnmbCE" target="_blank"><div class="relative m-auto flex w-4/5 flex-col items-center justify-center pb-10 h-60 md:h-72 lg:h-96 xl:h-96">
        <div class="relative flex flex-grow flex-col items-center justify-center gap-2.5 self-stretch border-8 rounded-lg border-Blanc py-5 group">
            <video src="./assets/extrait_interview.mp4" alt="" class="absolute w-full h-full z-0 opacity-0 group-hover:opacity-30 duration-1000"></video>
          <img class="w-1/5" src="./assets/icone_lecture.svg" alt="">
        </div>
      </div>
    </a>     
    <div class="relative m-auto flex w-2/5 flex-col items-center justify-center pb-10">
      <h3 class="font-sublima text-center text-base lg:text-lg xl:text-xl">Interview d'un ancien étudiant MMI (ex-SRC), concernant son parcours universitaire ainsi que professionnel.</h3>    
      <h4 class="font-sublima mt-5 text-center text-sm lg:text-sm xl:text-base"><i>(Capture vidéo effectué avec OBS Studio / Montage vidéo réalisé avec DaVinci Resolve)</i></h4>
      </div>
    </div>

    <h2 class="mt-60 ml-10 md:ml-20 lg:ml-20 xl:ml-20 font-bold text-2xl md:text-3xl lg:text-3xl xl:text-3xl">Me contacter</h2>


    <div class="flex justify-center mt-20 mb-32">
      <form class="w-full items-start justify-center max-w-sm md:max-w-lg xl:w-max-2xl xl:max-w-3xl">
        <div class="flex justify-center border-b border-Blanc py-2">
          <input class="appearance-none bg-transparent border-none w-full text-Blanc mr-3 py-1 px-2 leading-tight focus:outline-none" type="text" placeholder="Nom" aria-label="Nom">
        </div>
        <div class="flex justify-center border-b pt-16 border-Blanc py-2">
          <input class="appearance-none bg-transparent border-none w-full text-Blanc mr-3 py-1 px-2 leading-tight focus:outline-none" type="text" placeholder="Adresse mail" aria-label="Adresse mail">
        </div>
      </form>
    </div>

    

  <Footer/>
</div>
</template>