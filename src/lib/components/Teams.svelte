<script lang="ts">
    import LinkedInIcon from "$lib/icons/LinkedInIcon.svelte";
    import GithubIcon from "$lib/icons/GithubIcon.svelte";
    import XIcon from "$lib/icons/XIcon.svelte";

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

<section class="container max-w-7xl mx-auto px-4 py-16 sm:py-24 lg:py-32" id="despre">
    <div class="text-center mb-12">
        <div class="mb-12">
            <h2 class="text-lg text-primary text-center mb-3 tracking-wider">Despre noi</h2>

            <h2 class="mb-12 text-3xl md:text-4xl text-center font-bold">
                O echipă de profesioniști
            </h2>

            <p>Echipa noastră este formată din economiști și ingineri, membrii autorizați ANEVAR pentru evaluarea proprietăților imobiliare, bunurilor mobile și evaluarea întreprinderii. </p>
            <p>Cu o vastă experiență în plan profesional dar și în domeniul evaluărilor, putem răspunde oricărei provocări.</p>
            <p>Suntem axați pe eficiență și pe profesionalism, participarea anuală la programe de formare continuă fiind o regulă, nu doar din cauza obligativității acesteia ci și din dorința de a fi la curent cu noutățile din domeniul în care activăm.</p>
        </div>

        <div class="grid lg:grid-cols-2 place-items-center lg:gap-24">
            <div>
                <img alt="cladiri1" src="cladiri1.jpg">
            </div>
            <div>
                <h1 class="text-3xl md:text-4xl text-center font-bold">
                    Misiune
                </h1>

                <h2 class="text-lg text-primary text-center mb-3 tracking-wider">
                    Servicii pe măsura clienților
                </h2>

                <p>
                    Fiecare client este important pentru noi.
                    Adaptarea și găsirea de soluții personalizate pentru fiecare dintre ei este o permanentă provocare
                    dar și un lucru care ne ajută să evoluăm. Ne străduim să găsim cea mai bună soluție în funcție de
                    fiecare situație.
                </p>
            </div>
            <div>
                <h1 class="text-3xl md:text-4xl text-center font-bold">
                    Viziune
                </h1>

                <h2 class="text-lg text-primary text-center mb-3 tracking-wider">
                    Evoluție de la an la an
                </h2>

                <p>
                    Viziunea noastră este de a crea o echipă multidisciplinară de profesioniști care să ofere soluții
                    profesionale. Ne concentrăm pe impactul real pe care serviciile noastre îl pot avea asupra
                    clienților și a pieței, și ne străduim să fim lideri ceea ce facem.
                </p>
            </div>
            <div>
                <img alt="cladiri2" src="cladiri2.jpg">
            </div>
        </div>
    </div>
</section>
