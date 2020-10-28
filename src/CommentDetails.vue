<template>
  <div>
    by {{ currentComment.author }}
  </div>
</template>

<script>
export default {
  name: "CommentDetails",
  props: {
    currentComment: Object
  }
}
</script>
