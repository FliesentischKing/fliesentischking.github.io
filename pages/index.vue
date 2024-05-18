<script setup lang="ts">
import { BellRing, Check } from 'lucide-vue-next'

import { Button } from '@/components/ui/button'
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from '@/components/ui/card'
import { Switch } from '@/components/ui/switch'
import { cn } from '@/lib/utils'
import { Progress } from '@/components/ui/progress'
import { ref } from 'vue'

const currentlyPlaying = [
  {
    title: 'Super Mario 64',
    description: 'PC Port sm64ex',
    percentage: 30,
    image: 'Super_Mario_64_box_cover.jpg',
  },
  {
    title: 'Half Life',
    description: 'Steam Version mit Anniversary Update',
    percentage: 80,
    image: '256px-Half-Life_Cover_Art.webp',
  },
  {
    title: 'Super Mario 3D World',
    description: 'Nintendo Switch Version',
    percentage: 80,
    image: '82771_Super_Mario_3D_World__Bowsers_Fury.webp',
  },
  {
    title: 'Grand Theft Auto IV: The Lost and Damned',
    description: 'PC Version',
    percentage: 50,
    image: '256px-Grand_Theft_Auto_IV_coverart.jpg',
  },
  {
    title: 'The Legend of Zelda: Tears of the Kingdom',
    description: 'Yuzu Emulator',
    percentage: 25,
    image: '72589_The_Legend_of_Zelda_Tears_of_the_Kingdom.webp',
  }
]

const finishedGames = [
  {
    title: 'The Legend of Zelda: Ocarina of Time',
    description: 'PC Port Ship of Harkinian',
    image: '642652-zelda_master_quest_us_front_large.jpg',
  },
  {
    title: "Tony Hawk's Underground",
    description: 'PC Version',
    image: 'Tony_Hawks_Underground_PlayStation2_box_art_cover.jpg',
  },
  {
    title: 'The Simpsons Hit & Run',
    description: 'Gamecube Version',
    image: '10178_The_Simpsons_Hit_&_Run.webp',
  }
]

const backlog = [
  {
    title: 'Ape Escape',
    description: '',
    image: '7dc5ece165388748790d8170245197ed.png',
  },
  {
    title: 'Another World',
    description: '',
    image: 'f0841cf5f09060e3649a07ef3e4cb7d0.png',
  },
  {
    title: 'Half Life 2',
    description: '',
    image: '256px-421px-HL2box.webp',
  },
  {
    title: "FAR: Lone Sails",
    description: '',
    image: '56531_FAR_Lone_Sails.webp',
  },
  {
    title: 'FAR: Changing Tides',
    description: '',
    image: '94066_FAR_Changing_Tides.webp',
  },
  {
    title: 'Arise: A Simple Story',
    description: '',
    image: '70900_Arise_A_Simple_Story.webp',
  },
  {
    title: 'Banjo-Kazooie',
    description: '',
    image: '250px-BanjoKazooieCover500px.webp',
  },
  {
    title: 'Banjo-Tooie',
    description: '',
    image: '250px-Banjo-Tooie_Coverart.webp',
  },
  {
    title: 'Chrono Trigger',
    description: '',
    image: 'Chrono_Trigger.webp',
  },
  {
    title: "Conker's Bad Fur Day",
    description: '',
    image: 'e7ba692151c4e6c1c41c4770cdd15e8b.jpg',
  },
  {
    title: 'Deus Ex',
    description: '',
    image: 'ca20e1d8e1d19a92fbfc28f0b467dd5b.png',
  },
  {
    title: 'EarthBound',
    description: '',
    image: '6fd01250b30177eeee04afa605bc91e7.jpg',
  },
  {
    title: 'Firewatch',
    description: '',
    image: 'aa9264d85b7225106a396c7816efc645.jpg',
  },
  {
    title: 'Vollgas',
    description: '',
    image: '81d27c868d2dea21d9531afbbb45a2bd.jpg',
  },
  {
    title: 'Grim Fandango',
    description: '',
    image: '11b99b502b6eeca494fabcc6ee7ca553.jpg',
  },
  {
    title: 'Limbo',
    description: '',
    image: 'a0a9b321a2b35675be63a0603e77f0f2.jpg',
  },
  {
    title: 'Mafia',
    description: '',
    image: '349b4d0760cb85b962fa79800c168927.jpg',
  },
  {
    title: 'Mother 3',
    description: '',
    image: 'f7a491ac3d05204b541f8f8e17d24f9f.jpg',
  },
  {
    title: 'Super Mario Sunshine',
    description: '',
    image: 'f5e97c0193978d636807084bf658fc1c.jpg',
  },
  {
    title: 'The Legend of Zelda: Majoras Mask',
    description: '',
    image: '00431979216eadc4b0d908cf45bf28b7.jpg',
  },
  {
    title: 'The Legend of Zelda: Wind Waker',
    description: '',
    image: '304678bd2a45713cc7bfcb1a9e19c8e4.png',
  },
  {
    title: 'The Legend of Zelda: A Link to the Past',
    description: '',
    image: '9f0184e7dffd2c23559da5f7d9088d1d.png',
  },
  {
    title: 'The Witness',
    description: '',
    image: 'a27ce27d7af9c2e2312c46075c3e4ff0.png',
  },
  {
    title: 'Thief',
    description: '',
    image: '26c36be48049ac47c5a9af9e8501ab5c.png',
  },
  {
    title: 'Thief II: The Metal Age',
    description: '',
    image: '4ad38ecf2884a47a5efa657f3358e635.png',
  },
]
</script>

