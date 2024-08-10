<template>
    <form class="form m-5 p-5 bg-secondary row">

        <div class="col-md-6 form-group">    
            <input type="text" ref ="nom" class="form-control" placeholder="Nom"> 
        </div>
        <div class="col-md-6 form-group">    
            <input type="text" reg ="prenom" class="form-control" placeholder="Prenom">
        </div>
        <div class="col-md-6 form-group">    
            <input type="text" ref ="email" class="form-control" placeholder="Email"> 
        </div>
        <div class="col-md-6 form-group">    
            <input type="text" reg ="tel" class="form-control" placeholder="Téléphone">
        </div>
        
        <div class="col-md-12">
            <button class="btn">Enregistrer</button>
        </div>
    </form>
</template>
<script>
export default {
  name: 'ClientComponent',
  data(){
    return {}
  }
}
</script>
<style>
    
</style>