<template>
  <div id="project-card">
    <i class="fas fa-ellipsis-h"></i>
    <div class="card-body">
      <img :src="project.imgUrl" alt="project" />
      <div class="project-details">
        <span class="badge" :style="{ 'background-color': badgeBGC }">{{
          project.badge
        }}</span>
        <p class="days">
          <i class="far fa-clock"></i> {{ project.days }} days left
        </p>
        <p class="price-time">
          {{ project.hours }}hrs | <strong>${{ project.price }}</strong>
        </p>
      </div>
    </div>
    <div class="card-footer">
      <span>View Order</span>
      <i class="far fa-comment"></i>
      <img :src="project.userImgUrl" alt="user" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import ProjectInterface from '../../interfaces/Project'

export default defineComponent({
  name: 'ProjectCard',
  props: {
    project: {
      required: true,
      type: Object  as PropType<ProjectInterface>,
    },
  },
  computed: {
    badgeBGC() {
      switch (this.project.badge) {
        case 'NEW ORDER':
          return '#ffecd0'
          break
        case 'IN PROGRESS':
          return '#d3dffb'
          break
        case 'DELIVERED':
          return '#fdd6e9'
          break
        case 'COMPLETED':
          return '#caf4e1'
          break

        default:
          return '#e9e9e9'
          break
      }
    },
  },
})
</script>

<style lang="scss">
#project-card {
  display: flex;
  background-color: #fff;
  flex-direction: column;
  padding-top: 10px;
  border-radius: 10px;
  box-shadow: 0 2px 2px 2px rgba($color: #333, $alpha: 0.1);
  min-width: 280px;

  & > i {
    align-self: flex-end;
    margin-right: 20px;
    color: lightgray;
  }

  .card-body {
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding: 20px;

    & > img {
      border-radius: 5px;
      border: 2px solid #e9e9e9;
      width: 80px;
      height: auto;
    }

    .project-details {
      display: flex;
      flex-direction: column;
      align-items: flex-end;

      .badge {
        font-size: 0.7rem;
        padding: 3px 20px;
        border-radius: 20px;
        background-color: #e9e9e9;
        font-weight: 700;
      }

      .days {
        font-size: 0.8rem;
      }

      .price-time {
        font-size: 1rem;
        margin: 5px 0;
      }
    }
  }

  .card-footer {
    border-top: 1px solid #e9e9e9;
    padding: 10px 20px;
    display: flex;
    align-items: center;

    & > span {
      font-weight: 600;
      color: #a0a0a4;
    }

    & > i {
      margin-left: auto;
      margin-right: 20px;
      font-size: 1.5rem;
      color: lightgray;
    }

    & > img {
      widows: 25px;
      height: 25px;
      border: 1px solid #e9e9e9;
      border-radius: 50%;
    }
  }
}
</style>
