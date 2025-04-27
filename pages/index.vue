<script setup>

useHead({
  link: [
    {
      rel: 'stylesheet',
      href: 'https://fonts.googleapis.com/css2?family=Instrument+Sans:wght@400;700&display=swap'
    }
  ]
})

const items = ref([
  ['Apple', 'Banana', 'Blueberry', 'Grapes', 'Pineapple'],
  ['Aubergine', 'Broccoli', 'Carrot', 'Courgette', 'Leek']
])
const value = ref('Apple')



</script>




<template>
    <header>
        <div class="flex flex-col items-center mt-8">
                <h1 class="text-4xl font-bold">GameExhange.com</h1>
                <p class="text-sm text-gray-600 italic">. . . Finally time to make your buddy download that game</p>
        </div>
        
    </header>


    <main>
        <div class="flex justify-center items-center w-full h-[80vh]">
            <div class="flex space-x-70 ">
                <div>
                    <p class="text-sm text-gray-600 italic">Choose your game</p>
                    <UInputMenu v-model="value" :items="items" />
                </div>
                <div>
                    <p class="text-sm text-gray-600 italic">Choose your currency</p>
                    <UInputMenu v-model="value" :items="items" />
                </div>
                
            </div>
        </div>
    </main>
</template>

<style scoped>
h1 {
  font-family: 'Instrument Sans', sans-serif;
}
</style>