<template>
  <div class="reaction-box">
    <button class="reaction-btn">
      <i class="far fa-smile" style="font-size: 15px;"></i>
    </button>
    <button class="reaction-btn" v-if="this.$props.userId === this.user._id">
      <i class="fas fa-pen"></i>
    </button>
    <button class="reaction-btn">
      <i class="fas fa-ellipsis-h" style="font-size: 15px;"></i>
    </button>
  </div>
</template>

<script>
import { useState } from "@u3u/vue-hooks";

export default {
  props: ["userId"],
  setup() {
    const { user } = useState("auth", ["user"]);

    return {
      user
    };
  }
};
</script>

<style lang="scss">
.reaction-box {
  display: inline-flex;
  justify-content: space-between;
}

.reaction-btn {
  border: none;
  border-radius: 50px;
  padding: 0.4rem;
  color: white;
  background-color: $bg_dark;
  cursor: pointer;
  outline: none;
}

.reaction-btn:hover {
  background-color: $bg_lighter;
}
</style>