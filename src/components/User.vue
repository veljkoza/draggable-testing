<template>
    <li
        class="bg-green-300 p-4 mt-3 rounded-lg shadow-lg cursor-move flex items-center justify-between"
      >
        <div class="flex items-center">
          <img
            :src="user.avatar"
            :alt="user.name"
            class="h-10 w-10 rounded-full mr-4"
          />
          <p class="font-semibold tracking-wide font-sans">{{ user.name }}</p>
        </div>
        <div class="flex items-center">
          <button aria-label="Edit user" class="mr-4 text-green-600 hover:text-green-900 outline-none focus:shadow-outline  transition-colors">
            <EditIcon/>
          </button>
          <button class="text-pink-500 hover:text-pink-700  outline-none focus:shadow-outline transition-colors">
            <Trash2Icon/>
          </button>
        </div>
      </li>
</template>

<script>
import { EditIcon, Trash2Icon } from "vue-feather-icons";

    export default {
        props:{
            user:{
                type:Object,
                default:()=>({})
            }
        },
        components: {
    EditIcon,
    Trash2Icon,
  },
    }
</script>

<style lang="scss" scoped>

</style>