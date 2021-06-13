<template>
    <div class="relative bg-gray-50">
        <Popover class="relative bg-white shadow">
            <div class="max-w-7xl mx-auto px-4 sm:px-6">
                <div class="flex justify-between items-center py-6 md:justify-start md:space-x-10">
                </div>
            </div>

            <transition enter-active-class="duration-200 ease-out" enter-from-class="opacity-0 scale-95" enter-to-class="opacity-100 scale-100" leave-active-class="duration-100 ease-in" leave-from-class="opacity-100 scale-100" leave-to-class="opacity-0 scale-95">
                <PopoverPanel focus class="absolute top-0 inset-x-0 z-10 p-2 transition transform origin-top-right md:hidden">
                    <div class="rounded-lg shadow-lg ring-1 ring-black ring-opacity-5 bg-white divide-y-2 divide-gray-50">
                        <div class="pt-5 pb-6 px-5">
                            <div class="flex items-center justify-between">
                                <div>
                                    <img class="h-8 w-auto" src="https://tailwindui.com/img/logos/workflow-mark-indigo-600.svg" alt="Workflow" />
                                </div>
                                <div class="-mr-2">
                                    <PopoverButton class="bg-white rounded-md p-2 inline-flex items-center justify-center text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500">
                                        <span class="sr-only">Close menu</span>
                                        <XIcon class="h-6 w-6" aria-hidden="true" />
                                    </PopoverButton>
                                </div>
                            </div>
                            <div class="mt-6">
                                <nav class="grid gap-y-8">
                                    <a v-for="item in features" :key="item.name" :href="item.href" class="-m-3 p-3 flex items-center rounded-md hover:bg-gray-50">
                                        <component :is="item.icon" class="flex-shrink-0 h-6 w-6 text-indigo-600" aria-hidden="true" />
                                        <span class="ml-3 text-base font-medium text-gray-900">
                      {{ item.name }}
                    </span>
                                    </a>
                                </nav>
                            </div>
                        </div>
                        <div class="py-6 px-5 space-y-6">
                            <div class="grid grid-cols-2 gap-y-4 gap-x-8">
                                <a href="#" class="text-base font-medium text-gray-900 hover:text-gray-700">
                                    Pricing
                                </a>

                                <a href="#" class="text-base font-medium text-gray-900 hover:text-gray-700">
                                    Docs
                                </a>
                                <a v-for="item in resources" :key="item.name" :href="item.href" class="text-base font-medium text-gray-900 hover:text-gray-700">
                                    {{ item.name }}
                                </a>
                            </div>
                            <div>
                                <a href="#" class="w-full flex items-center justify-center px-4 py-2 border border-transparent rounded-md shadow-sm text-base font-medium text-white bg-indigo-600 hover:bg-indigo-700">
                                    Sign up
                                </a>
                                <p class="mt-6 text-center text-base font-medium text-gray-500">
                                    Existing customer?
                                    <a href="#" class="text-indigo-600 hover:text-indigo-500">
                                        Sign in
                                    </a>
                                </p>
                            </div>
                        </div>
                    </div>
                </PopoverPanel>
            </transition>
        </Popover>
        <main class="lg:relative">
            <div class="mx-auto max-w-7xl w-full pt-16 pb-20 text-center lg:py-48 lg:text-left">
                <div class="px-4 lg:w-1/2 sm:px-8 xl:pr-16">
                    <h1 class="text-4xl tracking-tight font-extrabold text-gray-900 sm:text-5xl md:text-6xl lg:text-5xl xl:text-6xl">
                        <span class="block xl:inline">Welcome to my life as I know it</span>
                        {{ ' ' }}
                        <span class="block text-indigo-600 xl:inline"></span>
                    </h1>
                    <p class="mt-3 max-w-md mx-auto text-lg text-gray-500 sm:text-xl md:mt-5 md:max-w-3xl">
                        Here you can explore our website and watch custom fan made videos. Made by Kieran Nava and
                        Jakson Thiel. lets get to know me. I was born june 25 2010, are friendship started in 3rd Grade we started making comics that kept building are friendship.
                        We both love marvel and DC so we decided to make it are thing. Are first series is god vs steel, so ENJOY!!! episode 1
                    </p>
