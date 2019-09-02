<template>
  <div>
    {{ fullName }}
    <div>
      firstName:
      <input v-model="firstName" />
    </div>
    <div>
      lastName:
      <input v-model="lastName" />
    </div>
  </div>
</template>
<script>
export default {
  data: function() {
    return {
      firstName: "Foo",
      lastName: "Bar",
      fullName: "Foo Bar"
    };
  },
  watch: {
    firstName: function(val) {
      window.clearTimeout(this.timer);
      this.timer = setTimeout(() => {
        this.fullName = val + " " + this.lastName;
      }, 1000);
    },
    lastName: function(val) {
      window.clearTimeout(this.timer);
      this.timer = setTimeout(() => {
        this.fullName = this.firstName + " " + val;
      }, 1000);
    }
  }
};
</script>