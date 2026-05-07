<template>
  <div>
    <!-- Navigation -->
    <nav :class="['navbar', { 'scrolled': isScrolled }]">
      <div class="container nav-content">
        <div class="logo">
          <AnchorIcon class="logo-icon" />
          <span>LocBateau</span>
        </div>
        <div class="nav-links">
          <a href="#features">{{ t('nav.features') }}</a>
          <a href="#pricing">{{ t('nav.pricing') }}</a>
          <a href="#contact">{{ t('nav.contact') }}</a>
          <button class="lang-switch" @click="toggleLocale">
            {{ locale === 'fr' ? 'EN' : 'FR' }}
          </button>
        </div>
      </div>
    </nav>

    <!-- Hero Section -->
    <header class="hero">
      <div class="hero-bg"></div>
      <div class="container hero-content">
        <div class="glass hero-card">
          <h1>{{ t('hero.title') }}</h1>
          <p class="subtitle">{{ t('hero.subtitle') }}</p>
          <div class="hero-badges">
            <span class="badge"><MapPinIcon size="16" /> {{ t('hero.location') }}</span>
            <span class="badge"><CarIcon size="16" /> {{ t('hero.parking') }}</span>
          </div>
          <a href="#contact" class="btn btn-primary cta-btn">
            {{ t('hero.cta') }}
          </a>
        </div>
      </div>
    </header>

    <!-- Destinations -->
    <section id="destinations" class="section-light">
      <div class="container">
        <h2 class="section-title">{{ t('destinations.title') }}</h2>
        <div class="destinations-grid">
          <div class="dest-card">
            <PalmtreeIcon size="40" class="dest-icon" />
            <h3>{{ t('destinations.porquerolles') }}</h3>
          </div>
          <div class="dest-card">
            <CompassIcon size="40" class="dest-icon" />
            <h3>{{ t('destinations.giens') }}</h3>
          </div>
          <div class="dest-card">
            <WavesIcon size="40" class="dest-icon" />
            <h3>{{ t('destinations.turquoise') }}</h3>
          </div>
        </div>
      </div>
    </section>

    <!-- Features -->
    <section id="features" class="section-dark">
      <div class="container">
        <h2 class="section-title">{{ t('features.title') }}</h2>
        <div class="features-grid">
          <div class="feature">
            <div class="icon-wrapper"><SunIcon /></div>
            <h3>{{ t('features.sunbed') }}</h3>
            <p>{{ t('features.sunbed_desc') }}</p>
          </div>
          <div class="feature">
            <div class="icon-wrapper"><UtensilsIcon /></div>
            <h3>{{ t('features.dining') }}</h3>
            <p>{{ t('features.dining_desc') }}</p>
          </div>
          <div class="feature">
            <div class="icon-wrapper"><FishIcon /></div>
            <h3>{{ t('features.snorkeling') }}</h3>
            <p>{{ t('features.snorkeling_desc') }}</p>
          </div>
          <div class="feature">
            <div class="icon-wrapper"><BedIcon /></div>
            <h3>{{ t('features.cabin') }}</h3>
            <p>{{ t('features.cabin_desc') }}</p>
          </div>
          <div class="feature">
            <div class="icon-wrapper"><DropletIcon /></div>
            <h3>{{ t('features.shower') }}</h3>
            <p>{{ t('features.shower_desc') }}</p>
          </div>
          <div class="feature">
            <div class="icon-wrapper"><GaugeIcon /></div>
            <h3>{{ t('features.engine') }}</h3>
            <p>{{ t('features.engine_desc') }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Pricing Section -->
    <section id="pricing" class="section-light">
      <div class="container">
        <h2 class="section-title">{{ t('pricing.title') }}</h2>
        <p class="pricing-subtitle">{{ t('pricing.subtitle') }}</p>
        
        <div class="pricing-cards">
          <!-- Half Day -->
          <div class="pricing-card">
            <div class="card-header">
              <h3>{{ t('pricing.half_day') }}</h3>
              <p>{{ t('pricing.half_day_time') }}</p>
            </div>
            <div class="card-body">
              <div class="price-row">
                <span class="price">{{ t('pricing.half_day_high') }}</span>
              </div>
              <div class="price-row">
                <span class="price-low">{{ t('pricing.half_day_low') }}</span>
              </div>
            </div>
            <div class="card-footer">
              <span class="no-deposit"><ShieldCheckIcon size="16"/> {{ t('pricing.no_deposit') }}</span>
            </div>
          </div>

          <!-- Full Day -->
          <div class="pricing-card featured">
            <div class="popular-tag">Popular</div>
            <div class="card-header">
              <h3>{{ t('pricing.full_day') }}</h3>
              <p>{{ t('pricing.full_day_time') }}</p>
            </div>
            <div class="card-body">
              <div class="price-row">
                <span class="price">{{ t('pricing.full_day_high') }}</span>
              </div>
              <div class="price-row">
                <span class="price-low">{{ t('pricing.full_day_low') }}</span>
              </div>
            </div>
            <div class="card-footer">
              <span class="no-deposit"><ShieldCheckIcon size="16"/> {{ t('pricing.no_deposit') }}</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="section-dark">
      <div class="container contact-container">
        <div class="contact-info">
          <h2 class="section-title" style="text-align: left;">{{ t('contact.title') }}</h2>
          <p>{{ t('contact.desc') }}</p>
          
          <div class="contact-methods">
            <div class="method">
              <PhoneIcon class="method-icon" />
              <div>
                <strong>{{ t('contact.phone') }}</strong>
                <p>+33 6 12 34 56 78</p>
              </div>
            </div>
            <div class="method">
              <MailIcon class="method-icon" />
              <div>
                <strong>{{ t('contact.email') }}</strong>
                <p>contact@locbateau.fr</p>
              </div>
            </div>
          </div>
        </div>
        
        <form class="glass contact-form" @submit.prevent="submitForm">
          <div class="form-group">
            <input type="text" placeholder="Nom / Name" required />
          </div>
          <div class="form-group">
            <input type="email" placeholder="Email" required />
          </div>
          <div class="form-group">
            <textarea placeholder="Message" rows="4" required></textarea>
          </div>
          <button type="submit" class="btn btn-primary w-full">{{ t('contact.send') }}</button>
        </form>
      </div>
    </section>

    <footer>
      <div class="container">
        <p>&copy; 2026 LocBateau. {{ t('footer.rights') }}</p>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { useI18n } from 'vue-i18n'
import { 
  AnchorIcon, MapPinIcon, CarIcon, PalmtreeIcon, CompassIcon, WavesIcon,
  SunIcon, UtensilsIcon, FishIcon, BedIcon, DropletIcon, GaugeIcon,
  ShieldCheckIcon, PhoneIcon, MailIcon 
} from 'lucide-vue-next'

const { t, locale } = useI18n()
const isScrolled = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const toggleLocale = () => {
  locale.value = locale.value === 'fr' ? 'en' : 'fr'
}

const submitForm = () => {
  alert('Formulaire envoyé ! / Form sent!')
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
/* Navigation */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
  padding: 1.5rem 0;
  transition: var(--transition);
}

.navbar.scrolled {
  background: rgba(10, 37, 64, 0.95);
  backdrop-filter: blur(10px);
  padding: 1rem 0;
  box-shadow: var(--shadow-md);
}

.nav-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  color: white;
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-family: var(--font-heading);
  font-size: 1.5rem;
  font-weight: 800;
}

