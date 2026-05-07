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
          <a href="#skipper">{{ t('nav.skipper') }}</a>
          <a href="#features">{{ t('nav.features') }}</a>
          <a href="#pricing">{{ t('nav.pricing') }}</a>
          <button class="lang-switch" @click="toggleLocale">
            {{ locale === 'fr' ? 'EN' : 'FR' }}
          </button>
          <a href="tel:+33612345678" class="btn btn-primary nav-btn">{{ t('nav.book') }}</a>
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
          <a href="tel:+33612345678" class="btn btn-primary cta-btn">
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

    <!-- Features -->
    <section id="features" class="section-dark">
      <div class="container">
        <h2 class="section-title text-white">{{ t('features.title') }}</h2>
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
            <div class="popular-tag">Idéal</div>
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

          <!-- Sunset -->
          <div class="pricing-card sunset-card">
            <div class="card-header">
              <h3>{{ t('pricing.sunset') }}</h3>
              <p>{{ t('pricing.sunset_time') }}</p>
            </div>
            <div class="card-body">
              <p class="text-center mb-4">{{ t('pricing.sunset_desc') }}</p>
              <div class="price-row">
                <span class="price sunset-price">{{ t('pricing.sunset_price') }}</span>
              </div>
            </div>
            <div class="card-footer">
              <a href="tel:+33612345678" class="btn btn-secondary w-full">Sur mesure</a>
            </div>
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
            <a href="tel:+33612345678" class="btn btn-primary cta-main-btn">
              <PhoneIcon size="24" class="mr-2" /> {{ t('contact.call_now') }} (+33 6 12 34 56 78)
            </a>
            <a href="https://wa.me/33612345678" target="_blank" class="btn btn-whatsapp">
              <MessageCircleIcon size="24" class="mr-2" /> {{ t('contact.whatsapp') }}
            </a>
          </div>
        </div>
      </div>
    </section>

    <footer>
      <div class="container">
        <p>&copy; 2026 LocBateau - Thibault. {{ t('footer.rights') }}</p>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { useI18n } from 'vue-i18n'
import { 
  AnchorIcon, MapPinIcon, CarIcon, UserIcon, CheckCircleIcon,
  SunIcon, UtensilsIcon, WavesIcon, MusicIcon, BedIcon, DropletIcon,
  ShieldCheckIcon, PhoneIcon, MessageCircleIcon 
} from 'lucide-vue-next'

const { t, locale } = useI18n()
const isScrolled = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const toggleLocale = () => {
  locale.value = locale.value === 'fr' ? 'en' : 'fr'
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
  background: rgba(4, 30, 66, 0.95);
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
  font-size: 1.8rem;
  font-weight: 800;
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
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.3);
  color: white;
  padding: 0.4rem 1rem;
  border-radius: 99px;
  cursor: pointer;
  font-weight: 600;
  transition: var(--transition);
}

.lang-switch:hover {
  background: white;
  color: var(--primary-color);
}

.nav-btn {
  padding: 0.5rem 1.5rem;
  font-size: 0.9rem;
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
}

.section-dark {
  background: var(--primary-color);
  color: white;
}

.text-white {
  color: white !important;
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

/* Pricing */
.pricing-subtitle {
  text-align: center;
  max-width: 700px;
  margin: 0 auto 4rem;
  color: var(--text-secondary);
  font-size: 1.15rem;
}

.pricing-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 2.5rem;
  align-items: stretch;
}

.pricing-card {
  background: white;
  border-radius: 2rem;
  padding: 3.5rem 2.5rem;
  box-shadow: var(--shadow-md);
  position: relative;
  transition: var(--transition);
  display: flex;
  flex-direction: column;
}

.pricing-card:hover {
  transform: translateY(-15px);
  box-shadow: var(--shadow-hover);
}

.pricing-card.featured {
  background: linear-gradient(180deg, var(--primary-color) 0%, var(--primary-light) 100%);
  color: white;
  transform: scale(1.05);
  box-shadow: var(--shadow-lg);
}

.pricing-card.featured:hover {
  transform: scale(1.05) translateY(-10px);
}

.pricing-card.featured h3, 
.pricing-card.featured .price {
  color: white;
}

.sunset-card {
  background: linear-gradient(135deg, #FFF5E1 0%, #FFE4E1 100%);
}

.sunset-card h3 {
  color: #FF7F50;
}

.popular-tag {
  position: absolute;
  top: -15px;
  left: 50%;
  transform: translateX(-50%);
  background: linear-gradient(90deg, var(--secondary-color), var(--accent-color));
  color: white;
  padding: 0.5rem 2rem;
  border-radius: 99px;
  font-weight: 800;
  font-size: 0.95rem;
  text-transform: uppercase;
  box-shadow: 0 4px 10px rgba(0, 229, 255, 0.4);
}

.card-header {
  text-align: center;
  margin-bottom: 2.5rem;
  padding-bottom: 2rem;
  border-bottom: 2px dashed rgba(0,0,0,0.1);
}

.pricing-card.featured .card-header {
  border-bottom: 2px dashed rgba(255,255,255,0.2);
}

.card-header h3 {
  font-size: 2.2rem;
  margin-bottom: 0.5rem;
}

.price-row {
  text-align: center;
  margin-bottom: 1.5rem;
}

.price {
  font-size: 2.8rem;
  font-weight: 800;
  color: var(--primary-color);
}

.price-low {
  font-size: 1.3rem;
  color: var(--text-secondary);
  font-weight: 500;
}

.pricing-card.featured .price-low {
  color: rgba(255,255,255,0.8);
}

.sunset-price {
  font-size: 2rem;
  background: linear-gradient(90deg, #FF7F50, #FF4500);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.card-body {
  flex-grow: 1;
}

.card-footer {
  margin-top: 3rem;
  text-align: center;
}

.no-deposit {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  font-weight: 700;
  color: #10B981;
  font-size: 1.1rem;
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

/* Footer */
footer {
  background: #020F24;
  color: white;
  text-align: center;
  padding: 3rem 0;
  font-size: 1.1rem;
}

@media (max-width: 992px) {
  .skipper-container {
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
}
</style>
