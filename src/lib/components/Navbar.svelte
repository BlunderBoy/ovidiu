<script lang="ts">
    import {Sheet, SheetContent, SheetHeader, SheetTitle, SheetTrigger,} from "$lib/components/ui/sheet";
    import {Button, buttonVariants} from "$lib/components/ui/button";
    import {Menu} from "lucide-svelte";

    interface RouteProps {
        href: string;
        label: string;
    }

    interface FeatureProps {
        title: string;
        description: string;
    }

    const routeList: RouteProps[] = [
        {href: "#servicii", label: "Servicii"},
        {href: "#tarife", label: "Tarife"},
        {href: "#despre", label: "Despre Noi"},
        {href: "#testimonials", label: "Testimoniale"},
        {href: "#contact", label: "Contact"},
        {href: "#faq", label: "FAQ"},
    ];

    let isOpen = false;
</script>

<header
        class="absolute top-5 left-1/2 transform -translate-x-1/2
            w-[90%] md:w-[70%] lg:w-[75%] lg:max-w-screen-xl
            border z-40 rounded-2xl flex justify-between items-center
            p-2 bg-card shadow-md dark:shadow-dark shadow-light
            h-16 md:h-20"
>
    <a class="font-bold text-lg flex items-center" href="/">
        <img alt="logo" class="h-[60px] w-[150px] max-h-full" src="logo.webp">
    </a>

    <!-- Mobile -->
    <div class="flex items-center lg:hidden">
        <Sheet bind:open={isOpen}>
            <SheetTrigger>
                <Menu class="cursor-pointer mr-3" on:click={() => (isOpen = true)}/>
            </SheetTrigger>

            <SheetContent class="flex flex-col justify-between rounded-tr-2xl rounded-br-2xl bg-card" side="left">
                <div>
                    <SheetHeader class="mb-4 ml-4">
                        <SheetTitle class="flex items-center">
                            <a class="flex items-center" href="/">
                                <img alt="logo" height="150px" src="logo.webp" width="150px">
                            </a>
                        </SheetTitle>
                    </SheetHeader>

                    <div class="flex flex-col gap-2">
                        {#each routeList as {href, label}}
                            <a on:click={() => (isOpen = false)} {href}>
                                <Button variant="ghost" class="justify-start text-base w-full">
                                    {label}
                                </Button>
                            </a>
                        {/each}
                    </div>
                </div>
            </SheetContent>
        </Sheet>
    </div>
    <div class="hidden lg:flex items-center gap-1">

        <!-- Navigation Links -->
        {#each routeList as {href, label}}
            <a {href} class={buttonVariants({ variant: "ghost", size: "default" })} aria-label="menu">
                {label}
            </a>
        {/each}
    </div>
</header>

<style>
    .shadow-light {
        box-shadow: inset 0 0 5px rgba(0, 0, 0, 0.085);
    }

    .shadow-dark {
        box-shadow: inset 0 0 5px rgba(255, 255, 255, 0.141);
    }
</style>
