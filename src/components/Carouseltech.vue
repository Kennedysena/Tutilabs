<template>
  <div class="carousel">
    <button class="arrow" @click="previousImage" v-if="selectedImage > 0">
      <img src="/src/assets/Vector3.svg">
    </button>
    <div class="images">
      <button :class="['button', image.class]" v-for="(image, index) in visibleImages" :key="index"
        @click="selectImage(index)">
        <img :src="image.src" :class="image.class">
      </button>
    </div>
    <button class="arrow" @click="nextImage" v-if="selectedImage < images.length - 3">
      <img src="/src/assets/Seta2.svg">
    </button>
  </div>
</template>

<script>
export default {
  name: 'Carouseltech',
  data() {
    return {
      selectedImage: 0,
      images: [
        { src: "/src/assets/Sass.svg", class: "sass", techname: "Sass", description: "Sass é uma linguagem de folha de estilo compilada em CSS . Ele permite que você use variáveis , regras aninhadas , mixins , funções e muito mais, tudo com uma sintaxe totalmente compatível com CSS . Sass ajuda a manter grandes folhas de estilo bem organizadas e facilita o compartilhamento de design dentro e entre  projetos.", },
        { src: "/src/assets/Vue.svg", class: "vue", techname: "Vue", description: "Vue é uma estrutura JavaScript para construção de interfaces de usuário. Ele se baseia em HTML, CSS e JavaScript padrão e fornece um modelo de programação declarativo baseado em componentes que ajuda a desenvolver interfaces de usuário de qualquer complexidade com eficiência." },
        { src: "/src/assets/Typescript.svg", class: "typescript", techname: "Typescript", description: "TypeScript é um superconjunto de JavaScript, ou seja, um conjunto de ferramentas e formas mais eficientes de escrever código JavaScript, adicionando recursos que não estão presentes de maneira nativa na linguagem. Saiba mais sobre TypeScript, suas principais vantagens e como utilizá-lo em seus projetos." },
        { src: "/src/assets/Github.svg", class: "github", techname: "Github", description: "GitHub é uma plataforma de hospedagem de código-fonte e arquivos com controle de versão usando o Git. Ele permite que programadores, utilitários ou qualquer usuário cadastrado na plataforma contribuam em projetos privados e/ou Open Source de qualquer lugar do mundo." },
        { src: "/src/assets/Html.svg", class: "html", techname: "Html", description: "HTML é uma linguagem de marcação utilizada na construção de páginas na Web. Documentos HTML podem ser interpretados por navegadores. A tecnologia é fruto da junção entre os padrões HyTime e SGML. HyTime é um padrão para a representação estruturada de hipermídia e conteúdo baseado em tempo." },
        { src: "/src/assets/Javascript.svg", class: "javascript", techname: "Javascript", description: "JavaScript é uma linguagem de programação que permite a você criar conteúdo que se atualiza dinamicamente, controlar múltimídias, imagens animadas, e tudo o mais que há de interessante. Ok, não tudo, mas é maravilhoso o que você pode efetuar com algumas linhas de código JavaScript." },
        { src: "/src/assets/Css.svg", class: "css", techname: "Css", description: "Cascading Style Sheets é um mecanismo para adicionar estilos a uma página web, aplicado diretamente nas tags HTML ou ficar contido dentro das tags <style>. Também é possível, adicionar estilos adicionando um link para um arquivo CSS que contém os estilos." },
      ]
    }
  },
  computed: {
    visibleImages() {
      return this.images.slice(this.selectedImage, this.selectedImage + 3);
    }
  },
  methods: {
    selectImage(index) {
      this.$emit('update-description', this.images[this.selectedImage + index].description);
      this.$emit('update-techname', this.images[this.selectedImage + index].techname);
      this.$emit('update-tech-info', this.images[this.selectedImage + index]);
    },
    nextImage() {
      if (this.selectedImage < this.images.length - 3) {
        this.selectedImage += 3;;
      }
    },
    previousImage() {
      if (this.selectedImage > 0) {
        this.selectedImage -= 3;
      }
    }
  }
}
</script>

<style scoped>
.button {
  border: none;
  border-radius: 50%;
  width: 6.25rem;
  height: 6.18rem;
  background-color: transparent;
  margin-left: 10px;
  cursor: pointer;
}

.button.vue {
  background-color: #41B883;
}

.button.typescript {
  background-color: #007ACC;
}

.button.github {
  background-color: #ECECEC;
}

.button.html {
  background-color: #E14E1D
}


.images button {
  transition: transform 0.3s ease;
}

.images button:hover {
  transform: scale(1.1);
}

.carousel {
  display: flex;
  align-items: center;
  justify-content: center;
  background: #D9D9D9;
  height: 7.06rem;
  width: 31rem;
  border-radius: 4.235rem;
  margin-left: 0.938rem;
}

.images {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-grow: 1;
}

.arrow {
  width: 3.62rem;
  height: 3rem;
  background: none;
  border: none;
  cursor: pointer;
  margin: 0px 1.25rem 0px 0.62rem;

}
</style>
