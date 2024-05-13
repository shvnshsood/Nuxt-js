<script setup lang="ts">
import { Mail } from "lucide-vue-next";
import { Carousel, CarouselContent, CarouselItem, CarouselNext, CarouselPrevious } from '@/components/ui/carousel'
import { Card, CardContent } from '@/components/ui/card'


function showAlert() {
  console.log("Button clicked!");
}
</script>

<template>
  <div class="text-7xl text-violet-950 text-center h-full my-auto">
    Hello
    <Button @click="showAlert" class="bg-red-900 text-xl">
      <Mail class="w-4 h-4 mr-2" /> Click me</Button
    >
  </div>
  <Carousel
    class="relative w-full mx-auto max-w-6xl"
    :opts="{
      align: 'start',
    }"
  >
    <CarouselContent>
      <CarouselItem v-for="(_, index) in 5" :key="index" class="md:basis-1/2 lg:basis-1/3">
        <div class="p-1">
          <Card>
            <CardContent class="flex aspect-square items-center justify-center p-6">
              <span class="text-3xl font-semibold">{{ index + 1 }}</span>
            </CardContent>
          </Card>
        </div>
      </CarouselItem>
    </CarouselContent>
    <CarouselPrevious />
    <CarouselNext />
  </Carousel>
</template>
