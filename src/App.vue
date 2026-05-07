<template>
  <div>
    <!-- Top Bar -->
    <div class="top-bar">
      <div class="container top-bar-content">
        <div class="top-links">
          <a href="tel:+33635407550"><PhoneIcon size="14" /> +33 6 35 40 75 50</a>
          <a href="mailto:LocBoat83@outlook.com"><MailIcon size="14" /> LocBoat83@outlook.com</a>
        </div>
      </div>
    </div>

    <!-- Navigation -->
    <nav :class="['navbar', { 'scrolled': isScrolled }]">
      <div class="container nav-content">
        <div class="logo">
          <img src="./assets/logo.png" alt="LocBoat Logo" class="logo-img" />
          <span style="display: none;">LocBoat</span>
        </div>
        <div class="nav-links">
          <a href="#skipper">{{ t('nav.skipper') }}</a>
          <a href="#features">{{ t('nav.boat') }}</a>
          <a href="#pricing">{{ t('nav.pricing') }}</a>
          <a href="#gallery">{{ t('nav.gallery') }}</a>
          <button class="lang-switch" @click="toggleLocale">
            {{ locale === 'fr' ? 'EN' : 'FR' }}
          </button>
          <a href="https://www.instagram.com/locboat83/" target="_blank" class="nav-insta-btn" title="Instagram">
            <InstagramIcon size="22" />
          </a>
          <a href="tel:+33635407550" class="btn btn-primary nav-btn">{{ t('nav.book') }}</a>
        </div>
      </div>
    </nav>

    <!-- Hero Section -->
    <header class="hero">
      <div class="hero-bg"></div>
      <div class="container hero-content">
        <div class="glass hero-card">
          <h1 class="gradient-text">{{ t('hero.title') }}</h1>
          <p class="subtitle">{{ t('hero.subtitle') }}</p>
          <div class="hero-badges">
            <span class="badge"><MapPinIcon size="16" /> {{ t('hero.location') }}</span>
            <span class="badge"><CarIcon size="16" /> {{ t('hero.parking') }}</span>
          </div>
          <a href="tel:+33635407550" class="btn btn-primary cta-btn">
            <PhoneIcon size="20" class="mr-2" /> {{ t('hero.cta') }}
          </a>
        </div>
      </div>
    </header>

    <!-- Skipper Section -->
    <section id="skipper" class="section-light">
      <div class="container">
        <div class="skipper-container">
          <div class="skipper-content">
            <h2 class="section-title" style="text-align: left;">{{ t('skipper.title') }}</h2>
            <h3 class="gradient-text skipper-subtitle">{{ t('skipper.subtitle') }}</h3>
            <p class="skipper-desc">{{ t('skipper.desc1') }}</p>
            <p class="skipper-desc">{{ t('skipper.desc2') }}</p>
            
            <ul class="skipper-bullets">
              <li><CheckCircleIcon class="check-icon"/> {{ t('skipper.bullet1') }}</li>
              <li><CheckCircleIcon class="check-icon"/> {{ t('skipper.bullet2') }}</li>
              <li><CheckCircleIcon class="check-icon"/> {{ t('skipper.bullet3') }}</li>
            </ul>
          </div>
          <div class="skipper-image-wrapper">
            <!-- Placeholder for Skipper Image -->
            <div class="glass skipper-placeholder">
              <UserIcon size="80" class="text-primary opacity-50" />
              <p>Photo de Thibault à venir</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Features & Boat Stats -->
    <section id="features" class="section-dark">
      <div class="container">
        <h2 class="section-title text-white">{{ t('features.title') }}</h2>
        <p class="boat-desc">
          {{ t('features.boat_desc') }}
        </p>
        
        <div class="boat-stats-container">
          <div class="stat-card glass-dark">
            <div class="stat-icon"><AnchorIcon size="28" /></div>
            <div class="stat-info">
              <span class="stat-value">{{ t('features.stat_length_val') }}</span>
              <span class="stat-label">{{ t('features.stat_length_lbl') }}</span>
            </div>
          </div>
          <div class="stat-card glass-dark">
            <div class="stat-icon"><UserIcon size="28" /></div>
            <div class="stat-info">
              <span class="stat-value">{{ t('features.stat_cap_val') }}</span>
              <span class="stat-label">{{ t('features.stat_cap_lbl') }}</span>
            </div>
          </div>
          <div class="stat-card glass-dark">
            <div class="stat-icon"><WavesIcon size="28" /></div>
            <div class="stat-info">
              <span class="stat-value">{{ t('features.stat_eng_val') }}</span>
              <span class="stat-label">{{ t('features.stat_eng_lbl') }}</span>
            </div>
          </div>
        </div>

        <div class="features-grid">
          <div class="feature glass-dark">
            <div class="icon-wrapper"><SunIcon /></div>
            <h3>{{ t('features.sunbed') }}</h3>
            <p>{{ t('features.sunbed_desc') }}</p>
          </div>
          <div class="feature glass-dark">
            <div class="icon-wrapper"><UtensilsIcon /></div>
            <h3>{{ t('features.dining') }}</h3>
            <p>{{ t('features.dining_desc') }}</p>
          </div>
          <div class="feature glass-dark">
            <div class="icon-wrapper"><WavesIcon /></div>
            <h3>{{ t('features.fun') }}</h3>
            <p>{{ t('features.fun_desc') }}</p>
          </div>
          <div class="feature glass-dark">
            <div class="icon-wrapper"><MusicIcon /></div>
            <h3>{{ t('features.comfort') }}</h3>
            <p>{{ t('features.comfort_desc') }}</p>
          </div>
          <div class="feature glass-dark">
            <div class="icon-wrapper"><DropletIcon /></div>
            <h3>{{ t('features.shower') }}</h3>
            <p>{{ t('features.shower_desc') }}</p>
          </div>
          <div class="feature glass-dark">
            <div class="icon-wrapper"><BedIcon /></div>
            <h3>{{ t('features.cabin') }}</h3>
            <p>{{ t('features.cabin_desc') }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Itineraries -->
    <section id="itineraries" class="section-light">
      <div class="container">
        <h2 class="section-title">{{ t('itineraries.title') }}</h2>
        <p class="pricing-subtitle">{{ t('itineraries.subtitle') }}</p>
        
        <!-- Local / Eco -->
        <h3 class="itinerary-category-title">{{ t('itineraries.eco_title') }}</h3>
        <br>
        <div class="itineraries-grid" style="margin-bottom: 3rem;">
          <div class="itinerary-card">
            <div class="itinerary-icon"><MountainIcon size="32" /></div>
            <h3>{{ t('itineraries.sicie') }}</h3>
            <p>{{ t('itineraries.sicie_desc') }}</p>
          </div>
          <div class="itinerary-card">
            <div class="itinerary-icon"><MapPinIcon size="32" /></div>
            <h3>{{ t('itineraries.mejean') }}</h3>
            <p>{{ t('itineraries.mejean_desc') }}</p>
          </div>
          <div class="itinerary-card">
            <div class="itinerary-icon"><WavesIcon size="32" /></div>
            <h3>{{ t('itineraries.carqueiranne') }}</h3>
            <p>{{ t('itineraries.carqueiranne_desc') }}</p>
          </div>
          <div class="itinerary-card">
            <div class="itinerary-icon"><SunIcon size="32" /></div>
            <h3>{{ t('itineraries.sanpeyre') }}</h3>
            <p>{{ t('itineraries.sanpeyre_desc') }}</p>
          </div>
        </div>

        <!-- Exploration -->
        <h3 class="itinerary-category-title">{{ t('itineraries.explo_title') }}</h3>
        <br>
        <div class="itineraries-grid">
          <div class="itinerary-card">
            <div class="itinerary-icon"><PalmtreeIcon size="32" /></div>
            <h3>{{ t('itineraries.porquerolles') }}</h3>
            <p>{{ t('itineraries.porquerolles_desc') }}</p>
          </div>
          <div class="itinerary-card">
            <div class="itinerary-icon"><AnchorIcon size="32" /></div>
            <h3>{{ t('itineraries.embiez') }}</h3>
            <p>{{ t('itineraries.embiez_desc') }}</p>
          </div>
          <div class="itinerary-card">
            <div class="itinerary-icon"><CompassIcon size="32" /></div>
            <h3>{{ t('itineraries.giens') }}</h3>
            <p>{{ t('itineraries.giens_desc') }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Pricing Section -->
    <section id="pricing" class="section-dark">
      <div class="container">
        <h2 class="section-title text-white">{{ t('pricing.title') }}</h2>
        <p class="pricing-subtitle text-white-opacity">{{ t('pricing.subtitle') }}</p>
        
        <div class="pricing-cards">
          <!-- Half Day -->
          <div class="pricing-card">
            <div class="card-label">Demi-journée</div>
            <div class="card-time">{{ t('pricing.half_day_time') }}</div>
            <div class="card-prices">
              <div class="season-price">
                <span class="season-label">Juillet – Août</span>
                <span class="season-amount">450€</span>
              </div>
              <div class="season-divider"></div>
              <div class="season-price">
                <span class="season-label">Hors saison</span>
                <span class="season-amount season-amount--low">350€</span>
              </div>
            </div>
            <div class="card-badge"><ShieldCheckIcon size="14"/> {{ t('pricing.no_deposit') }}</div>
          </div>

          <!-- Full Day (featured) -->
          <div class="pricing-card pricing-card--featured">
            <div class="featured-tag">Idéal</div>
            <div class="card-label">Journée Entière</div>
            <div class="card-time">{{ t('pricing.full_day_time') }}</div>
            <div class="card-prices">
              <div class="season-price">
                <span class="season-label">Juillet – Août</span>
                <span class="season-amount">750€</span>
              </div>
              <div class="season-divider"></div>
              <div class="season-price">
                <span class="season-label">Hors saison</span>
                <span class="season-amount season-amount--low">600€</span>
              </div>
            </div>
            <div class="card-badge"><ShieldCheckIcon size="14"/> {{ t('pricing.no_deposit') }}</div>
          </div>

          <!-- Sunset -->
          <div class="pricing-card pricing-card--sunset">
            <div class="card-label">🌅 Apéro Sunset</div>
            <div class="card-time">{{ t('pricing.sunset_time') }}</div>
            <div class="card-prices">
              <div class="season-price">
                <span class="season-label">{{ t('pricing.sunset_desc') }}</span>
                <span class="season-amount season-amount--sunset">300€</span>
              </div>
            </div>
            <div class="card-badge"><ShieldCheckIcon size="14"/> {{ t('pricing.no_deposit') }}</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Steps Section -->
    <section id="steps" class="section-light">
      <div class="container">
        <h2 class="section-title">{{ t('steps.title') }}</h2>
        <div class="steps-container">
          <div class="step-box">
            <div class="step-number">1</div>
            <h3>{{ t('steps.step1') }}</h3>
            <p>{{ t('steps.step1_desc') }}</p>
          </div>
          <div class="step-connector"></div>
          <div class="step-box">
            <div class="step-number">2</div>
            <h3>{{ t('steps.step2') }}</h3>
            <p>{{ t('steps.step2_desc') }}</p>
          </div>
          <div class="step-connector"></div>
          <div class="step-box">
            <div class="step-number">3</div>
            <h3>{{ t('steps.step3') }}</h3>
            <p>{{ t('steps.step3_desc') }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Gallery Section -->
    <section id="gallery" class="section-light">
      <div class="container">
        <h2 class="section-title">{{ t('gallery.title') }}</h2>
        <p class="pricing-subtitle">{{ t('gallery.subtitle') }}</p>
        
        <div class="gallery-grid">
          <div class="gallery-item" v-for="n in 6" :key="n">
            <div class="gallery-placeholder">
              <CameraIcon size="48" class="text-primary opacity-50 mb-2" />
              <span>{{ t('gallery.placeholder') }}</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Testimonials Section -->
    <section id="testimonials" class="section-dark testimonials-bg">
      <div class="container">
        <h2 class="section-title text-white">{{ t('testimonials.title') }}</h2>
        <div class="testimonials-grid">
          <div class="testimonial-card glass-dark">
            <div class="stars">★★★★★</div>
            <p class="review">"{{ t('testimonials.review1') }}"</p>
            <p class="name">- {{ t('testimonials.name1') }}</p>
          </div>
          <div class="testimonial-card glass-dark">
            <div class="stars">★★★★★</div>
            <p class="review">"{{ t('testimonials.review2') }}"</p>
            <p class="name">- {{ t('testimonials.name2') }}</p>
          </div>
          <div class="testimonial-card glass-dark">
            <div class="stars">★★★★★</div>
            <p class="review">"{{ t('testimonials.review3') }}"</p>
            <p class="name">- {{ t('testimonials.name3') }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- FAQ Section -->
    <section id="faq" class="section-light">
      <div class="container">
        <h2 class="section-title">{{ t('faq.title') }}</h2>
        <div class="faq-container">
          <div class="faq-item" v-for="n in 6" :key="n" @click="toggleFaq(n)" :class="{ active: activeFaq === n }">
            <div class="faq-question">
              <h3>{{ t(`faq.q${n}`) }}</h3>
              <ChevronDownIcon class="faq-icon" />
            </div>
            <div class="faq-answer">
              <p>{{ t(`faq.a${n}`) }}</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Location Section -->
    <section id="location" class="section-light">
      <div class="container">
        <h2 class="section-title">{{ t('location.title') }}</h2>
        <p class="pricing-subtitle">{{ t('location.subtitle') }}</p>
        
        <div class="location-container">
          <div class="location-info">
            <div class="location-card glass-light">
              <div class="location-card-header">
                <CarIcon size="32" class="text-accent" />
                <h3>{{ t('location.main_parking') }}</h3>
              </div>
              <p class="location-desc">{{ t('location.main_desc') }}</p>
              
              <h4>{{ t('location.other_parkings') }}</h4>
              <p class="location-list">{{ t('location.list') }}</p>
            </div>
          </div>
          
          <div class="map-container">
            <iframe 
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2913.064560855217!2d5.882121376839178!3d43.10269387113184!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x12c91ba7dcab5bc1%3A0x6b42b66236b281f!2sParking%20du%20Parc%20de%20la%20Navale!5e0!3m2!1sfr!2sfr!4v1715086745123!5m2!1sfr!2sfr" 
              width="100%" 
              height="100%" 
              style="border:0; border-radius: 1.5rem;" 
              allowfullscreen="" 
              loading="lazy" 
              referrerpolicy="no-referrer-when-downgrade">
            </iframe>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact CTA Section -->
    <section id="contact" class="contact-cta">
      <div class="container">
        <div class="glass cta-box">
          <h2 class="gradient-text">{{ t('contact.title') }}</h2>
          <p>{{ t('contact.desc') }}</p>
          <div class="cta-buttons">
            <a href="tel:+33635407550" class="btn btn-primary cta-main-btn">
              <PhoneIcon size="24" style="margin-right: 0.5rem;" /> {{ t('contact.call_now') }} (+33 6 35 40 75 50)
            </a>
            <a href="https://wa.me/33635407550" target="_blank" class="btn btn-whatsapp">
              <MessageCircleIcon size="24" style="margin-right: 0.5rem;" /> {{ t('contact.whatsapp') }}
            </a>
            <a href="mailto:LocBoat83@outlook.com" class="btn btn-secondary" style="width: 100%; max-width: 500px; background: rgba(255,255,255,0.1); color: white; border: 1px solid rgba(255,255,255,0.2);">
              <MailIcon size="24" style="margin-right: 0.5rem;" /> LocBoat83@outlook.com
            </a>
          </div>
        </div>
      </div>
    </section>

    <!-- Social Section -->
    <section class="section-dark" style="padding: 4rem 0; border-top: 1px solid rgba(255,255,255,0.1);">
      <div class="container" style="text-align: center;">
        <h3 style="color: white; margin-bottom: 2rem; font-size: 1.8rem; font-weight: 700;">{{ t('social.follow') }}</h3>
        <a href="https://www.instagram.com/locboat83/" target="_blank" class="btn btn-secondary social-btn">
          <InstagramIcon size="24" /> {{ t('social.insta_btn') }}
        </a>
      </div>
    </section>

    <footer>
      <div class="container footer-content">
        <p>&copy; 2026 LocBoat - Thibault. {{ t('footer.rights') }}</p>
        <button @click="showLegalModal = true" class="legal-link">{{ t('footer.legal') }}</button>
      </div>
    </footer>

    <!-- Legal Modal -->
    <div v-if="showLegalModal" class="modal-backdrop" @click="showLegalModal = false">
      <div class="modal-content" @click.stop>
        <h2>{{ t('legal.title') }}</h2>
        <div class="modal-body">
          <p>{{ t('legal.content1') }}</p>
          <p>{{ t('legal.content2') }}</p>
          <p>{{ t('legal.content3') }}</p>
        </div>
        <button @click="showLegalModal = false" class="btn btn-primary">{{ t('legal.close') }}</button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { useI18n } from 'vue-i18n'
import { 
  AnchorIcon, MapPinIcon, CarIcon, UserIcon, CheckCircleIcon,
  SunIcon, UtensilsIcon, WavesIcon, MusicIcon, BedIcon, DropletIcon,
  ShieldCheckIcon, PhoneIcon, MessageCircleIcon, PalmtreeIcon, MountainIcon, CompassIcon,
  ChevronDownIcon, CameraIcon, InstagramIcon, MailIcon
} from 'lucide-vue-next'

const { t, locale } = useI18n()
const isScrolled = ref(false)
const activeFaq = ref(null)
const showLegalModal = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const toggleLocale = () => {
  locale.value = locale.value === 'fr' ? 'en' : 'fr'
}

const toggleFaq = (n) => {
  activeFaq.value = activeFaq.value === n ? null : n
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
/* Top Bar */
.top-bar {
  background: var(--bg-color);
  border-bottom: 1px solid rgba(0,0,0,0.05);
  padding: 0.5rem 0;
  font-size: 0.85rem;
  font-weight: 500;
}

.top-bar-content {
  display: flex;
  justify-content: flex-end;
}

.top-links {
  display: flex;
  gap: 1.5rem;
}

.top-links a {
  display: flex;
  align-items: center;
  gap: 0.4rem;
  color: var(--text-secondary);
}

.top-links a:hover {
  color: var(--primary-color);
}

/* Navigation */
.navbar {
  position: absolute;
  top: 36px; /* Below top-bar */
  left: 0;
  width: 100%;
  z-index: 1000;
  padding: 1rem 0;
  transition: var(--transition);
  background: white;
  border-bottom: 1px solid rgba(0,0,0,0.05);
}

.navbar.scrolled {
  position: fixed;
  top: 0;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  box-shadow: var(--shadow-sm);
}

.nav-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: var(--primary-color);
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.logo-img {
  height: 75px;
  width: auto;
}

.nav-links {
  display: flex;
  align-items: center;
  gap: 2rem;
}

.nav-links a:not(.btn) {
  font-weight: 500;
  position: relative;
}

.nav-links a:not(.btn)::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--secondary-color);
  transition: var(--transition);
}

.nav-links a:not(.btn):hover::after {
  width: 100%;
}

.lang-switch {
  background: var(--bg-color);
  border: 1px solid var(--primary-light);
  color: var(--primary-color);
  padding: 0.4rem 1rem;
  border-radius: 99px;
  cursor: pointer;
  font-weight: 600;
  transition: var(--transition);
}

.lang-switch:hover {
  background: var(--primary-color);
  color: white;
}

.nav-btn {
  padding: 0.8rem 2rem;
  font-size: 1.1rem;
  font-weight: 700;
  box-shadow: 0 4px 15px rgba(0, 112, 243, 0.4);
  animation: pulse-glow 2s infinite;
}

.nav-insta-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: linear-gradient(45deg, #f09433 0%, #e6683c 25%, #dc2743 50%, #cc2366 75%, #bc1888 100%);
  color: white;
  transition: var(--transition);
  flex-shrink: 0;
}

.nav-insta-btn:hover {
  transform: scale(1.1);
  box-shadow: 0 6px 20px rgba(220, 39, 67, 0.4);
}

/* Hero Section */
.hero {
  height: 100vh;
  position: relative;
  display: flex;
  align-items: center;
  overflow: hidden;
}

.hero-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url('../assets/hero.png');
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
  z-index: 1;
}

.hero-bg::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, rgba(4, 30, 66, 0.9) 0%, rgba(4, 30, 66, 0.4) 100%);
}

