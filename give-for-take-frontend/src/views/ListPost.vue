<template>
  <PostItem></PostItem>
</template>

<script setup>
const postItem = {
  author: {
    authorName: 'Ted Goas',
    authorAvatarUrl: `https://miro.medium.com/v2/resize:fill:48:48/2*N9KgWVmQ_lZHNHZ6TR1Ldw.jpeg`,
  },
  publishDate: new Date(),
  title: `How Mid-Year Audits Can Solve Your Burn Out`,
  description: `Founders, you can have it all — just not all at once. —  Exhaustion. Burnout. Blasé. Unable to focus. Uninterested in anything. These are a few common underlying feelings when you have stretched your limits and can’t seem to make much progress. You seem to be doing everything but have nothing to show for it. Days go by, and your schedule is packed…`,
  thumbnailUrl: `https://miro.medium.com/v2/resize:fill:224:224/0*Gk5qp62b-TTA66fG`,
  tags: ['Self Improvement', 'Vuejs']
}
const lstPostItem = ref([{ ...postItem }, { ...postItem }, { ...postItem }, { ...postItem }, { ...postItem }, { ...postItem }, { ...postItem }, { ...postItem }, { ...postItem }, { ...postItem }, { ...postItem }, { ...postItem }, { ...postItem }, { ...postItem }, { ...postItem }, { ...postItem }])

import PostItem from '../components/PostItem.vue';
const props = defineProps({
  tag: String
})
</script>