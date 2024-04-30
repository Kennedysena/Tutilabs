<template>
    <div class="custom-component">
        <div class="background">
            <img src="/src/assets/Union.svg" alt="Imagem de fundo" />
            <img src="/src/assets/iPhone.svg" alt="Imagem do iPhone" class="iphone-image" />
            <div class="overlay">
                <p class="text">veja mais sobre nossos sistemas</p>
                <button class="button">
                    <p class="button-text">Visualizar</p>
                    <img src="/src/assets/Seta.svg" alt="Seta" class="arrow-icon" />
                </button>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'About',

}
</script>

<style scoped>
.custom-component {
    width: 18.438rem;
    height: 18.875rem;
    position: relative;
}

.background {
    width: 100%;
    height: 100%;
    background-color: #4C577D;
    border-radius: 25px;
    overflow: hidden;
    position: relative;
}

.iphone-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
    position: absolute;
    top: -3%;
    left: -4%;
    z-index: 1;

}

.overlay {
    width: 17.8rem;
    height: 5.5rem;
    top: 12.93rem;
    border-radius: 18px;
    margin: 0 0 0 0.3rem;
    position: absolute;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 2;
    backdrop-filter: blur(0.93rem);
    background-color: rgba(245, 245, 245, 0.5);
    flex-direction: column;
}

.text {
    font-size: 1rem;
    line-height: 0.87rem;
    text-align: center;
    justify-content: center;
    display: flex;
    font-family: 'Poppins', sans-serif;

}

.button {
    height: 1.87rem;
    width: 7rem;
    background-color: #4C577D;
    border: none;
    border-radius: 1.25rem;
    margin-left: 9.35rem;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 7.75px, 13.95px, 7.75px;
    margin-top: 0.18rem;
}

.button-text {
    font-size: 0.77rem;
    text-align: center;
    margin-right: 0.31rem;
    font-family: 'Poppins', sans-serif;
    font-weight: 400;

}

.arrow-icon {
    width: 1.13rem;
    height: 0.96rem;
}
</style>