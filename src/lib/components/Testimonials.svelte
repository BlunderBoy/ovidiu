<script lang="ts">
  import { Avatar, AvatarFallback, AvatarImage } from "$lib/components/ui/avatar";
  import {
    Card,
    CardContent,
    CardDescription,
    CardHeader,
    CardTitle,
  } from "$lib/components/ui/card";
  import * as Carousel from "$lib/components/ui/carousel";
  import { Star } from "lucide-svelte";
  import type { CarouselAPI } from "$lib/components/ui/carousel/context";
  import Autoplay from "embla-carousel-autoplay";

  interface ReviewProps {
    image: string;
    name: string;
    userName: string;
    comment: string;
    rating: number;
  }

  const reviewList: ReviewProps[] = [
    {
      image: "https://github.com/shadcn.png",
      name: "Năznean I.",
      userName: "Târgu Mureș",
      comment:
        "Am evaluat 4 proprietăți. Totul a decurs normal iar rapoartele de evaluare le-am primit în aproximativ o săptămână.",
      rating: 5.0,
    },
    {
      image: "https://github.com/zxce3.png",
      name: "Huib S.",
      userName: "Țările de Jos",
      comment:
        "Ați pregătit un raport excelent. Vă mulțumesc pentru acesta. Ați făcut cercetări amănunțite, astfel încât raportul conține o " +
          "mulțime de informații utile pentru mine și Anca, de care avem nevoie pentru a lua o decizie bine gândită.",
      rating: 5.0,
    },
    {
      image: "https://github.com/shadcn.png",
      name: "Lehel K.",
      userName: "Sângeorgiu de Mureș",
      comment:
        "Comunicare eficientă. Am primit raportul de evaluare într-o săptămână de la data inspecției.",
      rating: 4.9,
    },
      {
      image: "https://github.com/shadcn.png",
      name: "Alexandru M.",
      userName: "Târgu Mureș",
      comment:
        "Super evaluator, promt si corect.",
      rating: 4.9,
    },
      {
      image: "https://github.com/shadcn.png",
      name: "Maria P.",
      userName: "Bucuresti",
      comment:
        "Am colaborat cu un evaluator de nota 10!!!!!!.",
      rating: 4.9,
    }
  ];

  let api = $state<CarouselAPI>();
  const plugin = Autoplay({ delay: 4000, stopOnInteraction: true });
</script>

<section id="testimonials" class="container py-12 sm:py-12">
  <div class="text-center mb-8">

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
      Feedback-uri din partea clienților noștri
    </h2>
  </div>

  <Carousel.Root
    opts={{
      align: "start",
      loop: true,
    }}
    plugins={[plugin]}
    class="relative w-[80%] sm:w-[90%] lg:max-w-screen-xl mx-auto"
    setApi={(emblaApi) => (api = emblaApi)}
    onmouseenter={plugin.stop}
    onmouseleave={plugin.reset}
  >
    <Carousel.Content class="-ml-4">
      {#each reviewList as review (review.name)}
        <Carousel.Item class="pl-4 md:basis-1/2 lg:basis-1/3">
          <Card class="bg-muted/50 dark:bg-card h-full">
            <CardContent class="p-6 h-full flex flex-col">
              <div class="flex-1">
                <div class="flex gap-1 mb-6">
                  {#each Array(5) as _}
                    <Star class="size-4 fill-primary text-primary" />
                  {/each}
                </div>

                <p class="mb-6">"{review.comment}"</p>
              </div>

              <div class="flex items-center gap-4 pt-6 border-t">
                <Avatar>
                  <AvatarImage
                    src={review.image}
                    alt={`Avatar of ${review.name}`}
                  />
                  <AvatarFallback>
                    {review.name.split(' ').map(n => n[0]).join('')}
                  </AvatarFallback>
                </Avatar>

                <div class="flex flex-col">
                  <CardTitle class="text-lg">{review.name}</CardTitle>
                  <CardDescription>{review.userName}</CardDescription>
                </div>
              </div>
            </CardContent>
          </Card>
        </Carousel.Item>
      {/each}
    </Carousel.Content>
    <Carousel.Previous />
    <Carousel.Next />
  </Carousel.Root>
</section>
