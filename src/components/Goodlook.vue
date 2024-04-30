<template>
  <div class="container">
    <div class="message">
      <p>Boa sorte!</p>
    </div>
    <div class="image-container">
      <img src="/src/assets/Unicornio.svg" alt="Imagem">
    </div>

  </div>
</template>

<script>
export default {
  name: 'Goodlook'
}
</script>

<style scoped>
.container {
  width: 44.31rem;
  height: 19.43rem;
  background-color: #FEAB5E;
  border-radius: 1.56rem;
  margin: 1.25rem 0 1.87rem 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  overflow: hidden;
}

.message {
  margin-top: 1.25rem;
  margin-right: 30.625rem;

}

.message p {
  font-family: 'Poppins', sans-serif;
  font-size: 2.43rem;
  font-weight: 300;
  line-height: 2.63rem;
  text-align: left;
  margin: 0 0.25rem;
  color: #4C577D;


}

.image-container {
  width: 100%;
  box-sizing: border-box;

}

.image-container img {
  width: 44%;
  height: 100%;
  object-fit: cover;
  margin-left: 396px;

}
</style>