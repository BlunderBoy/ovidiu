<script lang="ts">
    import {Card, CardDescription, CardHeader, CardTitle,} from "$lib/components/ui/card";
    import {Badge} from "$lib/components/ui/badge";
    import {Separator} from "$lib/components/ui/separator"

    interface ServiceProps {
        title: string;
        price: string;
        description: string;
    }

    const serviceList: ServiceProps[] = [
        {
            title: "Evaluare apartament/ garsonieră",
            description:
                "Include inspecție, întocmirea Raportului de evaluare, consultanță",
            price: 'De la 600 RON',
        },
        {
            title: "Evaluare teren",
            description:
                "Include inspecție, întocmirea Raportului de evaluare, consultanță",
            price: 'De la 600 RON',
        },
        {
            title: "Evaluare casă/vilă",
            description: "Include inspecție, întocmirea Raportului de evaluare, consultanță",
            price: 'De la 1000 RON',
        },
        {
            title: "Evaluare spații comerciale/ industriale",
            description: "Include inspecție, întocmirea Raportului de evaluare, consultanță",
            price: 'De la 1000 RON',
        },
        {
            title: "Evaluare bunuri mobile",
            description: "Include inspecție, întocmirea Raportului de evaluare, consultanță",
            price: 'De la 400 RON',
        },
        {
          title: "Alte evaluari",
          description: "Include inspecție, întocmirea Raportului de evaluare, consultanță",
          price: 'De la 400 RON',
        },
    ];
</script>

<section class="container py-12 sm:py-12" id="tarife">

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
        Tarife
    </h2>
    <h3 class="md:w-3/4 mx-auto text-xl text-center text-muted-foreground">
        Tarifele de mai jos sunt orientative. Acestea pot varia în funcție de mai multe elemente.
    </h3>

    <div class="flex justify-center">
                <Separator class="lg:w-3/5 w-3/4 m-4"/>
            </div>

    <h3 class="md:w-3/4 mx-auto text-xl text-center text-muted-foreground">
        Tarifele practicate pentru evaluări nu țin cont de valoarea proprietății sau a bunului evaluat. Acestea sunt
        strict legate de scopul evaluării și implicit de timpul de lucru alocat pentru efectuarea întregului proces de
        evaluare.
    </h3>
    <div class="flex justify-center">
                <Separator class="lg:w-3/5 w-3/4 m-4"/>
            </div>
    <h3 class="md:w-3/4 mx-auto text-xl text-center text-muted-foreground mb-12 font-bold">
        Pentru ofertă concretă de preț, vă rugăm să ne contactați!
    </h3>

    <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4 w-full mx-auto">
        {#each serviceList as {title, description, price}}
            <Card class="bg-muted/60 dark:bg-card h-full pb-6 relative">
                <CardHeader>
                    <CardTitle>{title}</CardTitle>
                    <CardDescription>{description}</CardDescription>
                </CardHeader>
                <Badge variant="secondary" class="absolute -top-2 -right-3">
                    {price}
                </Badge>
            </Card>
        {/each}
    </div>
</section>
