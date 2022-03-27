<template>
  <div>
    <p>{{ person.name }}</p>
    <p>{{ person.age }}</p>
    <button @click="increaseAge">Next Year</button>
    <input type="text" :value="name" />
  </div>
  <div>{{ name }}{{ num != 0 ? num : null }}</div>
  <button @click="updateName">Update Name</button>
  <button @click="onClick" class="btn btn-primary">Click</button>
</template>

<script>
import { ref, reactive } from "vue";

export default {
  setup() {
    const name = ref("Raymond");
    const num = ref(0);

    const person = reactive({
      name,
      age: 18,
    });

    const updateName = () => {
      name.value = "Anything";
    };

    const onClick = () => {
      ++num.value;
    };

    const increaseAge = () => {
      ++person.age;
    };

    return {
      name,
      onClick,
      num,
      person,
      increaseAge,
      updateName,
    };
  },
};
</script>

<style></style>
