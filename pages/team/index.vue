<script setup lang="ts">
useHead({
  title: "Team",
});

type TeamInfo = "MB" | "RJ" | "JC" | "";

const activeTab = ref<TeamInfo>("");

const tabInfo = computed(() => {
  switch (activeTab.value) {
    case "MB":
      return {
        name: "Michael Bany",
        desc: "Something about Michael",
      };
    case "RJ":
      return {
        name: "Radim Jerabek",
        desc: "Something about Radim",
      };
    case "JC":
      return {
        name: "Jakub Cernoch",
        desc: "Something about Jakub",
      };
  }
});

const team = [
  {
    name: "Michael Baný",
    short: "MB" as TeamInfo,
    role: "Marketing & Komunikace",
    image: "/img/Profile1.png",
    teams: ["1000S"],
    link: "https://www.instagram.com/michael_bany",
  },
  {
    name: "Radim Jeřábek",
    short: "RJ" as TeamInfo,
    role: "Technik specialista",
    image: "/img/Profile2.png",
    teams: ["1000S", "HBP"],
    link: "https://www.instagram.com/jerabek_radim/",
  },
  {
    name: "Jakub Černoch",
    short: "JC" as TeamInfo,
    role: "Producent manager",
    image: "/img/Profile3.png",
    teams: ["1000S", "HBP"],
    link: "https://www.instagram.com/jakub__cernoch/",
  },
];
</script>
<template>
  <div class="flex flex-col items-center">
    <h1 class="text-4xl font-bold mt-10 mb-5">Náš tým</h1>

    <div
      class="mb-8 flex md:flex-row flex-col items-center justify-center gap-5"
    >
      <div
        class="flex w-64 flex-col items-center bg-slate-800 p-6 rounded-xl shadow-xl hover:shadow-2xl transition-shadow cursor-pointer"
        v-for="(member, i) in team"
        :key="i"
        @click="
          activeTab === member.short
            ? (activeTab = '')
            : (activeTab = member.short)
        "
      >
        <div class="w-full flex items-center gap-2">
          <div
            class="bg-red-600 w-max rounded-lg flex items-center gap-1 px-2 py-1 text-[10px]"
            v-if="member.teams.includes('1000S')"
          >
            <Icon name="bx:bxs-shield-alt-2" class="w-3 h-3" />
            1000S
          </div>

          <div
            class="bg-yellow-500 w-max rounded-lg flex items-center gap-1 px-2 py-1 text-[10px]"
            v-if="member.teams.includes('HBP')"
          >
            <Icon name="bx:bxs-shield-alt-2" class="w-3 h-3" />
            HBP • 1000S
          </div>
        </div>

        <img
          :src="member.image"
          class="w-24 h-24 object-cover rounded-full my-5"
        />

        <div class="w-full">
          <h2 class="text-lg font-bold my-3 mb-2">{{ member.name }}</h2>
          <p class="text-sm text-red-600">{{ member.role }}</p>
        </div>

        <a
          class="w-full mt-3 hover:text-white/80 transition-colors"
          :href="member.link"
          target="_blank"
        >
          <Icon name="lucide:link" class="w-4 h-4" />
        </a>
      </div>
    </div>

    <Transition
      enter-active-class="transition ease-out duration-100 transform"
      enter-from-class="opacity-0 scale-95"
      enter-to-class="opacity-100 scale-100"
      leave-active-class="transition
        ease-in duration-75 transform"
      leave-from-class="opacity-100 scale-100"
      leave-to-class="opacity-0 scale-95"
    >
      <div class="w-full mb-5" v-if="activeTab">
        <h3 class="font-bold text-lg">{{ tabInfo?.name }}</h3>
        <p class="text-slate-400 my-3">
          {{ tabInfo?.desc }}
        </p>
      </div>
    </Transition>

    <UiButton>Požádat o spolupráci</UiButton>

    <h2 class="text-4xl font-bold mt-10 mb-5 flex items-center gap-3">
      <div
        class="bg-red-600 w-max h-6 rounded-lg flex items-center gap-1 px-2 py-1 text-[10px]"
      >
        <Icon name="bx:bxs-shield-alt-2" class="w-3 h-3" />
        1000S
      </div>
      Studio Thousand
    </h2>
    <div>
      <p class="mt-3">
        Jsme moc rádi, že můžeme představit náš druhý krátkometrážní film. Naším
        cílem bylo se dostat k formátu, který odpovídá filmové kvalitě. Film o
        záhadné kostce byl pro nás velký oříšek, který jsem se snažili pojmout
        zodpovědně. Budeme moc vděční za každou vaši zpětnou vazbu, která nám
        pomůže příště zvládnout řešení lépe. Uvědomujeme si, že projekt má silné
        ale i slabé stránky. Stejně vám ho chceme úkázat, abychom mohli mít
        příště slabin méně.
      </p>

      <p class="mt-3">
        Celý film můžete již teď zhlédnout na našem
        <a
          class="text-red-600 font-medium hover:underline"
          href="https://www.youtube.com/@hbp1000s"
          target="_blank"
          >youtube kanále</a
        >
      </p>
    </div>

    <h2 class="text-4xl font-bold mt-10 mb-5 flex items-center gap-3">
      <div
        class="bg-yellow-500 w-max h-6 rounded-lg flex items-center gap-1 px-2 py-1 text-[10px]"
      >
        <Icon name="bx:bxs-shield-alt-2" class="w-3 h-3" />
        HBP • 1000S
      </div>
      High Budget Production
    </h2>
    <div>
      <p class="mt-3">
        Jsme moc rádi, že můžeme představit náš druhý krátkometrážní film. Naším
        cílem bylo se dostat k formátu, který odpovídá filmové kvalitě. Film o
        záhadné kostce byl pro nás velký oříšek, který jsem se snažili pojmout
        zodpovědně. Budeme moc vděční za každou vaši zpětnou vazbu, která nám
        pomůže příště zvládnout řešení lépe. Uvědomujeme si, že projekt má silné
        ale i slabé stránky. Stejně vám ho chceme úkázat, abychom mohli mít
        příště slabin méně.
      </p>

      <p class="mt-3">
        Celý film můžete již teď zhlédnout na našem
        <a
          class="text-red-600 font-medium hover:underline"
          href="https://www.youtube.com/@hbp1000s"
          target="_blank"
          >youtube kanále</a
        >
      </p>
    </div>
  </div>
</template>
