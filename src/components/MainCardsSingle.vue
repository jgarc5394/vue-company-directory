<script setup>
    import { faker } from '@faker-js/faker'
    const firstName = faker.person.firstName()
    const lastName = faker.person.lastName()
    const fullName = `${firstName} ${lastName}`

    const selectCard = () => {
        console.log(`${fullName} selected`)
    }
</script>

<template>
    <div class="card" @clicked="selectCard">
        <div class="card-image">
            <img :src="faker.internet.avatar()" alt="" srcset="" />
        </div>
        <div class="card-details">
            <p class="card-details-name">{{ fullName }}</p>
            <p class="card-details-job">{{ faker.name.jobTitle() }}, {{ faker.name.jobArea() }}</p>
            <p class="card-details-email">{{ faker.internet.exampleEmail(firstName, lastName) }}</p>
            <p class="card-details-quote">"{{ faker.lorem.paragraph() }}"</p>
        </div>      
    </div>
</template>

<style scoped lang="postcss">
    .card {
        @apply cursor-pointer overflow-hidden rounded-md bg-orange-300 p-8 shadow-md
        transition duration-300 hover:scale-110 hover:shadow-2xl hover:shadow-red-900;
        &-image {
            img {
                @apply mx-auto rounded-full object-contain;
            }
        }
        &-details {
            @apply flex flex-col gap-2 pt-6 text-center;
            &-name {
                @apply text-3xl font-thin tracking-wide text-orange-800;
            }
            &-job {
                @apply -mt-2 text-xs font-bold text-orange-600;
            }
            &-email {
                @apply text-sm text-orange-500;
            }
            &-quote {
                @apply pt-4 text-lg italic text-orange-800;
            }
        }
    }
</style>