.nav-links {
  display: flex;
  align-items: center;
  gap: 2rem;
}

.nav-links a {
  font-weight: 500;
  position: relative;
}

.nav-links a::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 0;
  height: 2px;
  background: var(--secondary-color);
  transition: var(--transition);
}

.nav-links a:hover::after {
  width: 100%;
}

.lang-switch {
  background: rgba(255, 255, 255, 0.2);
  border: 1px solid rgba(255, 255, 255, 0.4);
  color: white;
  padding: 0.25rem 0.75rem;
  border-radius: 99px;
  cursor: pointer;
  font-weight: 600;
  transition: var(--transition);
}

.lang-switch:hover {
  background: white;
  color: var(--primary-color);
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
  z-index: 1;
}

.hero-bg::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(to right, rgba(10, 37, 64, 0.8), rgba(10, 37, 64, 0.2));
}

.hero-content {
  position: relative;
  z-index: 2;
}

.hero-card {
  max-width: 600px;
  padding: 3rem;
}

.hero-card h1 {
  font-size: 3.5rem;
  margin-bottom: 1rem;
  color: var(--primary-color);
}

.subtitle {
  font-size: 1.1rem;
  color: var(--text-secondary);
  margin-bottom: 2rem;
}

.hero-badges {
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
  margin-bottom: 2rem;
}

.badge {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  background: rgba(0, 112, 243, 0.1);
  color: var(--accent-color);
  padding: 0.5rem 1rem;
  border-radius: 99px;
  font-weight: 600;
  font-size: 0.9rem;
  width: fit-content;
}

.cta-btn {
  font-size: 1.1rem;
  padding: 1rem 2rem;
}

