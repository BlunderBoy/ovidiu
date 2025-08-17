<script lang="ts">
    import {Button} from "$lib/components/ui/button";
    import {Card, CardContent, CardFooter, CardHeader} from "$lib/components/ui/card";
    import {Label} from "$lib/components/ui/label";
    import {Input} from "$lib/components/ui/input";
    import {Textarea} from "$lib/components/ui/textarea";
    import {Alert, AlertDescription, AlertTitle} from "$lib/components/ui/alert";
    import {AlertCircle, Building2, Mail, Phone} from "lucide-svelte";

    interface ContactFormProps {
        firstName: string;
        lastName: string;
        email: string;
        phoneNumber: string;
        message: string;
    }

    let contactForm: ContactFormProps = {
        firstName: "",
        lastName: "",
        email: "",
        phoneNumber: "",
        message: "",
    };

    let invalidInputForm = false;

    function handleSubmit(event: SubmitEvent) {
        console.log(contactForm);
        event.preventDefault();
        const {firstName, lastName, email, phoneNumber, message} = contactForm;
        console.log(contactForm);

        window.location.href = `mailto:cristialex99@gmail.com?subject=Contact ${firstName + " " + lastName}&body=Buna ziua, sunt ${firstName} ${lastName}, numar de telefon ${phoneNumber}. %0D%0A${message}`;
    }

    const subjects = [
        {value: "Web Development", label: "Web Development"},
        {value: "Mobile Development", label: "Mobile Development"},
        {value: "Figma Design", label: "Figma Design"},
        {value: "REST API", label: "REST API"},
        {value: "FullStack Project", label: "FullStack Project"}
    ];
</script>

<section class="container py-12 sm:py-12" id="contact">
    <section class="grid grid-cols-1 md:grid-cols-2 gap-8">
        <div>
            <div class="mb-4">
                <h2 class="text-3xl md:text-4xl font-bold">Contacteaza-ne!</h2>
            </div>

            <div class="flex flex-col gap-4">
                <div>
                    <div class="flex gap-2 mb-1">
                        <Phone/>
                        <div class="font-bold">Suna!</div>
                    </div>
                    <div>0744 332 566</div>
                </div>

                <div>
                    <div class="flex gap-2 mb-1">
                        <Mail/>
                        <div class="font-bold">Da un mail!</div>
                    </div>
                    <div>office@evaluatoranevar.com</div>
                </div>

                <div>
                    <div class="flex gap-2 mb-1">
                        <Building2/>
                        <div class="font-bold">Haide!</div>
                    </div>
                    <div>Strada Bărăganului 18, Târgu Mureș 540272</div>
                </div>


                <div>
                    <iframe
                            allowfullscreen
                            height="450"
                            loading="lazy"
                            referrerpolicy="no-referrer-when-downgrade"
                            src="https://www.google.com/maps/embed/v1/place?key=AIzaSyDSpTLhmfSR4bGunD_zqXx2L4FIFBqx51s
                                &q=VR+Services+SRL+mures"
                            style="border:0"
                            title="Harta"
                            width="100%">
                    </iframe>
                </div>
            </div>
        </div>

        <!-- Form -->
        <Card class="bg-muted/60 dark:bg-card">
            <CardHeader class="text-primary text-2xl"/>
            <CardContent>
                <form class="grid gap-6" on:submit={handleSubmit}>
                    <div class="flex flex-col md:flex-row gap-8">
                        <div class="flex flex-col w-full gap-1.5">
                            <Label for="firstName">Nume</Label>
                            <Input
                                    bind:value={contactForm.firstName}
                                    id="firstName"
                                    placeholder="Popescu"
                                    type="text"
                            />
                        </div>

                        <div class="flex flex-col w-full gap-1.5">
                            <Label for="lastName">Prenume</Label>
                            <Input
                                    bind:value={contactForm.lastName}
                                    id="lastName"
                                    placeholder="Ion"
                                    type="text"
                            />
                        </div>
                    </div>

                    <div class="flex flex-col gap-1.5">
                        <Label for="contactEmail">Email</Label>
                        <Input
                                bind:value={contactForm.email}
                                id="contactEmail"
                                placeholder="popescuion@gmail.com"
                                type="email"
                        />
                    </div>

                    <div class="flex flex-col gap-1.5">
                        <Label for="contactEmail">Numar de telefon</Label>
                        <Input
                                bind:value={contactForm.phoneNumber}
                                id="contactEmail"
                                placeholder="0744 444 444"
                                type="tel"
                        />
                    </div>

                    <div class="flex flex-col gap-1.5">
                        <Label for="contactMessage">Mesaj</Label>
                        <Textarea
                                bind:value={contactForm.message}
                                id="contactMessage"
                                placeholder="Mesajul tau..."
                                rows={5}
                        />
                    </div>

                    {#if invalidInputForm}
                        <Alert variant="destructive">
                            <AlertCircle class="w-4 h-4"/>
                            <AlertTitle>Error</AlertTitle>
                            <AlertDescription>
                                There is an error in the form. Please check your input.
                            </AlertDescription>
                        </Alert>
                    {/if}

                    <Button class="mt-4" type="submit">Trimite-ne mesajul!</Button>
                </form>
            </CardContent>
            <CardFooter/>
        </Card>
    </section>
</section>
