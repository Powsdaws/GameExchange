<script setup>

useHead({
  link: [
    {
      rel: 'stylesheet',
      href: 'https://fonts.googleapis.com/css2?family=Instrument+Sans:wght@400;700&display=swap'
    }
  ]
})

const games = ref([
  ['Valorant', 'Fortnite', 'League of Legends', 'Minecraft', 'Overwatch'],
  ['Call of Duty', 'Counter-Strike', 'PUBG', 'Apex Legends', 'Dota 2']
])

const currencies = ref([
    ['Apple', 'Banana', 'Blueberry', 'Grapes', 'Pineapple'],
    ['Aubergine', 'Broccoli', 'Carrot', 'Courgette', 'Leek']
])

const gameValue = ref(null)
const currencyValue = ref(null)

const converted = ref(false)

const convert = () => {
    if (gameValue.value && currencyValue.value !== null) {
    converted.value = true
    }
}


</script>




<template>
    <header>
        <div class="flex flex-col items-center mt-8">
                <h1 class="text-4xl font-bold">GameExhange.com</h1>
                <p class="text-sm text-gray-600 italic">. . . Finally time to make your buddy download that game</p>
        </div>
        
    </header>

    <!-- Main content -->
    <main>
        <div class="flex justify-center items-center w-full mt-[30vh]">
            <div class="flex gap-[12rem] ">
                <!-- Game selection -->
                <div>
                    <p class="text-sm text-gray-600 italic">Choose your game</p>
                    <UInputMenu v-model="gameValue" :items="games" />
                </div>
                <!-- Arrow icon -->
                <div class="flex items-center justify-center mt-4">            
                    <div v-if="!converted">
                        <UIcon name="formkit:arrowright" class="size-10" />
                    </div>        
                    <div v-else>
                        <UIcon name="line-md:chevron-double-right" class="size-10" />
                    </div>
                </div>
                <!-- Currency selection -->
                <div>
                    <p class="text-sm text-gray-600 italic">Choose your "currency"</p>
                    <UInputMenu v-model="currencyValue" :items="currencies" />
                </div>
                
            </div>
        </div>
        <div class="flex justify-center items-center mt-[10vh]">
            <UButton color="neutral" variant="outline" size="xl" class="w-[200px] flex justify-center items-center" @click="convert">Convert</UButton>
        </div>
        <div class="flex justify-center items-center mt-[10vh]">
            <p v-if="converted" class="text-sm text-gray-800 italic">{{ gameValue }} is worth (n) {{ currencyValue }}</p>
        </div>
    </main>
</template>

<style scoped>
h1 {
  font-family: 'Instrument Sans', sans-serif;
}
</style>