.hero-content {
  position: relative;
  z-index: 2;
  width: 100%;
}

.hero-card {
  max-width: 650px;
  padding: 3.5rem;
  animation: float 6s ease-in-out infinite;
}

.hero-card h1 {
  font-size: 3.5rem;
  margin-bottom: 1.5rem;
  line-height: 1.1;
}

.subtitle {
  font-size: 1.2rem;
  color: var(--text-secondary);
  margin-bottom: 2.5rem;
  font-weight: 500;
}

.hero-badges {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  margin-bottom: 2.5rem;
}

.badge {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  background: rgba(0, 112, 243, 0.1);
  color: var(--accent-color);
  padding: 0.6rem 1.2rem;
  border-radius: 99px;
  font-weight: 600;
  font-size: 0.95rem;
  width: fit-content;
}

.mr-2 {
  margin-right: 0.5rem;
}

/* Skipper Section */
.skipper-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.skipper-subtitle {
  font-size: 1.8rem;
  margin-bottom: 1.5rem;
}

.skipper-desc {
  font-size: 1.1rem;
  color: var(--text-secondary);
  margin-bottom: 1.5rem;
}

.skipper-bullets {
  margin-top: 2rem;
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.skipper-bullets li {
  display: flex;
  align-items: center;
  gap: 1rem;
  font-size: 1.1rem;
  font-weight: 500;
  color: var(--primary-color);
}

.check-icon {
  color: #10B981;
}

.skipper-placeholder {
  height: 400px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 1rem;
  color: var(--text-secondary);
  font-weight: 600;
  background: linear-gradient(135deg, rgba(255,255,255,0.8), rgba(255,255,255,0.4));
}

.text-primary {
  color: var(--primary-color);
}

.opacity-50 {
  opacity: 0.5;
}

/* Sections */
.section-light {
  background: var(--bg-color);
  color: var(--text-primary);
}

.section-dark {
  background: var(--primary-color);
  color: white;
}

.text-white {
  color: white !important;
}

.text-white-opacity {
  color: rgba(255, 255, 255, 0.8) !important;
}

.dark-card-text {
  color: var(--text-primary) !important;
}

.dark-card-text h3, .dark-card-text .price, .dark-card-text p {
  color: var(--text-primary) !important;
}

.dark-card-text .price-low, .dark-card-text .pricing-subtitle {
  color: var(--text-secondary) !important;
}

.boat-desc {
  text-align: center;
  color: rgba(255, 255, 255, 0.8);
  max-width: 800px;
  margin: 0 auto 3rem;
  font-size: 1.2rem;
  line-height: 1.6;
}

.boat-stats-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1.5rem;
  margin-bottom: 4rem;
}

