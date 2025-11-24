<template>
  <div class="container">
    <div class="inner-container">
        <p>Magazalarımız</p>
        <p>Kampanyalar</p>
    </div>
    <div class="inner-container"> </div>
  </div>
</template>

<script setup>
</script>

<style scoped>
 *{
    margin:0px;
    color:whitesmoke;
    box-sizing: border-box;
 }

.container{
    width:100%;
    height: 30px;
    background-color: #151B54;
    display: flex;
    flex-direction: row;
    padding-left:40px;
    padding-right: 40px;
}

.inner-container{
    width: 50%;
    margin-top:5px;
}

p{
  margin-left:10px;
  display:inline-block;
  font-family: 'Gotham' , sans-serif;
  font-size: 12px;
}
</style>