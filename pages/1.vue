<template>
  <UiContainer>

    <template v-for="(s, i) in step" :key="i">
      <section
        class="mt-12 grid grid-cols-1 items-center gap-10 lg:mt-24 lg:h-[280px] lg:grid-cols-2 lg:gap-20"
      >
        <div :class="[i % 2 == 0 ? 'lg:order-none' : 'lg:order-1']">
          <div class="mb-2 flex h-10 w-10 items-center justify-center rounded-full bg-primary/10">
            <Icon v-bind:name="s.icon" class="h-5 w-5 text-primary" />
          </div>
          <h3 class="mb-2 text-2xl font-semibold lg:mb-4 lg:text-3xl" v-html="s.title" />
          <p class="text-muted-foreground lg:text-lg" v-html="s.description" />

        </div>
        <!-- eslint-disable-next-line vue/html-self-closing -->
        <img
          :src="s.imageUrl"
          :alt="s.title"
          class="h-[180px] w-full rounded-lg object-cover shadow-sm lg:h-[320px]"
        />
      </section>
    </template>
  </UiContainer>
</template>

<script lang="ts" setup>
  const step = [
    {
      title: "Share team inboxes",
      icon: "heroicons:chat-bubble-left-right",
      description:
        "Whether you have a team of 2 or 200, our shared team inboxes keep everyone on the same page and in the loop.",
      imageUrl:
        "https://images.unsplash.com/photo-1582213782179-e0d53f98f2ca?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
      points: [
        { text: "Leverage automation to move fast" },
        { text: "Always give customers a human to chat to" },
        { text: "Automate customer support and close leads faster" },
      ],
    },
    {
      title: "Deliver instant answers",
      icon: "heroicons:bolt",
      description:
        "An all-in-one customer service platform that helps you balance everything your customers need to be happy.",
      imageUrl:
        "https://images.unsplash.com/photo-1542744173-8e7e53415bb0?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
      points: [
        { text: "Keep your customers in the loop with live chat" },
        { text: "Embed help articles right on your website" },
        { text: "Customers never have to leave the page to find an answer" },
      ],
    },
    {
      title: "Manage your team with reports",
      icon: "heroicons:cursor-arrow-rays",
      description: `Measure what matters with  easy-to-use reports. You can filter, export, and drill down on the data in a couple clicks.`,
      imageUrl:
        "https://images.unsplash.com/photo-1628348068343-c6a848d2b6dd?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D",
      points: [
        { text: "Filter, export, and drilldown on the data quickly" },
        { text: "Save, schedule, and automate reports to your inbox" },
        { text: "Connect the tools you already use with 100+ integrations" },
      ],
    },
  ];
</script>
