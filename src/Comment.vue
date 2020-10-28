<template>
  <div class="comment">
    <slot name="details" :currentComment="comment"></slot>
    <Comment
        v-for="reply in comment.replies"
        :key="reply.id"
        :comment="reply"
        :detailsComponent="detailsComponent"
    >
      <slot :currentComment="reply" />
      <template #details="{ currentComment }">
        <component
            :is="detailsComponent"
            :currentComment="currentComment"
            :detailsComponent="detailsComponent"
        />
      </template>
    </Comment>
  </div>
</template>

<script>
export default {
  name: 'Comment',
  props: {
    comment: Object,
    detailsComponent: Object
  }
}
</script>