<template>
  <div class="column is-3">
    <div class="card">
      <header class="card-header">
        <p class="card-header-title">
          {{badge.Title}}
        </p>
      </header>
      <div class="card-image">
        <nav class="level">
          <div class="level-item">
            <figure v-if="badge.Image1" class="image is-64x64">
              <img
                class="is-rounded"
                v-bind:src="badge.Image1"
                alt="Badge Image 1"
              />
            </figure>
            <b-icon v-if="badge.Icon" v-bind:icon="badge.Icon" size="is-large" v-bind:type="badge.IconType"/>
            <figure v-if="badge.Image2" class="image is-64x64">
            <img class="is-rounded"
                v-bind:src="badge.Image2"
                alt="Badge Image 2"
              />
            </figure>
          </div>
        </nav>
      </div>
      <div class="card-content">
        <div class="media">
          <div class="media-content">
            <p class="has-centered-text">
            {{badge.PlayerName}} {{badge.Description}}
          </p>
          <small v-if="badge.Blurb">{{badge.Blurb}}</small>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Match from "@/components/Match";

import _ from "lodash";
import Api from "@/api";
import { mapGetters } from "vuex";

export default {
    name: "Badge",
  props: ["badge"],
  data() {
    return {
    };
  }
};
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.card-image{
  padding-top:1rem;
}

</style>