<script lang="ts">
    import {ChevronsDown} from "lucide-svelte";
</script>

<footer class="container py-6 pb-16 sm:py-6 sm:pb-6" id="footer">
    <div class="p-10 bg-muted/50 dark:bg-card border rounded-2xl">
        <div class="flex flex-col items-center text-center gap-6 sm:flex-row sm:justify-between sm:text-left">

            <!-- Logo & Company -->
            <div class="flex flex-col items-center sm:flex-row sm:items-center gap-4">
                <a class="flex font-bold items-center" href="/">
                    <img src="logo.webp" alt="logo" width="150px" height="150px" class="mr-2">
                    <h3 class="text-xl sm:text-2xl">VR SERVICES SRL</h3>
                </a>
            </div>

            <!-- Copyright -->
            <section>
                <h3 class="text-sm sm:text-base">
                    &copy; 2024 Designed and developed by Cristian
                </h3>
            </section>
        </div>
    </div>
</footer>
