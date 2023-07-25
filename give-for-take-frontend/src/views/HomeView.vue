<script setup>
import IconArrowLeft from '@/components/icons/IconArrowLeft.vue'
import IconArrowRight from '@/components/icons/IconArrowRight.vue'
import { ref } from 'vue';
import PostItem from '../components/PostItem.vue';
import { useRouter, useRoute } from 'vue-router';

const router = useRouter()


const lstTag = ref(['Backend', '.Net', 'Database', 'Message broker', 'Cache', 'Redis', 'Frontend', 'CSS', 'HTML', 'Javascript'])

function navigateToPostDetail() {
  router.push({
    name: 'postDetail',
    params: {
      id: 1
    }
  })
}
</script>

<template>
  <main class="main-content">
    <section class="tags-navigator flex items-center">
      <div class="test">
        <IconArrowRight />
      </div>
      <ul class="tags-list">
        <li class="tags-item" v-for="tag in lstTag" :key="tag">{{ tag }}</li>
      </ul>
      <div>
        <IconArrowLeft />
      </div>
    </section>

    <section>
      <PostItem v-for="postItem in lstPostItem" v-bind="postItem" :key="postItem.title"
        @on-click="navigateToPostDetail" />
    </section>
  </main>
</template>

<style lang="scss">
.main-content {
  // margin-top: 57px;
  padding-top: 24px;

  .tags-navigator {
    height: 55px;
    position: sticky;
    top: 0;
    background-color: #ffffff;

    .tags-list {
      white-space: nowrap;
      overflow: auto;
      scrollbar-width: none;
      padding: 0;

      &::-webkit-scrollbar {
        display: none;
      }

      .tags-item {
        list-style-type: none;
        display: inline-block;
        margin: auto 26px;
        color: $text-color-secondary;
      }
    }
  }

  .test {
    background: linear-gradient(270deg, rgba(255, 255, 255, 0) 0%, rgba(255, 255, 255, 0.75) 25%, rgba(255, 255, 255, 0.9) 50%, rgba(255, 255, 255, 1) 75%)
  }
}
</style>
