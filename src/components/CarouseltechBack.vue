<template>
    <div class="carousel">
        <button class="arrow" @click="previousImage" v-if="selectedImage > 0">
            <img src="/src/assets/Vector3.svg">
        </button>
        <div class="images">
            <button :class="['button', image.class]" v-for="(image, index) in visibleImages" :key="index"
                @click="selectImage(selectedImage + index)">
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
    name: 'CarouseltechBack',
    data() {
        return {
            selectedImage: 0,
            images: [
                { src: "/src/assets/Node.svg", class: "node", technameBack: "Node", descriptionBack: "Node.js é um software de código aberto, multiplataforma, baseado no interpretador V8 do Google e que permite a execução de códigos JavaScript fora de um navegador web. A principal característica do Node.js é sua arquitetura assíncrona e orientada por eventos.", },
                { src: "/src/assets/Nest.svg", class: "nest", technameBack: "Nest", descriptionBack: "NestJS é um framework Node.js de código aberto destinado ao desenvolvimento de aplicativos do lado do servidor. Foi criado por Kamil Mysliwiec e lançado em 2017. Sob o capô, por padrão, o NestJS faz uso do framework Express.js, sendo também compatível com o Fastify. Sua arquitetura é fortemente inspirada no Angular." },
                { src: "/src/assets/Sql.svg", class: "sql", technameBack: "SQL", descriptionBack: "O MySQL é um sistema de gerenciamento de banco de dados, que utiliza a linguagem SQL como interface. É atualmente um dos sistemas de gerenciamento de bancos de dados mais populares da Oracle Corporation, com mais de 10 milhões de instalações pelo mundo." },
                { src: "/src/assets/Docker.svg", class: "docker", technameBack: "Docker", descriptionBack: "Docker é um conjunto de produtos de plataforma como serviço que usam virtualização de nível de sistema operacional para entregar software em pacotes chamados contêineres. Os contêineres são isolados uns dos outros e agrupam seus próprios softwares, bibliotecas e arquivos de configuração." },
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
            this.$emit('update-description-back', this.images[index].descriptionBack);
            this.$emit('update-techname-back', this.images[index].technameBack);
            this.$emit('update-tech-info', this.images[index]);
        },
        nextImage() {
            if (this.selectedImage < this.images.length - 3) {
                this.selectedImage += 1;
            }
        },
        previousImage() {
            if (this.selectedImage > 0) {
                this.selectedImage -= 1;
            }
        }
    }
}
</script>

<style scoped>
.button {
    border: none;
    border-radius: 50%;
    width: 100px;
    height: 99px;
    background-color: transparent;
    margin-left: 10px;
    cursor: pointer;
}


.button.docker {
    background-color: #2396ED;
}

.button.sql {
    background-color: #FFFFFF;
}



.images button img {
    transition: transform 0.3s ease;
}

.images button:hover img {
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
    margin-right: 1.5rem;
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
    margin: 0 1.25rem 0 0.62rem;

}
</style>