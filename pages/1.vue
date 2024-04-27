<template>
  <UiContainer class="py-16 lg:py-24">
    <h2 class="mb-4 mt-3 text-center text-3xl font-semibold lg:mb-5 lg:text-4xl">
      我们的特色
    </h2>
    <!-- <p class="mx-auto max-w-[760px] text-center text-lg text-muted-foreground lg:text-xl">
      Powerful, self-serve product and growth analytics to help you convert, engage, and retain more
      users. Trusted by over 4,000 startups.
    </p> -->

    <div
      class="grid grid-cols-1 gap-y-10 py-10 md:grid-cols-2 lg:grid-cols-3 lg:gap-8 lg:gap-y-16 lg:py-16"
    >
      <template v-for="(f1, i1) in features1" :key="i1">
        <div class="group flex flex-col items-center justify-center">
          <div class="flex h-12 w-12 items-center justify-center rounded-md border">
            <Icon
              :name="f1.icon"
              class="h-5 w-5 transition-colors group-hover:text-primary lg:h-6 lg:w-6"
            />
          </div>
          <h3
            class="mt-4 text-balance text-center text-lg font-semibold lg:mt-5 lg:text-xl"
            v-html="f1.title"
          />
          <p
            class="mt-1 max-w-[400px] text-balance text-center text-muted-foreground lg:mt-2"
            v-html="f1.description"
          />
        </div>
      </template>
    </div>
  </UiContainer>
</template>

<script lang="ts" setup>
  const features1 = [
    {
      icon: "lucide:cable",
      title: "多版本兼任",
      description:
        "支持Java版1.13及之后的版本以及基岩版的最新正式版",
    },
    {
      icon: "lucide:shield-check",
      title: "数据安全",
      description:
        "每日凌晨自动备份数据，保证数据安全",
    },
    {
      icon: "lucide:circle-arrow-up",
      title: "版本新",
      description: `当插件或模组支持，我们会追随最新的Minecraft版本`,
    },
  ];
</script>
