<script lang="ts">
  import {
    DropdownMenu,
    DropdownMenuContent,
    DropdownMenuItem,
    DropdownMenuTrigger
  } from "$lib/components/ui/dropdown-menu";
  import {
    Sheet,
    SheetContent,
    SheetFooter,
    SheetHeader,
    SheetTitle,
    SheetTrigger,
  } from "$lib/components/ui/sheet";
  import { Button, buttonVariants } from "$lib/components/ui/button";
  import { Separator } from "$lib/components/ui/separator";
  import { ChevronsDown, Menu } from "lucide-svelte";
  import GithubIcon from "$lib/icons/GithubIcon.svelte";
  import ToggleTheme from "$lib/components/ToggleTheme.svelte";

  interface RouteProps {
    href: string;
    label: string;
  }

  interface FeatureProps {
    title: string;
    description: string;
  }

  const routeList: RouteProps[] = [
      { href: "#servicii", label: "Servicii" },
      { href: "#tarife", label: "Tarife" },
      { href: "#despre", label: "Despre Noi" },
    { href: "#testimonials", label: "Testimoniale" },
    { href: "#contact", label: "Contact" },
    { href: "#faq", label: "FAQ" },
  ];

  let isOpen = false;
</script>

<header
  class="w-[90%] md:w-[70%] lg:w-[75%] lg:max-w-screen-xl top-5 mx-auto sticky border z-40 rounded-2xl flex justify-between items-center p-2 bg-card shadow-md dark:shadow-dark shadow-light"
>
  <a href="/" class="font-bold text-lg flex items-center">
    <img src="logo.png" alt="logo" width="150px" height="150px">
  </a>

  <!-- Mobile -->
  <div class="flex items-center lg:hidden">
    <Sheet bind:open={isOpen}>
      <SheetTrigger>
        <Menu on:click={() => (isOpen = true)} class="cursor-pointer" />
      </SheetTrigger>

      <SheetContent side="left" class="flex flex-col justify-between rounded-tr-2xl rounded-br-2xl bg-card">
        <div>
          <SheetHeader class="mb-4 ml-4">
            <SheetTitle class="flex items-center">
              <a href="/" class="flex items-center">
                <img src="logo.png" alt="logo" width="150px" height="150px">
              </a>
            </SheetTitle>
          </SheetHeader>

          <div class="flex flex-col gap-2">
            {#each routeList as { href, label }}
              <a on:click={() => (isOpen = false)} {href}>
                <Button variant="ghost" class="justify-start text-base w-full">
                  {label}
                </Button>
              </a>
            {/each}
          </div>
        </div>

        <SheetFooter class="flex-col sm:flex-col justify-start items-start">
          <Separator class="mb-2" />
          <ToggleTheme />
        </SheetFooter>
      </SheetContent>
    </Sheet>
  </div>
  <div class="hidden lg:flex items-center gap-1">

    <!-- Navigation Links -->
    {#each routeList as { href, label }}
      <a {href} class={buttonVariants({ variant: "ghost", size: "default" })}>
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
