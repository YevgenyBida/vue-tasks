<script>
export default {
  name: "Counter",
  props: {
    title: String
  },
  data(){
    return {
      count: 0,
    }
  }
}
</script>

<template>
  <div>
    <h2>{{count}}</h2>
    <button class="btn" @click = "count++">+</button>
    <button class="btn" @click = "count--">-</button>
    {{ title }}
  </div>
</template>