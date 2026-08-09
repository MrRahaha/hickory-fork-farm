<script setup lang="ts"></script>

<template>
  <section id="family" class="section section--alt family">
    <div class="container">
      <div class="section-header">
        <p class="eyebrow">Meet the Family</p>
        <h2>The people behind the farm</h2>
        <p>A husband-and-wife team doing this one chore, one season, at a time.</p>
      </div>

      <div class="family__content">
        <div class="family__media">
          <img
            src="/katiekyle.jpg"
            alt="Katie and Kyle Spruill standing in front of The Farm on Hickory Fork sign"
            class="family__photo"
          />
        </div>

        <h3>Katie &amp; Kyle Spruill</h3>
        <p class="family__role">Owners &amp; Operators</p>
        <p class="family__bio">
          Katie and Kyle are the husband-and-wife team behind The Farm on Hickory Fork. Kyle handles
          the flock, the lambing, and anything that needs fixing &mdash; which, on a farm, is always
          something. Katie keeps the farm running day to day, from planning and record-keeping to
          getting eggs and orders into neighbors' hands. Together they've built a small operation
          they're proud to put their name on, and they love the relationships it's built with the
          folks who eat what they raise.
        </p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.family__content {
  max-width: 760px;
  margin: 0 auto;
  text-align: center;
}

.family__media {
  margin-bottom: 2rem;
  border-radius: var(--radius);
  overflow: hidden;
  box-shadow: var(--shadow-md);
}

.family__photo {
  width: 100%;
  aspect-ratio: 3 / 2;
  object-fit: cover;
  object-position: center 25%;
}

.family__content h3 {
  font-size: 1.5rem;
  margin-bottom: 0.25rem;
}

.family__role {
  color: var(--color-accent-dark);
  font-weight: 600;
  font-size: 0.95rem;
  margin-bottom: 1.25rem;
}

.family__bio {
  color: var(--color-text-muted);
  font-size: 1.05rem;
}
</style>