.stat-card {
  padding: 1.5rem;
  display: flex;
  align-items: center;
  gap: 1.5rem;
  transition: var(--transition);
}

.stat-card:hover {
  background: rgba(255, 255, 255, 0.1);
  transform: translateY(-5px);
  border-color: rgba(0, 229, 255, 0.4);
}

.stat-icon {
  background: linear-gradient(135deg, var(--secondary-color), var(--accent-color));
  width: 50px;
  height: 50px;
  border-radius: 1rem;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  box-shadow: 0 4px 15px rgba(0, 229, 255, 0.3);
}

.stat-info {
  display: flex;
  flex-direction: column;
}

.stat-value {
  font-size: 1.4rem;
  font-weight: 800;
  color: white;
  margin-bottom: 0.2rem;
}

.stat-label {
  font-size: 0.85rem;
  color: rgba(255, 255, 255, 0.7);
  text-transform: uppercase;
  letter-spacing: 1px;
}

/* Features */
.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.feature {
  padding: 2.5rem;
  transition: var(--transition);
}

.glass-dark {
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(16px);
  -webkit-backdrop-filter: blur(16px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 1.5rem;
}

.feature:hover {
  transform: translateY(-10px);
  background: rgba(255, 255, 255, 0.1);
}

.icon-wrapper {
  width: 70px;
  height: 70px;
  background: linear-gradient(135deg, var(--secondary-color), var(--accent-color));
  color: white;
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 2rem;
  box-shadow: 0 10px 20px rgba(0, 229, 255, 0.3);
}

.icon-wrapper svg {
  width: 32px;
  height: 32px;
}

.feature h3 {
  margin-bottom: 1rem;
  font-size: 1.4rem;
  color: white;
}

.feature p {
  color: rgba(255,255,255,0.8);
}

/* Itineraries */
.itineraries-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
}

