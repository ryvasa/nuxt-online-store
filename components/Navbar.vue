<template>
    <div
        :class="[
            'navbar fixed z-10 w-full transition-all duration-300',
            isAtTop ? 'lg:bg-transparent bg-base-200' : 'bg-base-200',
        ]"
    >
        <div class="flex-1">
            <nuxt-link to="/" class="btn btn-ghost text-xl"
                ><p :class="[isAtTop && 'lg:text-base-200']">
                    <span class="text-primary">On</span>Store
                </p></nuxt-link
            >
        </div>
        <div class="flex-none gap-4 lg:gap-2">
            <div class="lg:flex hidden">
                <input
                    @input="handleInput"
                    id="search"
                    type="text"
                    :class="[
                        'focus:placeholder:text-base-200 placeholder:text-transparent bg-transparent outline-none px-2 border-b-2 border-transparent focus:border-primary transition-all duration-200',
                        isAtTop && 'text-base-200 placeholder:text-base-200',
                        search.length > 0 && 'border-gray-500',
                    ]"
                    placeholder="Search"
                />
                <label
                    for="search"
                    class="btn btn-ghost btn-circle btn-sm lg:btn-md"
                >
                    <svg
                        :class="[isAtTop && 'text-base-200']"
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-5 w-5"
                        fill="none"
                        viewBox="0 0 24 24"
                        stroke="currentColor"
                    >
                        <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="2"
                            d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"
                        />
                    </svg>
                </label>
            </div>

            <label
                for="notification"
                class="btn btn-ghost btn-circle btn-sm lg:btn-md lg:flex hidden"
            >
                <div class="indicator">
                    <svg
                        :class="[isAtTop && 'lg:text-base-200']"
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-5 w-5"
                        fill="none"
                        viewBox="0 0 24 24"
                        stroke="currentColor"
                    >
                        <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="2"
                            d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"
                        />
                    </svg>
                    <span
                        class="badge badge-error badge-xs lg:badge-sm text-xs indicator-item"
                        >8</span
                    >
                </div>
            </label>
            <label for="cart" class="btn btn-ghost btn-circle btn-sm lg:btn-md">
                <div class="indicator">
                    <svg
                        :class="['h-5 w-5', isAtTop && 'lg:text-base-200']"
                        xmlns="http://www.w3.org/2000/svg"
                        fill="none"
                        viewBox="0 0 24 24"
                        stroke="currentColor"
                    >
                        <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="2"
                            d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z"
                        />
                    </svg>
                    <span
                        class="badge badge-error badge-xs lg:badge-sm text-xs indicator-item"
                        >8</span
                    >
                </div>
            </label>
            <div class="dropdown dropdown-end">
                <div
                    tabindex="0"
                    role="button"
                    class="btn btn-ghost btn-circle btn-sm lg:btn-md avatar"
                >
                    <div class="w-10 rounded-full">
                        <img
                            alt="Tailwind CSS Navbar component"
                            src="https://img.daisyui.com/images/stock/photo-1534528741775-53994a69daeb.webp"
                        />
                    </div>
                </div>
                <ul
                    tabindex="0"
                    class="menu menu-sm dropdown-content bg-base-200 rounded-box z-[1] mt-3 w-52 px-4 py-2 shadow"
                >
                    <li>
                        <nuxt-link to="/profile">Edit Profile</nuxt-link>
                    </li>
                    <li>
                        <nuxt-link to="/transaction"
                            >Order Transaction</nuxt-link
                        >
                    </li>
                    <li class="lg:hidden">
                        <nuxt-link to="/notification">Notifications</nuxt-link>
                    </li>
                    <li><nuxt-link to="/login">Logout</nuxt-link></li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
const search = ref("");
const isAtTop = ref(true);

const handleInput = (e: Event) => {
    const target = e.target as HTMLSelectElement;
    search.value = target.value;
    console.log(search.value);
};
const handleScroll = () => {
    isAtTop.value = window.scrollY === 0;
};

onMounted(() => {
    window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
    window.removeEventListener("scroll", handleScroll);
});
</script>

<style></style>
