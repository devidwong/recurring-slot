<template>
  <div id="app">
    <Comment
      v-for="comment in comments"
      :key="comment.id"
      :comment="comment"
      :detailsComponent="CommentDetails"
    >
      <template #details="{ currentComment }">
        <CommentDetails
            :currentComment="currentComment"
        />
      </template>
    </Comment>
  </div>
</template>

<script>
import Comment from "@/Comment";
import CommentDetails from "@/CommentDetails";
export default {
  components: {
    Comment,
    CommentDetails
  },
  data: () => ({
    CommentDetails,
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
  })
}
</script>
