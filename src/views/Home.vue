<template>
  <div class="home">
    <div class="container">
      <div class="col-md-6 offset-md-3 mt-5">
        <h1>Кто вы?</h1>
        <button class="btn btn-success" to="/register/customer">Покупатель</button>
        <button class="btn btn-primary" to="/register/worker">Рабочий</button>
        <button class="btn btn-warning" to="/register/director">Директор</button>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'home',
  
}
</script>

<style scoped>

</style>
