<template>
  <div id="app">
    <Comment
      v-for="comment in comments"
      :key="comment.id"
      :comment="comment"
    >
      <template #default="{ currentComment }">
        <div>by {{ currentComment.author }}</div>
      </template>
    </Comment>
  </div>
</template>

<script>
import Comment from "@/Comment";
export default {
  data: () => ({
    comments: [
      {
        id: 1,
        author: 'Goodman',
        replies: [
          {
            id: 11,
            author: 'RepeatingMan',
            replies: [
              {
                id: 111,
                author: 'ExpectedMan',
                replies: [
                  {
                    id: 1111,
                    author: 'MelodyOfFuture',
                    replies: []
                  }
                ]
              }
            ]
          }
        ]
      }
    ]
  }),
  components: {
    Comment
  }
}
</script>