<template>
  <main class="flex flex-1 flex-col gap-4 p-4 md:gap-8 md:p-8">
    <p class="font-semibold">Aktuell gespielte Spiele</p>
    <div class="grid gap-4 md:grid-cols-2 md:gap-8 lg:grid-cols-4 xl:grid-cols-4 2xl:grid-cols-6">
      <Card v-for="(game, index) in currentlyPlaying" :key="index">
        <CardHeader>
          <CardTitle>{{ game.title }}</CardTitle>
          <CardDescription>{{ game.description }}</CardDescription>
        </CardHeader>
        <CardContent class="grid gap-4">
          <div>
            <img :src="game.image" class="h-64 mb-4 rounded-xl object-cover" />
            Fortschritt: {{ game.percentage }}%
            <Progress class="mt-4" v-model="game.percentage" />
          </div>
        </CardContent>
      </Card>
    </div>

    <p class="font-semibold">Im Stream durchgespielte Spiele</p>
    <div class="grid gap-4 md:grid-cols-2 md:gap-8 lg:grid-cols-4 xl:grid-cols-4 2xl:grid-cols-6">
      <Card v-for="(game, index) in finishedGames" :key="index">
        <CardHeader>
          <CardTitle>{{ game.title }}</CardTitle>
          <CardDescription>{{ game.description }}</CardDescription>
        </CardHeader>
        <CardContent class="grid gap-4">
          <div>
            <img :src="game.image" class="h-64 mb-4 rounded-xl object-cover" />
          </div>
        </CardContent>
      </Card>
    </div>

    <p class="font-semibold">Spiele, die ich bald streamen will</p>
    <div class="grid gap-4 md:grid-cols-2 md:gap-8 lg:grid-cols-4 xl:grid-cols-4 2xl:grid-cols-6">
      <Card v-for="(game, index) in backlog" :key="index">
        <CardHeader>
          <CardTitle>{{ game.title }}</CardTitle>
          <CardDescription>{{ game.description }}</CardDescription>
        </CardHeader>
        <CardContent class="grid gap-4">
          <div>
            <img :src="game.image" class="h-64 mb-4 rounded-xl object-cover" />
          </div>
        </CardContent>
      </Card>
    </div>
  </main>
</template>