<!--                    <div class="mt-10 sm:flex sm:justify-center lg:justify-start">-->
<!--                        <div class="rounded-md shadow">-->
<!--                            <a href="#" class="w-full flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 md:py-4 md:text-lg md:px-10">-->
<!--                                Get started-->
<!--                            </a>-->
<!--                        </div>-->
<!--                        <div class="mt-3 rounded-md shadow sm:mt-0 sm:ml-3">-->
<!--                            <a href="#" class="w-full flex items-center justify-center px-8 py-3 border border-transparent text-base font-medium rounded-md text-indigo-600 bg-white hover:bg-gray-50 md:py-4 md:text-lg md:px-10">-->
<!--                                Live demo-->
<!--                            </a>-->
<!--                        </div>-->
<!--                    </div>-->
                </div>
            </div>
            <div class="relative w-full h-64 sm:h-72 md:h-96 lg:absolute lg:inset-y-0 lg:right-0 lg:w-1/2 lg:h-full">
                <video class="absolute inset-0 w-full h-full object-cover" width="320" height="240" controls>
                    <source src="/img/Project_06-061_HD_720p_mp4.mov">
                    Your browser does not support the video tag.
                </video>
            </div>
        </main>
    </div>
</template>

<script>
import { Popover, PopoverButton, PopoverGroup, PopoverPanel } from '@headlessui/vue'
import {
    BookmarkAltIcon,
    CalendarIcon,
    ChartBarIcon,
    CursorClickIcon,
    MenuIcon,
    PhoneIcon,
    PlayIcon,
    RefreshIcon,
    ShieldCheckIcon,
    SupportIcon,
    ViewGridIcon,
    XIcon,
} from '@heroicons/vue/outline'
import { ChevronDownIcon } from '@heroicons/vue/solid'

const features = [
    {
        name: 'Analytics',
        href: '#',
        description: 'Get a better understanding of where your traffic is coming from.',
        icon: ChartBarIcon,
    },
    {
        name: 'Engagement',
        href: '#',
        description: 'Speak directly to your customers in a more meaningful way.',
        icon: CursorClickIcon,
    },
    { name: 'Security', href: '#', description: "Your customers' data will be safe and secure.", icon: ShieldCheckIcon },
    {
        name: 'Integrations',
        href: '#',
        description: "Connect with third-party tools that you're already using.",
        icon: ViewGridIcon,
    },
    {
        name: 'Automations',
        href: '#',
        description: 'Build strategic funnels that will drive your customers to convert',
        icon: RefreshIcon,
    },
]
const callsToAction = [
    { name: 'Watch Demo', href: '#', icon: PlayIcon },
    { name: 'Contact Sales', href: '#', icon: PhoneIcon },
]
const resources = [
    {
        name: 'Help Center',
        description: 'Get all of your questions answered in our forums or contact support.',
        href: '#',
        icon: SupportIcon,
    },
    {
        name: 'Guides',
        description: 'Learn how to maximize our platform to get the most out of it.',
        href: '#',
        icon: BookmarkAltIcon,
    },
    {
        name: 'Events',
        description: 'See what meet-ups and other events we might be planning near you.',
        href: '#',
        icon: CalendarIcon,
    },
    { name: 'Security', description: 'Understand how we take your privacy seriously.', href: '#', icon: ShieldCheckIcon },
]
const recentPosts = [
    { id: 1, name: 'Boost your conversion rate', href: '#' },
    { id: 2, name: 'How to use search engine optimization to drive traffic to your site', href: '#' },
    { id: 3, name: 'Improve your customer experience', href: '#' },
]

export default {
    components: {
        Popover,
        PopoverButton,
        PopoverGroup,
        PopoverPanel,
        ChevronDownIcon,
        MenuIcon,
        XIcon,
    },
    setup() {
        return {
            features,
            callsToAction,
            resources,
            recentPosts,
        }
    },
}
</script>
