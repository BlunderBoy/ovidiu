<script lang="ts">
  import { Card, CardContent, CardHeader, CardTitle } from "$lib/components/ui/card";
  import {
      Paintbrush,
      MessageCircle,
      TabletSmartphone,
      BadgeCheck,
      Goal,
      PictureInPicture,
      MousePointerClick,
      Newspaper, Blocks, LineChart, Sparkle,
  } from "lucide-svelte";

  interface FeaturesProps {
    icon: string;
    title: string;
    description: string;
  }

  const featureList: FeaturesProps[] = [
    {
      icon: "blocks",
      title: "Evaluarea proprietăților imobiliare",
      description:
        "Apartamente, garsoniere, terenuri, case/vile, cabane, spații comerciale, spații industriale etc.",
    },
    {
      icon: "lineChart",
      title: "Evaluarea bunurilor mobile",
      description:
        "Autovehicule, stocuri, instalații complexe, echipamente și echipamente de producție, stocuri de marfă și materiale etc",
    },
    {
      icon: "goal",
      title: "Evaluare pentru garantarea împrumutului",
      description:
        "Obligatorie la accesarea sau refinanțarea creditelor ipotecare sau la creditele cu garanție ipotecară",
    },
    {
      icon: "sparkle",
      title: "Evaluarea pentru informare",
      description:
        "Utilizată în diverse scopuri, cu ar fi partajul, dezbaterea moștenirii sau pur și simplu pentru obținerea valorii de piață a unui imobil.",
    },
      {
      icon: "sparkle",
      title: "Evaluarea pentru scopuri contabile",
      description:
        "Utilizată de către persoanele juridice pentru înregistrarea valori bunurilor în contabilitate sau pentru alte scopuri contabile.",
    },
      {
      icon: "sparkle",
      title: "Evaluarea pentru impozitare",
      description:
        "Obligatorie pentru persoanele juridice care dețin imobile și pentru persoane fizice care dețin imobile cu altă destinație decât cea rezidențială.",
    },
  ];

  const iconMap = {
    blocks: Blocks,
    lineChart: LineChart,
    goal: Goal,
    sparkle: Sparkle
  };
</script>

<section id="features" class="container py-12 sm:py-12">
  <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
    Servicii v1
  </h2>

  <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
    Ce oferim?
  </h2>

  <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8">
    Oferim servicii de evaluare pentru bunuri imobile și bunuri mobile. Ne desfășurăm activitatea în județul Mureș dar ne putem deplasa în toată țara.
  </h3>

  <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4">
    {#each featureList as { icon, title, description }}
      <Card class="h-full bg-background border-0 shadow-none">
        <CardHeader class="flex justify-center items-center">
          <div class="bg-primary/20 p-2 rounded-full ring-8 ring-primary/10 mb-4">
            <svelte:component 
              this={iconMap[icon]} 
              class="size-6 text-primary"
            />
          </div>
          <CardTitle class="text-center">{title}</CardTitle>
        </CardHeader>

        <CardContent class="text-muted-foreground text-center">
          {description}
        </CardContent>
      </Card>
    {/each}
  </div>
</section>
