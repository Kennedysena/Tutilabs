<template>
    <div class="texto-rolavel">
        <div class="container">
            <div class="line">
                <div>
                    <p class="name">{{ techname }}</p>
                </div>
            </div>
            <div class="header">
                <div class="scrollable-content">
                    <p class="paragrafo">{{ description }}</p>

                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Description',
    props: {
        description: {
            type: String,
            default: ''
        },
        techname: {
            type: String,
            default: ''
        }
    },
    watch: {
        description(newDescription) {
            this.$emit('update-description', newDescription);
        },
        descriptionBack(newDescriptionBack) {
            this.$emit('update-description-back', newDescriptionBack);
        },
        techname(newTechName) {
            this.$emit('update-techname', newTechName);
        }
    }
}
</script>

<style scoped>
.texto-rolavel {
    display: flex;
    flex-direction: column;
    align-items: flex-start;

}


.container {
    width: 24.37rem;
    height: 19.43rem;
    border-radius: 25px;
    border: 1px solid #000000;
    overflow: hidden;
}

.line {
    width: 25rem;
    height: 3.12rem;
    border-bottom: 1px solid #000000;
    display: block;

}


.scrollable-content {
    overflow-y: auto;
    max-height: 15.62rem;
    margin: 0.62rem 0.62rem 0px 0px;

}


.paragrafo {
    margin: 0.93rem 1.25rem;
    text-align: left;
    font-size: 0.75rem;
    word-wrap: break-word;
    font-family: 'Poppins' sans-serif;
    font-weight: 500;

}

.name {
    margin: 0.25rem 15.625rem 0 0;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 1.5rem;
    font-family: 'Poppins' sans-serif;
    font-weight: 500;

}
</style>