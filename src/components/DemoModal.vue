<script setup>
import { ref } from "vue";
import {
  DialogRoot,
  DialogTrigger,
  DialogContent,
  DialogOverlay,
  DialogPortal,
  DialogTitle,
  DialogDescription,
  DialogClose,
} from "radix-vue";


const open = ref(false);
</script>

<template>
  <DialogRoot v-model:open="open">
    <DialogTrigger class="dialog-trigger">Open Modal Dialog</DialogTrigger>
    <DialogPortal>
      <DialogOverlay class="dialog-overlay" />
      <DialogContent class="dialog-content">
        <img class="dialog-image" src="./../assets/feedback.png" alt="" />
        <DialogTitle class="dialog-title">Provide Feedback</DialogTitle>
        <DialogDescription class="dialog-description">
          We appreciate your feedback. Please take a few minutes to let us know what you
          think of our product.
        </DialogDescription>
        <div class="button-group">
          <DialogClose class="cta">Give Feedback</DialogClose>
          <DialogClose>Cancel</DialogClose>
        </div>
      </DialogContent>
    </DialogPortal>
  </DialogRoot>
</template>

<style scoped>
.dialog-trigger {
  margin: 100px auto;
}

.dialog-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
}

.dialog-content {
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: #ffffff;
  box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
  border-radius: 10px;
  padding: 20px;
  max-width: 400px;
}

.dialog-image {
  display: block;
  width: 120px;
  margin: 0 auto 20px;
}

.dialog-title {
  font-size: 22px;
  font-weight: 600;
  margin: 0 0 10px;
}

.dialog-description {
  color: rgb(107, 114, 128);
  letter-spacing: 0.4px;
  line-height: 1.6;
  margin: 0;
}
</style>
