<script setup lang="ts">

import { Icon } from '@iconify/vue'

var currentlyPlaying = [
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
    image: '39eaa84fa49b129edaa137171ba60746.jpg',
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

var finishedGames = [
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

var backlog = [
  {
    title: 'Shakedown Hawaii',
    description: '',
    image: 'd7d2fb293f4cd636bb59ae6386813dd3.png',
  },
  {
    title: 'Retro City Rampage',
    description: '',
    image: 'db7f2bf023263eb0a0a8247c5007f49a.png',
  },
  {
    title: 'Golf Story',
    description: '',
    image: 'b2f39eaa50e146f33c6ea8cd06889a84.png',
  },
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
    image: '381cea722f1c755b54fa72826e4142e8.png',
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
  {
    title: 'Blood',
    description: '',
    image: '0d5db791e260aff09b1844fbbf0b97d5.png'
  },
  {
    title: 'Bowsers Fury',
    description: '',
    image: '053b2108e3f9c0adf2a8edf682075323.png'
  },
  {
    title: 'Glitchpunk',
    description: '',
    image: 'b03d8174d4677eb0299c12699854ca7e.jpg'
  },
  {
    title: 'American Fugitive',
    description: '',
    image: '9fe2132cbfda2218e4928f320f53ce8e.png'
  },
  {
    title: 'Rustler',
    description: '',
    image: '35d2535722ed9509e0567e222e3a7d2e.png'
  },
  {
    title: 'Dragonball Z: Das Erbe von Goku',
    description: '',
    image: '1bd164ad48783b615ca23c04b1f8c20a.png'
  },
  {
    title: 'Dragonball Z: Das Erbe von Goku 2',
    description: '',
    image: 'fae504c7f3bdce5b17da7664b3efeded.png'
  },
  {
    title: 'Dragonball Z: Buu\'s Fury',
    description: '',
    image: '1dc43796fb1b397a7f2b43180068b580.png'
  },
  {
    title: 'Super Mario World 2: Yoshi\s Island',
    description: '',
    image: '59857cc70355243795b398b32447b862.png'
  },
  {
    title: 'Banjo-Kazooie: Schraube Locker',
    description: '',
    image: '17faa600670ae46a32ff83f76e83806a.png'
  },
]

//Sorting the Arrays by object.title so I don't have to format it manually
currentlyPlaying = useOrderBy(currentlyPlaying, ['title'], ['asc'])
finishedGames = useOrderBy(finishedGames, ['title'], ['asc'])
backlog = useOrderBy(backlog, ['title'], ['asc'])

</script>

<template>
  <main class="flex flex-1 flex-col gap-4 p-4 md:gap-8 md:p-8">
    <Alert>
      <Icon icon="radix-icons:update" />
      <AlertTitle>Es gab ein Update!</AlertTitle>
      <AlertDescription>
        Aktualisiert am 15.09.2024
      </AlertDescription>
    </Alert>

    <Tabs default-value="current">
      <TabsList>
        <TabsTrigger value="current">
          Aktuell gespielte Spiele
        </TabsTrigger>
        <TabsTrigger value="finished">
          Im Stream durchgespielte Spiele
        </TabsTrigger>
        <TabsTrigger value="backlog">
          Spiele, die ich bald streamen will
        </TabsTrigger>
      </TabsList>
      <TabsContent value="current">
        <div class="grid gap-2 md:grid-cols-2 md:gap-8 lg:grid-cols-5 xl:grid-cols-6 2xl:grid-cols-8">
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
      </TabsContent>
      <TabsContent value="finished">
        <div class="grid gap-2 md:grid-cols-2 md:gap-8 lg:grid-cols-5 xl:grid-cols-6 2xl:grid-cols-8">
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
      </TabsContent>
      <TabsContent value="backlog">
        <div class="grid gap-2 md:grid-cols-2 md:gap-8 lg:grid-cols-5 xl:grid-cols-6 2xl:grid-cols-8">
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
      </TabsContent>
    </Tabs>
  </main>
</template>