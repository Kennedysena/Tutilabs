<template>
    <div class="content">
        <p class="greeting">Olá</p>
        <p class="description">
            Agradecemos seu interesse em estagiar na Tutiplast e por participar do nosso teste
            de front-end. Este teste foi desenvolvido para avaliar suas habilidades e conhecimentos na área,
            portanto, não se preocupe se não conseguir completar todas as tarefas. O objetivo é entender seu processo de
            resolução de problemas e seu conhecimento técnico.
        </p>
    </div>
</template>

<script>
export default {
    name: 'Subtitle'
}
</script>

<style scoped>
.content {
    width: 100%;
    width: 32rem;
    color: #000000;
    margin-top: -25px;
}

p {
    font-family: 'Poppins', sans-serif;
    font-size: 0.68rem;
    text-align: justify;
    font-weight: 400;
    color: #000000;
    line-height: 0.75rem;
    letter-spacing: 0.06rem;
    margin: 0 0 0 0.625rem;
}
</style>