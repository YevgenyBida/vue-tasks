
<template>
  <div id="main_div">
    <button class = 'btn' @click = "loudImg()">get image</button>

  </div>
</template>



<script>
import Counter from "@/components/Counter.vue";
export default {
  components: {
    Counter
  },
  data() {
    return {
    }
  },
  methods: {
    async loudImg() {
      const response = await fetch('https://cataas.com/cat');
      console.log(response);
      const storageImg = await response.blob();
      const img = document.createElement('img');
      const mainDiv = document.getElementById('main_div');
      img.style = 'width:150px;border-radius:50%'
      img.src = URL.createObjectURL(storageImg);
      mainDiv.appendChild(img);
      setTimeout(()=>{
        img.remove();
      },3000)
    },

  }
}
</script>


