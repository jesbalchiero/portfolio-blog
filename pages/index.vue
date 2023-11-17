<template>
    <section>
        <h1 class="text-5xl font-bold mt-20">👋🏻 Hello, I'm Jean Sbalchiero!</h1>
        <p class="text-base text-gray-900 p-2 italic">Full Stack Web Developer in Conecta Softwares</p>
    </section>
    <section class="flex flex-col md:flex-row">
        <div class="md:w-3/4">
            <h2 class="text-3xl font-bold mt-8">My Story</h2>
            <p class="text-lg py-2">
                I'm a Full Stack Web Developer at Conecta Softwares, and a mobile developer enthusiast. My soft skills are focused on .NET and Vue.js, with big experience to manage and develop funcs to ERP systems.
            </p>
        </div>
        <!-- <img src="~/assets/images/jean-avatar.png" alt="Profile Avatar" class="w-1/2 md:max-w-sm p-8 mx-auto"> -->
    </section>
    <section>
        <h2 class="text-3xl font-bold mt-8">Latest Blog Posts</h2>
        <div class="grid md:grid-cols-3 pt-8 gap-10">
            <Post :posts="posts" />
        </div>
    </section>
</template>

<script setup>
    const { data: posts } = await useAsyncData('latest-posts', () =>
        queryContent('/blog').sort({ data: 1 }).limit(3).find()
    )
</script>

<style scoped>

</style>