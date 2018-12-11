<template>
  <div class="upvote">
    <h2 class="title has-text-centered dividing-header">UpVote!</h2>
    <div class="section">
      <article
        v-for="submission in submissions"
        v-bind:key="submission.id"
        class="media"
        v-bind:class="{'blue-border': submission.votes >= 20}"
      >
        <vote-component v-bind:submission="submission" v-bind:submissions="submissions"></vote-component>
      </article>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Vote from "@/components/Vote.vue";

export default {
  data: function() {
    return {
      baseUrl: process.env.BASE_URL,
      submissions: [
        {
          id: 1,
          title: "Yellow Pail",
          description: "On-demand sand castle construction expertise.",
          url: "#",
          votes: 16,
          avatar: process.env.BASE_URL + "images/avatars/daniel.jpg",
          submissionImage:
            process.env.BASE_URL + "images/submissions/image-yellow.png"
        },
        {
          id: 2,
          title: "Supermajority: The Fantasy Congress League",
          description:
            "Earn points when your favorite politicians pass legislation.",
          url: "#",
          votes: 11,
          avatar: process.env.BASE_URL + "images/avatars/kristy.png",
          submissionImage:
            process.env.BASE_URL + "images/submissions/image-rose.png"
        },
        {
          id: 3,
          title: "Tinfoild: Tailored tinfoil hats",
          description: "We have your measurements and shipping address.",
          url: "#",
          votes: 17,
          avatar: process.env.BASE_URL + "images/avatars/veronika.jpg",
          submissionImage:
            process.env.BASE_URL + "images/submissions/image-steel.png"
        },
        {
          id: 4,
          title: "Haught or Naught",
          description: "High-minded or absent-minded? You decide.",
          url: "#",
          votes: 9,
          avatar: process.env.BASE_URL + "images/avatars/molly.png",
          submissionImage:
            process.env.BASE_URL + "images/submissions/image-aqua.png"
        }
      ]
    };
  },
  components: {
    "vote-component": Vote
  }
};
</script>

<style>
.dividing-header {
  margin-top: 1em;
  margin-bottom: 2em;
}

.section {
  padding: 2rem 1.5rem;
}

.media {
  max-width: 600px;
  margin: 0 auto;
  border: 1px solid #e6e7e9;
  padding: 1em 1.5em 0.5em 1.5em;
  border-radius: 0.3em;
}

.media + .media {
  margin-top: 1.5rem;
}

.blue-border {
  border: 1px solid #3373dc !important;
}

.tag {
  font-size: 0.6rem !important;
}

.icon {
  cursor: pointer;
}

.image.is-24x24 {
  display: inline;
  position: relative;
  top: 5px;
  border-radius: 20px;
}
</style>