.itinerary-card {
  background: white;
  border-radius: 1.5rem;
  padding: 2.5rem;
  box-shadow: var(--shadow-sm);
  transition: var(--transition);
  text-align: center;
}

.itinerary-card:hover {
  transform: translateY(-10px);
  box-shadow: var(--shadow-md);
}

.itinerary-icon {
  width: 80px;
  height: 80px;
  background: rgba(0, 112, 243, 0.05);
  color: var(--accent-color);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1.5rem;
  transition: var(--transition);
}

.itinerary-card:hover .itinerary-icon {
  background: var(--accent-color);
  color: white;
  transform: scale(1.1) rotate(5deg);
}

.itinerary-card h3 {
  font-size: 1.4rem;
  margin-bottom: 1rem;
}

.itinerary-card p {
  color: var(--text-secondary);
}

/* Pricing */
.pricing-subtitle {
  text-align: center;
  max-width: 700px;
  margin: 0 auto 4rem;
  color: var(--text-secondary);
  font-size: 1.15rem;
  white-space: pre-line;
}

.pricing-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
  align-items: end;
}

/* Base card */
.pricing-card {
  background: white;
  border-radius: 1.5rem;
  padding: 2.5rem 2rem;
  box-shadow: 0 4px 20px rgba(10, 37, 64, 0.1);
  position: relative;
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  border: 1px solid rgba(10, 37, 64, 0.07);
  transition: var(--transition);
}

