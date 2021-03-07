<template>
  <div>
    <MyComponent/>
  </div>
</template>

<script>
// @ is an alias to /src
import MyComponent from '@/components/MyComponent.vue'

export default {
  name: 'User',
  components: {
    MyComponent
  }
}
</script>
