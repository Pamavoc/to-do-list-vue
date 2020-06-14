<template>
    <div class="container mt-5">
        
        <h1> Do the job !</h1>
        
        <form class="form-group">

            <div>
                <label for='action'>Les choses doivent se faire</label>
                <input v-model="formData.tache" type="text" id="action" class="form-control">
            </div>
        </form>    

        <button v-on:click.prevent="creationTache" class="btn btn-primary mb-3">Créer une tache</button>


        <ul>
            <li v-bind:key="index" v-for="(tache, index) in tableauTaches">
                <tache v-bind:id="index" :tache="tache" :suppression="suppression"></tache>
                <!-- id qui est l'index de l'element du tableau -->
            </li>
            
            

        </ul>


    </div>
    


</template>

<script>

//on veut les utiliser partout donc export
import Tache from './Tache'


export default {



    name:'Contenu',
    data(){
        return {
            formData: {
                tache: ''
            },
            tableauTaches: ['JavaScript', 'Vue', 'Python']
        }
    },
    methods: {
        creationTache:function() {
            this.tableauTaches.push(this.formData.tache)
            this.formData.tache = ''
            //two ways data-binding
        },

         suppression:function(e) {
            //console.log(e.target.parentNode.id);
            this.tableauTaches.splice(e.target.parentNode.id, 1)
        },
     },
  
    components: {
        'tache': Tache
    }
    
}



</script>



<style>


h1 {
    margin-top: 100px !important;
}

ul {
    list-style-type:none;
}
</style>