.pricing-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 12px 40px rgba(10, 37, 64, 0.15);
}

/* Featured (Journée Entière) */
.pricing-card--featured {
  background: linear-gradient(160deg, var(--primary-color) 0%, var(--primary-light) 100%);
  border: none;
  transform: scale(1.04);
  box-shadow: 0 16px 50px rgba(10, 37, 64, 0.35);
  color: white;
}

.pricing-card--featured:hover {
  transform: scale(1.04) translateY(-6px);
}

.pricing-card--featured .card-label,
.pricing-card--featured .card-time,
.pricing-card--featured .season-label {
  color: rgba(255,255,255,0.75);
}

.pricing-card--featured .season-amount {
  color: white;
}

.pricing-card--featured .season-divider {
  border-color: rgba(255,255,255,0.15);
}

.pricing-card--featured .card-badge {
  border-color: rgba(255,255,255,0.2);
  color: rgba(255,255,255,0.9);
}

/* Sunset card */
.pricing-card--sunset {
  background: linear-gradient(160deg, #e8f4fd 0%, #dbeeff 100%);
  border-color: rgba(0, 133, 255, 0.15);
}

/* Featured tag */
.featured-tag {
  position: absolute;
  top: -16px;
  left: 50%;
  transform: translateX(-50%);
  background: var(--secondary-color);
  color: white;
  padding: 0.35rem 1.5rem;
  border-radius: 99px;
  font-weight: 800;
  font-size: 0.8rem;
  text-transform: uppercase;
  letter-spacing: 1px;
  box-shadow: 0 4px 12px rgba(0, 180, 216, 0.4);
}

/* Card content */
.card-label {
  font-size: 1.6rem;
  font-weight: 800;
  color: var(--primary-color);
  font-family: var(--font-heading);
}

.card-time {
  font-size: 0.95rem;
  color: var(--text-secondary);
  font-weight: 500;
  margin-top: -0.75rem;
}

.card-prices {
  display: flex;
  flex-direction: column;
  gap: 0;
}

.season-price {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0.9rem 0;
}

.season-divider {
  border-top: 1px dashed rgba(10, 37, 64, 0.12);
}

.season-label {
  font-size: 0.95rem;
  color: var(--text-secondary);
  font-weight: 500;
}

.season-amount {
  font-size: 1.8rem;
  font-weight: 800;
  color: var(--primary-color);
  font-family: var(--font-heading);
}

.season-amount--low {
  font-size: 1.4rem;
  color: var(--primary-light);
}

.season-amount--sunset {
  color: var(--accent-color);
}

.card-badge {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 1rem;
  font-weight: 800;
  color: #059669;
  border: 2px solid #10B98150;
  background: #10B98115;
  padding: 0.5rem 1.1rem;
  border-radius: 99px;
  align-self: flex-start;
  letter-spacing: 0.5px;
}

/* Steps Section */
.steps-container {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  max-width: 900px;
  margin: 0 auto;
  position: relative;
}

.step-box {
  flex: 1;
  text-align: center;
  position: relative;
  z-index: 2;
  padding: 0 1rem;
}

.step-number {
  width: 60px;
  height: 60px;
  background: linear-gradient(135deg, var(--secondary-color), var(--accent-color));
  color: white;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  font-weight: 800;
  margin: 0 auto 1.5rem;
  box-shadow: 0 10px 20px rgba(0, 229, 255, 0.3);
}

.step-box h3 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
}

