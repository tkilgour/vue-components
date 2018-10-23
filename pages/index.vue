<template>
  <div class="text-center">
    <Header></Header>
    <main class="max-w-lg mx-auto mt-8 px-4">
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Distinctio, aperiam voluptate porro numquam reprehenderit voluptates repudiandae totam et vitae nisi amet! Eaque quod amet animi nihil quibusdam fugit hic architecto!</p>
      <div class="my-12 md:-mx-4 flex flex-wrap justify-center">
        <div class="w-100 md:flex-1 flex flex-col md:px-4 py-8">
          <InteractiveCards></InteractiveCards>
          <p class="mt-6">An interactive card component that can cycles through given inputs.</p>
        </div>
        <div class="w-100 md:flex-1 flex flex-col md:px-4">
          <CountdownTimer
            class="flex-1 flex justify-center items-center text-3xl text-green-dark"
            :handleTimerEnd="() => null"
          ></CountdownTimer>
          <p class="mt-6">
            A countdown timer that receives a
            <code>timerLength</code>&nbsp;and a
            <code>handleTimerEnd</code>function.
          </p>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
export default {};
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
</style>
