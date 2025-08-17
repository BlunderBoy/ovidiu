<script lang="ts">
    import LinkedInIcon from "$lib/icons/LinkedInIcon.svelte";
    import GithubIcon from "$lib/icons/GithubIcon.svelte";
    import XIcon from "$lib/icons/XIcon.svelte";
    import {Separator} from "$lib/components/ui/separator"

    interface TeamProps {
        imageUrl: string;
        firstName: string;
        lastName: string;
        positions: string[];
    }

    const socialIconMap = {
        LinkedIn: LinkedInIcon,
        Github: GithubIcon,
        X: XIcon,
    };
</script>

<section class="container max-w-7xl mx-auto px-4 py-12 sm:py-12" id="despre">
    <div class="text-center">
        <div class="mx-8">
            <h2 class="text-3xl text-primary text-center mb-3 tracking-wider">Despre noi</h2>

            <h2 class="mb-12 text-3xl md:text-4xl text-center font-bold">
                O echipă de profesioniști
            </h2>

            <p class="md:w-3/4 mx-auto text-xl text-center text-muted-foreground">Echipa noastră este formată din
                economiști și ingineri, membrii autorizați ANEVAR pentru evaluarea
                proprietăților imobiliare, bunurilor mobile și evaluarea întreprinderii. </p>

            <div class="flex justify-center">
                <Separator class="lg:w-3/5 w-3/4 m-4"/>
            </div>

            <p class="md:w-3/4 mx-auto text-xl text-center text-muted-foreground">Cu o vastă experiență în plan
                profesional dar și în domeniul evaluărilor, putem răspunde oricărei
                provocări.</p>

            <div class="flex justify-center">
                <Separator class="lg:w-3/5 w-3/4 m-4"/>
            </div>

            <p class="md:w-3/4 mx-auto text-xl text-center text-muted-foreground">Suntem axați pe eficiență și pe
                profesionalism, participarea anuală la programe de formare continuă fiind
                o regulă, nu doar din cauza obligativității acesteia ci și din dorința de a fi la curent cu noutățile
                din domeniul în care activăm.</p>
        </div>

        <section class="bg-muted/50 dark:bg-card p-10 rounded-2xl space-y-16">
            <!-- First block: image left, text right -->
            <div class="flex flex-col md:flex-row items-center gap-8">
                <div class="md:w-1/2">
                    <img alt="cladiri1" class="w-full rounded-xl shadow-md" src="cladiri1.jpg">
                </div>
                <div class="lg:ml-8 md:w-1/2 text-center md:text-left space-y-4">
                    <h1 class="text-3xl md:text-4xl font-bold">Misiune</h1>
                    <h2 class="text-lg text-primary mb-3 tracking-wider">Servicii pe măsura clienților</h2>
                    <p class=" mx-auto text-xl text-muted-foreground">
                        Fiecare client este important pentru noi. Adaptarea și găsirea de soluții personalizate pentru
                        fiecare dintre ei este o permanentă provocare
                        dar și un lucru care ne ajută să evoluăm. Ne străduim să găsim cea mai bună soluție în funcție
                        de fiecare situație.
                    </p>
                </div>
            </div>

            <!-- Second block: text left, image right -->
            <div class="flex flex-col md:flex-row-reverse items-center gap-8">
                <div class="md:w-1/2">
                    <img alt="cladiri2" class="w-full rounded-xl shadow-md" src="cladiri2.jpg">
                </div>
                <div class="lg:mr-8 md:w-1/2 text-center md:text-left space-y-4">
                    <h1 class="text-3xl md:text-4xl font-bold">Viziune</h1>
                    <h2 class="text-lg text-primary mb-3 tracking-wider">Evoluție de la an la an</h2>
                    <p class="mx-auto text-xl text-muted-foreground">
                        Viziunea noastră este de a crea o echipă multidisciplinară de profesioniști care să ofere
                        soluții profesionale. Ne concentrăm pe impactul real pe care serviciile noastre îl pot avea
                        asupra clienților și a pieței, și ne străduim să fim lideri ceea ce facem.
                    </p>
                </div>
            </div>
        </section>
    </div>
</section>
