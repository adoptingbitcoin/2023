<template>
    <div class="component">

        <AngledBanner topImage="/images/section-heading--back-in-sv.svg"
                      bottomImage="/images/section-heading--back-in-sv.svg"/>

        <div class="container mx-auto px-4">
            <div class="grid md:grid-cols-2 mb-12">
                <div class=""></div>
                <div class="">
                    <client-only>
                        <p>
                            <FadeInText
                                    text="El Salvador is the first country to adopt Bitcoin, making it the ground-zero for global Bitcoin adoption."/>
                        </p>
                        <br>
                        <p>
                            <FadeInText
                                    text="This novel situation presents both the challenge of onboarding users and the opportunity to learn from them, benefiting the entire ecosystem, from protocol and application developers to entrepreneurs, investors, and the many communities around the world that followed Bitcoin Beach's example by establishing circular Bitcoin economies."/>
                        </p>
                    </client-only>
                </div>
            </div>

        </div>

        <div class="hidden md:block">
            <BlogSlider slides-per-view="2.5"/>
        </div>
        <div class="md:hidden">
            <BlogSlider slides-per-view="1.5"/>
        </div>
    </div>
</template>
<script setup lang="ts">
import BlogSlider from "~/components/BlogSlider.vue";

const {data} = await useAsyncData('blog' + process.env.CACHE_KEY, () => queryContent('/blog').find())
</script>