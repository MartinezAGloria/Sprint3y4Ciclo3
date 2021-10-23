<template>
  <div id="app">

    <top-banner v-bind:idCarousel="['carousel1']" ></top-banner>

    <div class="container-fluid">

<!-- aquí se deberían cargar 4 películas que simulan las 4 noticias pero el hook no es el correcto -->
          <section-api></section-api>
        </div>

<!-- Esta es la tarjeta de miembros que nos piden pero al parecer estamos enviando las props de mala manera o con un nombre no correcro -->
    <div class="container-fluid">
      <div class="row justify-content-center mb-5">
        <div class="col mt-5" v-for="(item, index) of team" :key="index">
          <team-card :member="item"></team-card>
        </div>
      </div>
    </div>

    <page-footer></page-footer>
    <!-- <h1>{{ title }}</h1> -->
  </div>
</template>

<script>
import PageFooter from "./components/PageFooter.vue";
import TeamCard from "./components/TeamCard.vue";
import SectionApi from "./components/SectionApi.vue";
import TopBanner from './components/TopBanner.vue';

export default {
  name: "App",
  components: {
    PageFooter,
    TeamCard,
    SectionApi,
    TopBanner,
  },
  data(){
    return {
      title: "Vivo dentro de VUE",
      carousel1 : 'carousel1',
      // Esta es la definición del objeto team, el objeto contiene la info de cada miembro del equipo
      // Se esta enviando correctamente en el ciclo v-for pero las pruebas fallan
      // Al parecer tenemos un problema con la definición de los nombres de los atributos
      team: [
        {
          codigo: 1,
          nombre: "Limón",
          descripcion:
            "1. Deseo que mi amo lea mucho para que pase mas tiempo conmigo",
          rol: "Mascota",
          imagen: "https://placeimg.com/192/192/animals",
        },
        {
          codigo: 2,
          nombre: "Gloria Martínez",
          descripcion:
            "2. Incentivar el hábito de la lectura mejorando permanentemente la plataforma para que la gente comparta sus libros",
          rol: "Scrum master",
          imagen: "https://placeimg.com/192/192/any",
        },
        {
          codigo: 3,
          nombre: "Edgar Andrés Serna",
          descripcion:
            "3. Publicare los libros que termine de leer para compartir con mucha gente y hacer amigos",
          rol: "Usuario",
          imagen: "https://placeimg.com/192/192/architecture",
        },
        {
          codigo: 4,
          nombre: "Integrante 4",
          descripcion:
            "4. Leeré más para que mis hijos adquieran el hábito de la lectura.",
          rol: "Usuario",
          imagen: "https://placeimg.com_192_192_nature",
        },
        {
          codigo: 5,
          nombre: "Integrante 5",
          descripcion:
            "5. Comentaré sobre los libros que intercambie para motivar a los demás a que participen",
          rol: "Usuario",
          imagen: "https://placeimg.com.com/192/192/any",
        },
      ],
    };
  },
};
</script>