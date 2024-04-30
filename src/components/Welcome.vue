<template>
    <div class="titulo">
        <h1> Bem-vindo ao Tutilabs
            <img class="wave-icon" src="/src/assets/Bay.svg">
        </h1>
    </div>
</template>

<script>
export default {
    name: 'Titulo'
}
</script>

<style scoped>
.titulo {
    height: 12.5rem;
    width: 31.87rem;
    display: flex;
    margin: 0 0 0 0.625rem;
}

h1 {
    color: #424242;
    line-height: 5.25rem;
    font-size: 4.75rem;
    margin-top: -0.25rem;
    font-family: 'Poppins' sans-serif;
    font-weight: 500;
    text-align: left;
}

.wave-icon {
    animation: wave 1s infinite;
}

@keyframes wave {

    0%,
    100% {
        transform: rotate(0);
    }

    50% {
        transform: rotate(20deg);
    }
}
</style>