<script setup lang="ts">
useHead({
  title: "Home",
});

const projects = [
  {
    title: "Project: Cube 2",
    description:
      "Tajemství, která vám odhalil první díl jsme se rozhodli odkrýt v pokračování. Zjisti co nejvíce o kouzelném světě cestování časem.",
    image: "/img/project5.png",
    tag: "V Produkci",
  },
  {
    title: "Project: Dopad",
    description:
      "Příběh o lásce, která překonává všechny překážky. Připravte se na dojemný příběh, který vás nenechá chladnými.",
    image: "/img/project2.png",
    tag: "Nadcházející",
  },
  {
    title: "Project: Cube",
    description:
      "Základní kámen celého světa. Příběh o hrdinovi, který se musí vydat na cestu, aby zachránil svět před zkázou.",
    image: "/img/project4.jpeg",
  },
  {
    title: "Focení Ostrava",
    description:
      "Série fotografií zachycující krásu města Ostrava. Podívejte se na nádherné fotografie, které vás dostanou do varu.",
    image: "/img/project1.png",
  },
];
</script>
<template>
  <div class="flex flex-col items-center">
    <div class="grid sm:grid-cols-2 gap-6 grid-cols-1 lg:grid-cols-4 mb-5">
      <!-- card 1 -->
      <div
        v-for="(project, i) in projects"
        :key="i"
        class="relative shadow-lg bg-slate-800 rounded-lg"
      >
        <div
          v-if="project.tag"
          class="bg-purple-500 px-3 py-0.5 text-sm flex items-center gap-1 rounded-2xl absolute top-2 right-2"
        >
          <Icon name="bx:bxs-star" class="w-4 h-4" />
          {{ project.tag }}
        </div>
        <img
          :src="project.image"
          alt="project1"
          class="rounded-lg rounded-b-none w-full h-[200px] object-cover object-position"
        />

        <div class="p-5 mt-1">
          <h3 class="text-lg font-medium mb-1">{{ project.title }}</h3>
          <p class="text-slate-400 text-sm">{{ project.description }}</p>
        </div>
      </div>
    </div>

    <UiButton variant="secondary">Zobrazit Další</UiButton>

    <h2 class="text-4xl font-bold mt-10 mb-5">Čerstvé novinky</h2>
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
        <a class="text-red-600 font-medium hover:underline" href="https://www.youtube.com/@hbp1000s" target="_blank"
          >youtube kanále</a
        >
      </p>
    </div>
  </div>
</template>
