<template>
    <NuxtLayout>
        <UiContainer class="py-16 text-center lg:py-24">
            <slot name="title">
                <h2 class="mb-4 mt-2 text-4xl font-bold lg:mb-6 lg:mt-3 lg:text-5xl">历史存档下载～</h2>
            </slot>
            <slot name="description">
                <div class="flex w-full justify-center ">
                    <div class="space-y-2 ">
                        <span>在此获取往期周目的完整存档文件</span>
                    </div>
                </div>
            </slot>
            <div class="lg:py-24 py-16"></div>

            <div>
                <div class="flex flex-col gap-5 md:flex-row">
                    <NuxtLink
                        :to="'https:/' + '/' + 'pan.neokoni.moe/%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%20%7C%20AliDrive/Craft233/%E5%AD%98%E6%A1%A3/week1/backup-2024-02-23(2).zip'"
                        class="shrink-0" target="_blank">
                        <!-- eslint-disable-next-line vue/html-self-closing -->
                        <img src="/assets/img/week1/2023-08-31_00.03.12.png" alt="第一周目主城"
                            class="h-[240px] w-full rounded-lg object-cover shadow md:h-[200px]" />
                    </NuxtLink>
                    <div>
                        <NuxtLink
                            :to="'https:/' + '/' + 'pan.neokoni.moe/%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%20%7C%20AliDrive/Craft233/%E5%AD%98%E6%A1%A3/week1/backup-2024-02-23(2).zip'"
                            target="_blank">
                            <p class="mb-2 text-xl font-semibold lg:text-2xl">第一周目</p>
                        </NuxtLink>
                        <p class="mb-5 line-clamp-2 text-ellipsis text-muted-foreground">
                            Craft233最原始的一个周目，此时我们正在用不知名的配置开服，一切都是未知的，每一次修改都是对开服的学习
                        </p>
                        <div class="items-center">
                            <div>
                                <p class="text-sm text-muted-foreground">2023.7.10--2024.2.23</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

        </UiContainer>
    </NuxtLayout>
</template>

<script>
// 页面标题
const runtimeConfig = useRuntimeConfig()
useHead({
  titleTemplate: (titleChunk) => {
    return titleChunk ? `${titleChunk} - 网站名称` : 'Craft233 | 获取存档';
  }
})
</script>