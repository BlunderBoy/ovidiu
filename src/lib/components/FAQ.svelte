<script lang="ts">
  import {
    Accordion,
    AccordionContent,
    AccordionItem,
    AccordionTrigger,
  } from "$lib/components/ui/accordion";

  interface FAQProps {
    question: string;
    answer: string;
    value: string;
  }

  const FAQList: FAQProps[] = [
    {
      question: "cat ma costa?",
      answer: "atata",
      value: "item-1",
    },
      {
      question: "Unde?",
      answer: "tg-mures",
      value: "item-2",
    },
      {
      question: "intrebare?",
      answer: "raspuns",
      value: "item-3",
    },
  ];
</script>

<section id="faq" class="container md:w-[700px] py-24 sm:py-32">
  <div class="text-center mb-8">
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider">FAQS</h2>
    <h2 class="text-3xl md:text-4xl text-center font-bold">
      Common Questions
    </h2>
  </div>

  <Accordion type="single" class="w-full">
    {#each FAQList as { question, answer, value }}
      <AccordionItem {value}>
        <AccordionTrigger class="text-left">
          {question}
        </AccordionTrigger>
        <AccordionContent>
          {answer}
        </AccordionContent>
      </AccordionItem>
    {/each}
  </Accordion>

  <h3 class="font-medium mt-4">
    Inca aveti intrebari?
    <a href="#contact" class="text-muted-foreground">
      <span class="underline">Intrebati-ne!</span>
    </a>
  </h3>
</section>
