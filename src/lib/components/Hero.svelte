<script lang="ts">
    import {Button} from "$lib/components/ui/button";
    import {ArrowRight} from "lucide-svelte";
    import {onMount} from "svelte";

    // Placeholder small image first
    let imageSrc = 'bg-small.webp';
    let heroSection: HTMLElement;

    const images = {
        small: 'bg-small.webp',
        medium: 'bg-medium.webp',
        large: 'bg.webp'
    };

    function getResponsiveSrc() {
        if (window.innerWidth < 640) return images.small;
        if (window.innerWidth < 1024) return images.medium;
        return images.large;
    }

    onMount(() => {
        if (!heroSection) return;

        const img = new Image();
        img.src = getResponsiveSrc();
        img.onload = () => {
            heroSection.style.backgroundImage = `url('${img.src}')`;
        };
    });

    //
    // onMount(() => {
    //     const section = document.getElementById('hero')!;
    //     const img = new Image();
    //     img.src = imageSrc;
    //     section.onload = () => {
    //         console.log(section)
    //         img.onload = () => {
    //             console.log(section)
    //             if (section) {
    //                 console.log('section')
    //                 section.style.backgroundImage = `url('${img.src}')`;
    //             }
    //         };
    //     }
    // })


</script>

<section
        bind:this={heroSection}
        class="relative overflow-hidden bg-cover bg-center bg-no-repeat"
        style="background-image: url({imageSrc}); background-position: center 40%;"
>
    <!-- Optional overlay for extra contrast -->
    <div class="absolute inset-0 bg-black/60"></div>

    <!-- Content -->
    <div class="container relative z-10 grid place-items-center gap-8 mx-auto py-20 md:py-32 text-center mt-20">
        <div class="space-y-8">
            <div class="max-w-screen-md mx-auto text-5xl md:text-6xl font-bold text-white">
                Obține consultanță gratuită
            </div>

            <p class="max-w-screen-sm mx-auto text-2xl text-white">
                Suntem aici să te ajutăm. Lasă datele tale de contact în formularul alăturat și un coleg te va contacta
                pentru asistență.
            </p>

            <div class="space-y-4 md:space-y-0 md:space-x-4">
                <a href="#contact">
                    <Button class="w-5/6 md:w-1/4 font-bold group/arrow mb-4">
                        Contacteaza-ne!
                        <ArrowRight
                                class="size-5 ml-2 group-hover/arrow:translate-x-1 transition-transform"
                        />
                    </Button>
                </a>

                <a href="#despre">
                    <Button class="w-5/6 md:w-1/4 font-bold" variant="secondary">
                        Afla mai multe!
                    </Button>
                </a>
            </div>
        </div>
    </div>
</section>


<style>

    @keyframes img-shadow-animation {
        from {
            opacity: 0.5;
            transform: translateY(30px);
        }

        to {
            opacity: 1;
            transform: translateY(0px);
        }
    }

    @keyframes img-border-animation {
        from {
            @apply border-t-primary/10;
        }

        to {
            @apply border-t-primary/60;
        }
    }
</style>
