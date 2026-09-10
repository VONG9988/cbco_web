<script setup>
import Icon from "@/components/Icon.vue";
import Navbar from "@/components/Navbar.vue";
import Footer from "@/components/Footer.vue";
</script>

<template>
    <div class="page founder-page">
        <Navbar />
        <main>
            <section class="founder-hero">
                <div class="founder-hero-copy">
                    <p class="eyebrow">The person behind CBCO</p>
                    <h1>Visal<br /><em>ALLY</em></h1>
                    <p class="founder-lede">
                        Founder of Cambodia Banner Charity Organization, building a
                        place where practical support begins with people.
                    </p>
                </div>
                <div class="founder-hero-image">
                    <img src="/images/sal.jpg" alt="CBCO community members" />
                </div>
            </section>

            <section id="founder-story" class="founder-story">
                <div>
                    <p class="eyebrow">Founder profile</p>
                    <h2>The person<br /><em>who began CBCO.</em></h2>
                </div>
                <div class="founder-story-copy">
                    <p>
                        Visan Hang is the founder of Cambodia Banner Charity
                        Organization (CBCO).
                    </p>
                    <p>
                        This organization carries the founder's commitment to
                        supporting children, families, and communities in Cambodia.
                    </p>
                </div>
            </section>

            <section class="founder-quote">
                <p class="eyebrow">The organization continues</p>
                <blockquote>
                    Visal & Ally<br /><em>Founder of CBCO</em>
                </blockquote>
                <a class="underlined-link" href="/">Return to CBCO
                    <Icon name="arrow-up-right" />
                </a>
            </section>
        </main>
        <Footer />
    </div>
</template>