.step-box p {
  font-size: 1.1rem;
  line-height: 1.7;
  color: var(--text-secondary);
}

.step-connector {
  flex: 0.5;
  height: 2px;
  background: rgba(0, 112, 243, 0.2);
  margin-top: 30px;
}

/* Testimonials Section */
.testimonials-bg {
  background: url('../assets/hero.png') center/cover fixed;
  position: relative;
}
.testimonials-bg::before {
  content: '';
  position: absolute;
  top: 0; left: 0; width: 100%; height: 100%;
  background: rgba(4, 30, 66, 0.9);
}
.testimonials-bg .container {
  position: relative;
  z-index: 2;
}

.testimonials-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 2rem;
}

.testimonial-card {
  padding: 2.5rem;
  text-align: center;
}

.stars {
  color: #FBBF24;
  font-size: 1.5rem;
  margin-bottom: 1rem;
  letter-spacing: 2px;
}

.review {
  font-size: 1.1rem;
  font-style: italic;
  margin-bottom: 1.5rem;
  line-height: 1.8;
}

.name {
  font-weight: 600;
  color: var(--secondary-color);
}

/* FAQ Section */
.faq-container {
  max-width: 800px;
  margin: 0 auto;
}

.faq-item {
  background: white;
  border-radius: 1rem;
  margin-bottom: 1rem;
  box-shadow: var(--shadow-sm);
  overflow: hidden;
  cursor: pointer;
  transition: var(--transition);
}