/* Sections */
.section-light {
  background: white;
}

.section-dark {
  background: var(--bg-color);
}

/* Destinations */
.destinations-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.dest-card {
  text-align: center;
  padding: 2rem;
  background: white;
  border-radius: 1rem;
  box-shadow: var(--shadow-sm);
  transition: var(--transition);
}

.dest-card:hover {
  transform: translateY(-5px);
  box-shadow: var(--shadow-md);
}

.dest-icon {
  color: var(--secondary-color);
  margin-bottom: 1rem;
}

/* Features */
.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.feature {
  background: white;
  padding: 2rem;
  border-radius: 1rem;
  box-shadow: var(--shadow-sm);
  transition: var(--transition);
}

.feature:hover {
  transform: translateY(-5px);
  box-shadow: var(--shadow-md);
}

.icon-wrapper {
  width: 60px;
  height: 60px;
  background: rgba(0, 229, 255, 0.1);
  color: var(--secondary-color);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1.5rem;
}

.icon-wrapper svg {
  width: 30px;
  height: 30px;
}

.feature h3 {
  margin-bottom: 1rem;
  font-size: 1.25rem;
}

/* Pricing */
.pricing-subtitle {
  text-align: center;
  max-width: 600px;
  margin: 0 auto 3rem;
  color: var(--text-secondary);
  font-size: 1.1rem;
}

.pricing-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
  max-width: 900px;
  margin: 0 auto;
}

.pricing-card {
  background: white;
  border-radius: 1.5rem;
  padding: 3rem 2rem;
  box-shadow: var(--shadow-md);
  position: relative;
  transition: var(--transition);
}

.pricing-card:hover {
  transform: translateY(-10px);
  box-shadow: var(--shadow-xl);
}

.pricing-card.featured {
  background: var(--primary-color);
  color: white;
  transform: scale(1.05);
}

.pricing-card.featured:hover {
  transform: scale(1.05) translateY(-10px);
}

.pricing-card.featured h3, 
.pricing-card.featured .price {
  color: white;
}

.popular-tag {
  position: absolute;
  top: -15px;
  left: 50%;
  transform: translateX(-50%);
  background: var(--secondary-color);
  color: var(--primary-color);
  padding: 0.5rem 1.5rem;
  border-radius: 99px;
  font-weight: 700;
  font-size: 0.9rem;
  text-transform: uppercase;
}

.card-header {
  text-align: center;
  margin-bottom: 2rem;
  padding-bottom: 2rem;
  border-bottom: 1px solid rgba(0,0,0,0.1);
}

.pricing-card.featured .card-header {
  border-bottom: 1px solid rgba(255,255,255,0.2);
}

.card-header h3 {
  font-size: 2rem;
  margin-bottom: 0.5rem;
}

.price-row {
  text-align: center;
  margin-bottom: 1rem;
}

.price {
  font-size: 2.5rem;
  font-weight: 800;
  color: var(--primary-color);
}

.price-low {
  font-size: 1.25rem;
  color: var(--text-secondary);
}

.pricing-card.featured .price-low {
  color: rgba(255,255,255,0.8);
}

.card-footer {
  margin-top: 2rem;
  text-align: center;
}

.no-deposit {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  font-weight: 600;
  color: #10B981; /* Green */
}

/* Contact */
.contact-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.contact-info p {
  margin-bottom: 2rem;
  font-size: 1.1rem;
  color: var(--text-secondary);
}

.contact-methods {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.method {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.method-icon {
  color: var(--accent-color);
}

.contact-form {
  padding: 3rem;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 1rem;
  border: 1px solid rgba(0,0,0,0.1);
  border-radius: 0.5rem;
  font-family: inherit;
  font-size: 1rem;
  background: rgba(255,255,255,0.9);
  transition: var(--transition);
}

.form-group input:focus,
.form-group textarea:focus {
  outline: none;
  border-color: var(--accent-color);
  box-shadow: 0 0 0 3px rgba(0, 112, 243, 0.1);
}

.w-full {
  width: 100%;
}

/* Footer */
footer {
  background: var(--primary-color);
  color: white;
  text-align: center;
  padding: 2rem 0;
}

@media (max-width: 768px) {
  .nav-links {
    display: none;
  }
  
  .hero-card h1 {
    font-size: 2.5rem;
  }
  
  .contact-container {
    grid-template-columns: 1fr;
  }
  
  .pricing-card.featured {
    transform: scale(1);
  }
  
  .pricing-card.featured:hover {
    transform: translateY(-10px);
  }
}
</style>
