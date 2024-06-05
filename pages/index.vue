<template>
  <div>
    <NuxtLayout>
      <UiContainer class="relative flex flex-col items-center justify-center gap-y-12 py-10 lg:h-[720px] lg:flex-row">
        <img src="https://resource.neokoni.moe/craft233/img/craft233_logo.svg" alt="Server image"
          :title="`Craft233 Server image`" class="h-[200px] object-cover md:w-[600px] lg:h-full" />
        <div class="flex h-full items-center justify-center">
          <div>
            <h3 class="text-3xl font-semibold lg:text-5xl ">
              Craft233
            </h3>
            <h2 class="mt-8 flex flex-col text-2xl text-muted-foreground">由热爱驱动，致力于长久与安全的Minecraft服务器</h2>
            <div class="grid mt-8 md:flex w-full shrink-0 flex-col-reverse gap-3 md:mt-12 lg:w-auto lg:flex-row">
              <UiButton size="lg" class="w-full shrink-0 whitespace-nowrap md:w-auto" to="join">加入</UiButton>
              <a href="https://docs.craft233.top" target="_blank">
                <UiButton size="lg" class="w-full lg:w-auto" variant="outline">文档
                  <Icon name="lucide:external-link" class="h-4 w-4" />
                </UiButton>
              </a>
            </div>
          </div>
        </div>
        <!-- eslint-disable-next-line vue/html-self-closing -->

      </UiContainer>
      <UiContainer>
        <template v-for="(f, i) in features" :key="i">
          <section class="mt-12 grid grid-cols-1 items-center gap-10 lg:mt-20 lg:h-[450px] lg:grid-cols-2 lg:gap-20">
            <div :class="[i % 2 == 0 ? 'lg:order-none' : 'lg:order-1']">
              <h3 class="mb-2 text-2xl font-semibold lg:mb-4 lg:text-3xl" v-html="f.title" />
              <p class="text-muted-foreground lg:text-lg" v-html="f.description" />
            </div>
            <!-- eslint-disable-next-line vue/html-self-closing -->
            <img :src="f.imageUrl" :alt="f.title"
              class="h-[250px] w-full rounded-lg object-cover shadow-sm lg:h-[330px]" />
          </section>
        </template>
      </UiContainer>
      <UiContainer class="py-16 lg:py-24">
        <h2 class="mb-4 mt-3 text-center text-3xl font-semibold lg:mb-5 lg:text-4xl">
          我们的特色
        </h2>
        <!-- <p class="mx-auto max-w-[760px] text-center text-lg text-muted-foreground lg:text-xl">
      Powerful, self-serve product and growth analytics to help you convert, engage, and retain more
      users. Trusted by over 4,000 startups.
    </p> -->

        <div class="grid grid-cols-1 gap-y-10 py-10 md:grid-cols-2 lg:grid-cols-3 lg:gap-8 lg:gap-y-16 lg:py-16">
          <template v-for="(f1, i1) in features1" :key="i1">
            <div class="group flex flex-col items-center justify-center">
              <div class="flex h-12 w-12 items-center justify-center rounded-md border">
                <Icon :name="f1.icon" class="h-5 w-5 transition-colors group-hover:text-primary lg:h-6 lg:w-6" />
              </div>
              <h3 class="mt-4 text-balance text-center text-lg font-semibold lg:mt-5 lg:text-xl" v-html="f1.title" />
              <p class="mt-1 max-w-[400px] text-balance text-center text-muted-foreground lg:mt-2"
                v-html="f1.description" />
            </div>
          </template>
        </div>
      </UiContainer>
    </NuxtLayout>
  </div>
</template>

<script lang="ts" setup>
import axios from 'axios';

const response = await axios.get('https://list.mczfw.cn/api/mc.craft233.top');
const playersNum = response.data.p;
const players: number = playersNum as number;
if (players > 2) {
  var playerInfo = players + "名";
} else {
  var playerInfo = "";
}

onMounted(() => {
  document.getElementById('playerdata').textContent = playerInfo
})

const features = [
  {
    title: "友好的氛围",
    icon: "heroicons:chat-bubble-left-right",
    description:
      `友善的玩家与管理团队解决您遇到的问题，立即加入，与其他<span id="playerdata"></span>玩家一同创建家园`,
    imageUrl:
      "https://images.unsplash.com/photo-1582213782179-e0d53f98f2ca?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
  },
  {
    title: "综合的发展方向",
    description:
      `• Oases:由Leaves核心驱动的休闲服，提供更丰富的游玩内容，开放生电特性与相关协议支持<br>• Cube: 由Fabric核心驱动的生电服务器，提供完整的生电内容与优化的原版内容`,
    imageUrl:
      "https://images.unsplash.com/photo-1542744173-8e7e53415bb0?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
  }
];
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

// 页面标题
const runtimeConfig = useRuntimeConfig()
useHead({
  titleTemplate: (titleChunk) => {
    return titleChunk ? `${titleChunk} - 网站名称` : 'Craft233 | 主页';
  }
})

</script>