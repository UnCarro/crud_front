<template> 

<div class="file">
  <form @submit.prevent="onSubmit" enctype="multipart/form-data">
    <div class='fields'>
      <label> ¡Introduce una imagen!</label><br/>
      <input 
      type="file" 
      ref="file"
      @change="onSelect"
      />

    </div>
    <div class ="fields">
      <button>Subir!</button>
    </div>
    <div class="message">
      <h5> {{ message }} </h5>
    </div>
  </form>
</div>

</template>

<script>
import axios from 'axios';
export default {
  name: "uploader",
  data(){
    return{
      file: "",
      message: ""
    }
  },
  methods: {
    onSelect(){
      const file = this.$refs.file.files[0];
      this.file = file;
    },
    async onSubmit(){
      const formData = new FormData();
      formData.append('file', this.file);
      try{
        await axios.post('/upload', formData);
        this.message = '¡Éxito!'
      }
      catch(err){
        console.log(err);
        this.message = 'Algo salió mal. Inténtalo nuevamente.'
      }
    }
  }
};
</script>
