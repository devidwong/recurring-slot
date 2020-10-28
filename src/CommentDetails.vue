<template>
  <div>
    by {{ currentComment.author }}
  </div>
</template>

<script>
export default {
  props: {
    currentComment: Object
  }
}
</script>
