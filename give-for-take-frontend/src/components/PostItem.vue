<script setup>
const props = defineProps({
  author: {
    authorName: String,
    authorAvatarUrl: String,
  },
  publishDate: Date,
  title: String,
  description: String,
  thumbnailUrl: String,
  tags: Array
})

// const emit = defineEmits(['onClick'])
</script>

<template>
  <article class="post-item" @click="$emit('onClick')">
    <div class="post-info">
      <img class="avatar-author" :src="props.author.authorAvatarUrl" alt="avatar author">
      <span class="author-name text-primary">{{ props.author.authorName }}</span>
      <span class="text-secondary">{{ props.publishDate.toLocaleString() }}</span>
    </div>
    <div class="post-content flex justify-around">
      <div class="post-content-bref">
        <h2 class="title">{{ props.title }}</h2>
        <p class="description">{{ props.description }}</p>
      </div>
      <img :src="props.thumbnailUrl" alt="">
    </div>
    <div class="tags">
      <span class="tag" v-for="tag in props.tags" :key="tag">{{ tag }}</span>
    </div>
  </article>
</template>

<style lang="scss" scoped>
.post-item {
  border-bottom: 1px solid $color-tertiary;
  padding-top: 2.4rem;

  .post-info {
    display: flex;
    gap: 0.8rem;
    align-items: center;

    .avatar-author {
      width: 2.4rem;
      height: 2.4rem;
      border-radius: 50%;
    }
  }

  .post-content {
    height: 5.7rem;
    margin-top: 1.2rem;

    .post-content-bref {
      .title {
        color: $text-color-primary;
        font-size: 1.6rem;
        line-height: 2rem;
        max-height: 4rem;
        font-weight: 700;
      }

      .description {
        display: none;
      }
    }
  }

  .tags {
    display: flex;
    gap: .8rem;

    .tag {
      background-color: $color-tertiary;
      padding: 2px 8px;
      margin: 1.6rem 0;
      display: inline-block;
      border: 1px solid $color-tertiary;
      border-radius: 100px;
    }
  }
}

@media screen and (min-width: 768px) {
  .post-item {
    cursor: pointer;

    .post-content {
      height: 11.2rem;

      .post-content-bref {
        .title {
          font-size: 2rem;
        }

        .description {
          display: -webkit-box;
          color: #242424;
          font-size: 1.6rem;
          line-height: 2.4rem;
          -webkit-line-clamp: 3;
          font-weight: 400;
          overflow: hidden;
          -webkit-box-orient: vertical;
          font-family: source-serif-pro, Georgia, Cambria, "Times New Roman", Times, serif;
        }
      }
    }
  }
}
</style>