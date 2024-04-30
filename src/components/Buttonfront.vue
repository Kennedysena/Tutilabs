<template>
    <button class="frontend-button" :class="{ inactive: !isActive }">
        front-end
        <img class="button-icon" :src="isActive ? '/src/assets/Happy.svg' : '/src/assets/Happyblack.svg'" />
    </button>
</template>

<script>
export default {
    name: 'ButtonFront',
    props: {
        isActive: {
            type: Boolean,
            default: true
        }
    }
}
</script>

<style scoped>
.frontend-button {
    height: 2.531rem;
    width: 7.594rem;
    border-radius: 1.5rem;
    font-size: 0.75rem;
    padding: 0.625rem 1rem;
    border: none;
    display: flex;
    align-items: center;
    margin-right: 1rem;
    background-color: black;
    color: white;
    cursor: pointer;
    text-align: center;
    font-size: 0.77rem;
    font-weight: 400;
    font-family: 'Poppins' sans-serif;
    border: 1px solid #000000;
}

.button-icon {
    margin-left: 1rem;

}

.frontend-button.inactive {
    background-color: #ECECEC;
    color: #181818;
}
</style>