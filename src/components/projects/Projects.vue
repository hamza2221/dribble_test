<template>
  <div>
    <div id="projects">
      <ProjectList heading="NEW ORDERS" :projects="projects.new" />
      <ProjectList heading="IN PROGRESS" :projects="projects.inProgress" />
      <ProjectList
        heading="WAITING FOR BUYER"
        :projects="projects.waitingForBuyer"
      />
      <ProjectList heading="COMPLETED" :projects="projects.completed" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import ProjectList from './ProjectList.vue'

export default defineComponent({
  name: 'Projects',
  components: {
    ProjectList,
  },
  data() {
    return {
      projects: {
        new: [
          {
            userImgUrl: 'https://randomuser.me/api/portraits/med/men/75.jpg',
            id: Math.random() * 100,
            imgUrl: 'https://source.unsplash.com/90x90/?coding,programming',
            badge: 'NEW ORDER',
            days: 5,
            hours: 20,
            price: 320,
          },
          {
            userImgUrl: 'https://randomuser.me/api/portraits/med/men/76.jpg',
            id: Math.random() * 100,
            imgUrl: 'https://source.unsplash.com/90x90/?programming',
            badge: 'NEW ORDER',
            days: 2,
            hours: 340,
            price: 420,
          },
          {
            userImgUrl: 'https://randomuser.me/api/portraits/med/men/77.jpg',
            id: Math.random() * 100,
            imgUrl: 'https://source.unsplash.com/90x90/?coding',
            badge: 'NEW ORDER',
            days: 2,
            hours: 30,
            price: 420,
          },
          {
            userImgUrl: 'https://randomuser.me/api/portraits/med/men/78.jpg',
            id: Math.random() * 100,
            imgUrl: 'https://source.unsplash.com/90x90/?programming',
            badge: 'NEW ORDER',
            days: 2,
            hours: 30,
            price: 420,
          },
        ],
        inProgress: [
          {
            userImgUrl: 'https://randomuser.me/api/portraits/med/men/79.jpg',
            id: Math.random() * 100,
            imgUrl: 'https://source.unsplash.com/90x90/?coding,programming',
            badge: 'IN PROGRESS',
            days: 5,
            hours: 20,
            price: 320,
          },
          {
            userImgUrl: 'https://randomuser.me/api/portraits/med/men/80.jpg',
            id: Math.random() * 100,
            imgUrl: 'https://source.unsplash.com/90x90/?coding,graphics',
            badge: 'IN PROGRESS',
            days: 2,
            hours: 340,
            price: 420,
          },
          {
            userImgUrl: 'https://randomuser.me/api/portraits/med/men/81.jpg',
            id: Math.random() * 100,
            imgUrl: 'https://source.unsplash.com/90x90/?design,programming',
            badge: 'IN PROGRESS',
            days: 2,
            hours: 30,
            price: 420,
          },
        ],
        waitingForBuyer: [
          {
            userImgUrl: 'https://randomuser.me/api/portraits/med/men/82.jpg',
            id: Math.random() * 100,
            imgUrl: 'https://source.unsplash.com/90x90/?coding,graphics',
            badge: 'DELIVERED',
            days: 5,
            hours: 20,
            price: 320,
          },
          {
            userImgUrl: 'https://randomuser.me/api/portraits/med/men/83.jpg',
            id: Math.random() * 100,
            imgUrl: 'https://source.unsplash.com/90x90/?table,programming',
            badge: 'DELIVERED',
            days: 2,
            hours: 30,
            price: 420,
          },
        ],
        completed: [
          {
            userImgUrl: 'https://randomuser.me/api/portraits/med/men/84.jpg',
            id: Math.random() * 100,
            imgUrl: 'https://source.unsplash.com/90x90/?shoe,programming',
            badge: 'COMPLETED',
            days: 5,
            hours: 20,
            price: 320,
          },
          {
            userImgUrl: 'https://randomuser.me/api/portraits/med/men/85.jpg',
            id: Math.random() * 100,
            imgUrl: 'https://source.unsplash.com/90x90/?coding,chair',
            badge: 'COMPLETED',
            days: 2,
            hours: 340,
            price: 420,
          },
          {
            userImgUrl: 'https://randomuser.me/api/portraits/med/men/86.jpg',
            id: Math.random() * 100,
            imgUrl: 'https://source.unsplash.com/90x90/?coding,programming',
            badge: 'COMPLETED',
            days: 2,
            hours: 30,
            price: 420,
          },
        ],
      },
    }
  },
});
</script>

<style lang="scss">
#projects {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  grid-gap: 40px;
  justify-items: center;
}
</style>