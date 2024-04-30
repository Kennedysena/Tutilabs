<template>
    <button class="backend-button" :class="{ inactive: !isActive }">
        back-end
        <img class="button-icon" :src="isActive ? '/src/assets/Sadwhite.svg' : '/src/assets/Sad.svg'" />
    </button>
</template>

<script>
export default {
    name: 'ButtonBack',
    props: {
        isActive: {
            type: Boolean,
            default: true
        }
    }
}
</script>

<style scoped>
.backend-button {
    height: 2.531rem;
    width: 7.594rem;
    border-radius: 1.5rem;
    font-size: 0.75rem;
    padding: 0.625rem 1rem;
    background-color: #181818;
    border: 0.063rem solid #181818;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    font-weight: 400;
    font-family: 'Poppins', sans-serif;
    cursor: pointer;
}

.button-icon {
    margin-left: 0.313rem;
}

.backend-button.inactive {
    background-color: #ECECEC;
    color: #181818;

}
</style>