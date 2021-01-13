<template>
  <div
    id="app"
    class="min-h-screen w-screen bg-blue-900 flex items-center justify-center"
  >
    <div class="w-full max-w-md text-center">
      <p class="text-white text-3xl font-semibold">List 1</p>
      <draggable
        tag="ul"
        :list="users"
        class="w-full max-w-md border-transparent transition-colors"
        :class="
          users.length === 0
            ? 'border-red-500 border-2 border-dotted min-h-5 rounded-lg'
            : ''
        "
        animation="200"
        ghost-class="moving-card"
        filter=".action-button"
        group="all-users"
      >
        <user v-for="user in users" :key="user.id" :user="user" />
      </draggable>
    </div>
    <div class="w-full max-w-md text-center ml-10">
      <p class="text-white text-3xl font-semibold">List 2</p>
      <draggable
        tag="ul"
        :list="newUsers"
        class="w-full max-w-md border-transparent transition-colors"
        :class="
          newUsers.length === 0
            ? 'border-red-500 border-2 border-dotted min-h-5 rounded-lg'
            : ''
        "
        animation="200"
        ghost-class="moving-card"
        filter=".action-button"
        group="all-users"
      >
        <user v-for="user in newUsers" :key="user.id" :user="user" />
      </draggable>
    </div>
  </div>
</template>

<script>
import Draggable from "vuedraggable";
import User from "@/components/User";
export default {
  name: "App",
  components: {
    Draggable,
    User,
  },
  data() {
    return {
      users: [
        {
          id: 1,
          name: "Adrian Schubert",
          avatar:
            "https://pickaface.net/gallery/avatar/unr_sample_161118_2054_ynlrg.png",
        },
        {
          id: 2,
          name: "Violet Gates",
          avatar: "https://pickaface.net/gallery/avatar/freud51c8b3f65e7dc.png",
        },
        {
          id: 3,
          name: "Steve Jobs",
          avatar: "https://pickaface.net/gallery/avatar/Opi51c74d0125fd4.png",
        },
        {
          id: 4,
          name: "Yassine Smith",
          avatar:
            "https://pickaface.net/gallery/avatar/unr_yassine_191124_2012_3gngr.png",
        },
        {
          id: 5,
          name: "Senior Saez",
          avatar:
            "https://pickaface.net/gallery/avatar/elmedinilla541c03412955c.png",
        },
      ],
      newUsers: [
        {
          id: 6,
          name: "Prndrian Schubert",
          avatar:
            "https://pickaface.net/gallery/avatar/unr_sample_161118_2054_ynlrg.png",
        },
        {
          id: 7,
          name: "Smrdolet Kapije",
          avatar: "https://pickaface.net/gallery/avatar/freud51c8b3f65e7dc.png",
        },
        {
          id: 8,
          name: "Stevo Poslovi",
          avatar: "https://pickaface.net/gallery/avatar/Opi51c74d0125fd4.png",
        },
        {
          id: 9,
          name: "Jasam Smith",
          avatar:
            "https://pickaface.net/gallery/avatar/unr_yassine_191124_2012_3gngr.png",
        },
        {
          id: 10,
          name: "Stariji Saez",
          avatar:
            "https://pickaface.net/gallery/avatar/elmedinilla541c03412955c.png",
        },
      ],
    };
  },
};
</script>

<style lang="postcss">
.moving-card {
  @apply opacity-50 bg-green-200 border border-purple-500;
}

.min-h-5 {
  min-height: 5rem;
}
</style>