.faq-item:hover {
  box-shadow: var(--shadow-md);
}

.faq-question {
  padding: 1.5rem 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.faq-question h3 {
  font-size: 1.2rem;
  margin: 0;
  color: var(--text-primary);
  font-weight: 700;
}

.faq-icon {
  color: var(--accent-color);
  flex-shrink: 0;
  margin-left: 1rem;
  transition: transform 0.3s ease;
}

.faq-item.active .faq-icon {
  transform: rotate(180deg);
}

.faq-answer {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.4s ease;
  background: var(--bg-color);
}

.faq-item.active .faq-answer {
  max-height: 300px;
}

.faq-answer p {
  padding: 1rem 2rem 1.8rem;
  color: var(--text-secondary);
  margin: 0;
  font-size: 1.05rem;
  line-height: 1.7;
  border-top: 1px solid rgba(10,37,64,0.07);
}

/* Location Section */
.location-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 3rem;
  align-items: stretch;
}

.location-card {
  padding: 3rem;
  border-radius: 1.5rem;
  height: 100%;
}

.glass-light {
  background: white;
  box-shadow: var(--shadow-md);
  border: 1px solid rgba(0,0,0,0.05);
}

.text-accent {
  color: var(--accent-color);
}

.text-xl {
  font-size: 1.5rem;
}

.font-bold {
  font-weight: 700;
}

.font-semibold {
  font-weight: 600;
}

.mb-2 {
  margin-bottom: 0.5rem;
}

.mb-4 {
  margin-bottom: 1rem;
}

.mb-6 {
  margin-bottom: 1.5rem;
}

.text-sm {
  font-size: 0.95rem;
}

.text-secondary {
  color: var(--text-secondary);
}

.flex {
  display: flex;
}

.items-center {
  align-items: center;
}

.gap-4 {
  gap: 1rem;
}

.location-card-header {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1rem;
}

