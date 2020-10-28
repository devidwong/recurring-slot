<template>
  <div class="comment">
    <component
        :is="detailsComponent"
        :currentComment="comment"
    />
          <Comment
              v-for="reply in comment.replies"
              :key="reply.id"
              :comment="reply"
              :detailsComponent="detailsComponent"
          >
            <template #default="{ currentComment }">
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