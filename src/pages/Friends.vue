<template>
  <div>
    <h1 class="friends-title text-center space-bottom">Friends & Guestbook</h1>

    <div class="friends-container text-center space-bottom">
      <a
        class="btn"
        v-for="friend in friends"
        :key="friend.id"
        :href="friend.link"
        target="_blank"
        :style="friend.style"
        ><g-image class="avatar" alt="avatar" :src="friend.avatar" blur="5" />
        <span>{{ friend.id }}</span></a
      >
    </div>

    <div class="post-comments">
      <div id="disqus_thread" />
    </div>
  </div>
</template>

<script>


export default {
  metaInfo: {
    title: 'Friends',
  },
  data() {
    return {
      friends: [
        {
          id: '@Patrick Wu',
          link: 'https://patrickwu.space/',
          avatar: 'https://avatars0.githubusercontent.com/u/15316889?s=160',
          style: 'color: #fff; background-color: #61a3cf',
        },
      ],
    }
  },
}
</script>

<style lang="scss">
.friends-container {
  max-width: var(--content-width);
  margin-left: auto;
  margin-right: auto;

  .btn {
    margin: 0.3em 0.6em 0.3em 0;
    text-decoration: none;
    padding: 0.5em;
    border-radius: var(--radius);
    display: inline-block;
    overflow: hidden;
    position: relative;

    .avatar {
      position: absolute;
      top: 0;
      left: 0;
      bottom: 0;
      width: 48px;
      height: 48px;
      border-radius: var(--radius);
      background-color: #fff;
      transform: rotate(20deg) translate(-15%, 0%);
    }

    span {
      margin-left: 2.6em;
    }
  }

  .note {
    margin: calc(var(--space) / 2) 0;
    font-size: 0.9em;
    opacity: 0.8;
  }
}

.post-comments {
  padding: calc(var(--space) / 2);
  max-width: var(--content-width);
  margin: 0 auto;
  font-family: var(--base-font-family);
}
</style>
