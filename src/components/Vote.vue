<template>
  <div class="vote" style="display: flex; width: 100%">
    <figure class="media-left">
      <img :src="submission.submissionImage" alt class="image is-64x64">
    </figure>
    <div class="media-content">
      <div class="content">
        <p>
          <strong>
            <a :href="submission.url" class="has-text-info">{{ submission.title }}</a>
            <span class="tag is-small">#{{ submission.id }}</span>
          </strong>
          <br>
          {{ submission.description }}
          <br>
          <small class="is-size-7">
            Submitted by:
            <img :src="submission.avatar" class="image is-24x24" alt>
          </small>
        </p>
      </div>
    </div>
    <div class="media-right">
      <span class="icon is-small" @click="upvote(submission.id)">
        <i class="fa fa-chevron-up"></i>
        <strong class="has-text-info">{{ submission.votes }}</strong>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  props: ["submission", "submissions"],
  methods: {
    upvote(submissionId) {
      const submission = this.submissions.find(
        submission => submission.id === submissionId
      );
      submission.votes++;
    }
  }
}
</script>
