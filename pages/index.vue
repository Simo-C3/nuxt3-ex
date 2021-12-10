<template>
  <div class="flex flex-col items-center justify-center h-full space-y-4 text-xl">
    <p>Here's a counter:</p>
    <div class="flex items-center justify-center">
      
      <button @click="counter++" v-if="name === 'hoge'" class="px-4 py-2 font-bold text-white bg-green-500 rounded hover:bg-green-700">
        +
      </button>
      <span class="mx-2">{{ counter }}</span>
      <button @click="counter--" class="px-4 py-2 font-bold text-white bg-green-500 rounded hover:bg-green-700">
        -
      </button>
    </div>
    <div v-for="item in items" :key="item.id">
        <post :item="item"/>
    </div>
    <div>
        <button @click="flag = !flag">click</button>
        <p v-if="flag">押した</p>
        <p v-else>押してない</p>
    </div>
    <div>
        <form>
            <label>
                test:
                <input v-model="text" placeholder="入力ください" type="text">
            </label>
        </form>
        <p>{{ text }}</p>
    </div>
  </div>
</template>

<script lang="ts">
import Post from "~/components/Post.vue"

export default ({
  layout: 'custom',
  components:{
      post: Post
  },
  data() {
    return {
      counter: 0,
      items: [
          {
              id: "1",
              name: "huga1",
              content: "This is pen."
          },
          {
              id: "2",
              name: "huga2",
              content: "This is apple."
          },
          {
              id: "3",
              name: "huga3",
              content: "This is car."
          },
          {
              id: "4",
              name: "huga4",
              content: "This is cat."
          },
      ],
      flag: false,
      name: "hoge",
      text: ""
    }
  }
})
</script>