.location-card-header h3 {
  font-size: 1.5rem;
  font-weight: 700;
  margin: 0;
}

.location-desc {
  margin-bottom: 1.5rem;
  font-size: 1.1rem;
  line-height: 1.5;
}

.location-card h4 {
  font-weight: 600;
  margin-bottom: 0.5rem;
}

.location-list {
  font-size: 0.95rem;
  color: var(--text-secondary);
}

.map-container {
  border-radius: 1.5rem;
  overflow: hidden;
  box-shadow: var(--shadow-md);
  min-height: 400px;
}

/* Contact CTA */
.contact-cta {
  background: url('../assets/hero.png') center/cover fixed;
  position: relative;
}

.contact-cta::before {
  content: '';
  position: absolute;
  top: 0; left: 0; width: 100%; height: 100%;
  background: rgba(4, 30, 66, 0.85);
}

.cta-box {
  position: relative;
  z-index: 2;
  max-width: 800px;
  margin: 0 auto;
  text-align: center;
  padding: 5rem 3rem;
}

.cta-box h2 {
  font-size: 3.5rem;
  margin-bottom: 1.5rem;
}

.cta-box p {
  font-size: 1.3rem;
  color: var(--text-secondary);
  margin-bottom: 3rem;
}

.cta-buttons {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  align-items: center;
}

.cta-main-btn {
  font-size: 1.4rem;
  padding: 1.5rem 3rem;
  width: 100%;
  max-width: 500px;
  animation: pulse-glow 2s infinite;
}

.btn-whatsapp {
  background-color: #25D366;
  color: white;
  width: 100%;
  max-width: 500px;
  font-size: 1.2rem;
  padding: 1rem 2rem;
  box-shadow: 0 10px 20px rgba(37, 211, 102, 0.3);
}

.btn-whatsapp:hover {
  background-color: #128C7E;
  transform: translateY(-3px);
  box-shadow: 0 15px 25px rgba(37, 211, 102, 0.4);
}

/* Social */
.social-btn {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  background: linear-gradient(45deg, #f09433 0%, #e6683c 25%, #dc2743 50%, #cc2366 75%, #bc1888 100%);
  color: white;
  border: none;
  font-size: 1.2rem;
  padding: 1rem 2rem;
  font-weight: 600;
  border-radius: 99px;
  transition: transform 0.3s;
}

.social-btn:hover {
  transform: scale(1.05);
  color: white;
}

/* Footer */
footer {
  background: #020F24;
  color: white;
  text-align: center;
  padding: 3rem 0;
  font-size: 1.1rem;
}

/* Gallery Section */
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
}

.gallery-item {
  aspect-ratio: 4/3;
  border-radius: 1rem;
  overflow: hidden;
  box-shadow: var(--shadow-sm);
  background: white;
}

.gallery-placeholder {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background: linear-gradient(135deg, rgba(0, 112, 243, 0.05), rgba(0, 229, 255, 0.05));
  color: var(--text-secondary);
  font-weight: 500;
  transition: var(--transition);
}

.gallery-placeholder:hover {
  background: linear-gradient(135deg, rgba(0, 112, 243, 0.1), rgba(0, 229, 255, 0.1));
  transform: scale(1.05);
}

/* Footer & Legal */
.footer-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
}

.legal-link {
  background: none;
  border: none;
  color: rgba(255,255,255,0.6);
  cursor: pointer;
  text-decoration: underline;
  font-size: 0.9rem;
}
.legal-link:hover {
  color: white;
}

/* Modal */
.modal-backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  backdrop-filter: blur(5px);
  z-index: 2000;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 1rem;
}

.modal-content {
  background: white;
  border-radius: 1.5rem;
  padding: 2.5rem;
  max-width: 600px;
  width: 100%;
  box-shadow: var(--shadow-lg);
  color: var(--text-primary);
  text-align: left;
}

.modal-content h2 {
  font-size: 1.8rem;
  margin-bottom: 1.5rem;
  color: var(--primary-color);
}

.modal-body {
  margin-bottom: 2rem;
  line-height: 1.6;
  color: var(--text-secondary);
}

.modal-body p {
  margin-bottom: 1rem;
}

@media (max-width: 992px) {
  .skipper-container,
  .location-container {
    grid-template-columns: 1fr;
  }
}

@media (max-width: 768px) {
  .nav-links {
    display: none;
  }
  
  .hero-card h1 {
    font-size: 2.5rem;
  }
  
  .pricing-card.featured {
    transform: scale(1);
  }
  
  .pricing-card.featured:hover {
    transform: translateY(-10px);
  }
  
  .cta-box h2 {
    font-size: 2.5rem;
  }
  
  .map-container {
    min-height: 300px;
  }

  .steps-container {
    flex-direction: column;
    align-items: center;
    gap: 2rem;
  }

  .step-connector {
    display: none;
  }
}
</style>
