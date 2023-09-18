<script setup>
    import { ref } from 'vue'
    const brand = ref ('🖥️ Fictional Company Directory')
</script>

<template>
    <nav>
        <div class="wrapper">
            <div class="brand">
                <span class="brand-title">{{ brand }}</span>
            </div>
            <div class="menu">
                <a href="#" class="menu-item">Departments</a>
                <a href="#" class="menu-item">Settings</a>
                <a href="#" class="menu-login">Logout</a>
            </div>
        </div>
    </nav>
</template>

<style scoped lang="postcss">
    nav {
        @apply flex h-20 bg-red-700 text-white;
        .wrapper{
            @apply container mx-auto flex w-full items-center justify-between;
        }
            .brand {
                &-title {
                    @apply text-2xl font-extrabold text-orange-300;
                }
            }
            .menu {
                @apply flex gap-2;
                &-item {
                    @apply rounded-md font-bold px-4 py-2 hover:bg-orange-300 hover:text-slate-900;
                }
                &-login {
                    @apply rounded-md font-bold bg-orange-300 px-4 py-2 hover:bg-red-500 hover:text-slate-900 hover:font-bold;
                }
            }
    }       
</style>
