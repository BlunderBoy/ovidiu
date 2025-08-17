<script lang="ts">
  import { Card, CardContent, CardHeader, CardTitle } from "$lib/components/ui/card";
  import {
    Sparkle,
    Tag,
    Paintbrush,
    Blocks,
    LineChart,
    Wallet,
  } from "lucide-svelte";

  interface BenefitsProps {
    icon: 'sparkle' | 'tag' | 'paintbrush' | 'blocks' | 'lineChart' | 'wallet';
    title: string;
    description: string;
  }

  const benefitList: BenefitsProps[] = [
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
      icon: "wallet",
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
    sparkle: Sparkle,
    tag: Tag,
    paintbrush: Paintbrush,
    blocks: Blocks,
    lineChart: LineChart,
    wallet: Wallet,
  };
</script>

<section id="servicii" class="container py-12 sm:py-12">
  <div class="place-items-center lg:gap-24">
    <div>
        <h2>Servicii v2 </h2>
      <h2 class="text-3xl md:text-4xl font-bold mb-4">
        Ce oferim?
      </h2>
      <p class="text-xl text-muted-foreground mb-8">
        Oferim servicii de evaluare pentru bunuri imobile și bunuri mobile.
        Ne desfășurăm activitatea în județul Mureș dar ne putem deplasa în toată țara.
      </p>
    </div>

    <div class="grid lg:grid-cols-2 gap-4 w-full">
      {#each benefitList as { icon, title, description }, index}
        <Card class="bg-muted/50 dark:bg-card hover:bg-background dark:hover:bg-background transition-all delay-75 group/number">
          <CardHeader>
            <div class="flex justify-between">
              <svelte:component 
                this={iconMap[icon]} 
                class="size-8 mb-6 text-primary"
              />
              <span class="text-5xl text-muted-foreground/15 font-medium transition-all delay-75 group-hover/number:text-muted-foreground/30">
                0{index + 1}
              </span>
            </div>
            <CardTitle>{title}</CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground">
            {description}
          </CardContent>
        </Card>
      {/each}
    </div>
  </div>
</section>
