<template>
  <div class="comment">
    <slot :currentComment="comment"></slot>
    <Comment
        v-for="reply in comment.replies"
        :key="reply.id"
        :comment="reply"
    >
      <slot :currentComment="reply" />
    </Comment>
  </div>
</template>

<script>
export default {
  name: 'Comment',
  props: {
    comment: Object
  }
}
</script>