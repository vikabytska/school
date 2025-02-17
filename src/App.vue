<template>
  <div id="app">
    <header>
      <nav class="navbar navbar-expand-lg">
        <a class="navbar-brand" href="#">EduLearn</a>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav">
            <li class="nav-item">
              <router-link to="/">Головна</router-link>
            </li>
            <li class="nav-item">
              <router-link to="/courses">Курси</router-link>
            </li>
            <li class="nav-item">
              <router-link to="/mycourses">Мої курси</router-link>
            </li>
          </ul>
        </div>
      </nav>
    </header>

    <main>
      <RouterView />
    </main>

    <!-- Site footer -->
    <footer class="site-footer">
      <div class="container">
        <div class="row">
          <div class="col-sm-12 col-md-6">
            <h6>EduLearn</h6>
            <p class="text-justify">
              EduLearn — це сучасна платформа дистанційної освіти, що пропонує широкий вибір курсів для професійного та особистісного розвитку. Ми створюємо можливості для навчання будь-де та будь-коли.
            </p>
            <p>Приєднуйтесь до EduLearn та відкривайте нові горизонти знань!</p>
          </div>

          <div class="col-xs-6 col-md-3">
            <h6>Навігація</h6>
            <ul class="footer-links">
              <li><router-link to="/">Головна</router-link></li>
              <li><router-link to="/courses">Курси</router-link></li>
              <li><router-link to="/mycourses">Мої курси</router-link></li>
            </ul>
          </div>

          <div class="col-xs-6 col-md-3">
            <h6>Контактна інформація</h6>
            <ul class="footer-links">
              <li>Адреса: м. Київ, вул. Освітянська, 25</li>
              <li>Телефон: <a href="#"> +380 (44) 987-65-43</a></li>
              <li>Email: <a href="mailto:info@edulearn.com">info@edulearn.com</a></li>
            </ul>
          </div>
        </div>
        <hr>
      </div>
      <div class="container">
        <div class="row">
          <div class="col-12">
            <p class="copyright-text">EduLearn &copy; 2024 ; Всі права захищено</p>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>


<script setup>
import { useRouter } from 'vue-router';
import { useCoursesStore } from "@/stores/courses";

// Використовуємо useRouter для отримання доступу до router
const router = useRouter();
const coursesStore = useCoursesStore();
</script>

<style>

/* Основна структура */
#app {
  height: 100vh;
  display: flex;
  flex-direction: column;
  font-family: "Manrope", sans-serif;
}

header {
  flex-shrink: 0;
  margin-bottom: 10px;
}

main {
  flex-grow: 1; 
  margin-bottom: 50px;
}

/* Навбар */
.navbar {
  background-color: #29542b; 
  padding: 15px 20px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  height: 50px;
}

.navbar-brand {
  font-size: 1.5rem;
  font-weight: bold;
  color: #ffffff;
  text-decoration: none;
  transition: color 0.3s ease;
}

.navbar-brand:hover {
  color: #d4ffd8;
}

.navbar-nav {
  display: flex;
  align-items: center;
  gap: 20px;
  margin: 0;
  list-style: none;
}

.nav-item a, 
.nav-item router-link {
  font-size: 1rem;
  color: #ffffff;
  text-decoration: none;
  font-weight: 500;
  padding: 10px 15px;
  border-radius: 6px;
  transition: background-color 0.3s ease, color 0.3s ease;
}

.nav-item a:hover, 
.nav-item router-link:hover {
  background-color: #d4ffd8; 
  color: #29542b; 
}

.nav-item a.router-link-active, 
.nav-item router-link.router-link-active {
  background-color: #ffffff; 
  color: #29542b; 
  font-weight: bold;
}

.navbar-toggler {
  border: none;
  background-color: transparent;
}

.navbar-toggler-icon {
  width: 30px;
  height: 3px;
  background-color: #ffffff;
  display: block;
  margin: 6px 0;
  transition: transform 0.3s ease;
}

.navbar-toggler:hover .navbar-toggler-icon {
  transform: scale(1.1);
}



.site-footer {
  background-color: #29542b; 
  padding: 45px 20px;
  flex-shrink: 0;
  color: #ffffff; 
  font-size: 15px;
  line-height: 1.6;
  height: 290px;
}

.site-footer hr {
  border-top-color: #ffffff;
  opacity: 0.2; 
}

.site-footer h6 {
  color: #ffffff;
  font-size: 18px;
  font-weight: bold;
  margin-bottom: 15px;
}

.site-footer a {
  color: #ffffff; 
  text-decoration: none;
  transition: color 0.3s ease;
}

.site-footer a:hover {
  color: #d4ffd8; 
  text-decoration: underline;
}

.footer-links {
  padding-left: 0;
  list-style: none;
}

.footer-links li {
  margin-bottom: 10px;
}

.footer-links a {
  font-size: 14px;
}

.copyright-text {
  margin: 0;
  font-size: 14px;
  text-align: center;
  color: #d4ffd8; 
}

/* Адаптивність футера */
@media (max-width: 991px) {
  .site-footer [class^="col-"] {
    margin-bottom: 30px;
  }
}

@media (max-width: 767px) {
  .site-footer {
    text-align: center;
  }
  .footer-links {
    text-align: center; 
  }
  .footer-links li {
    display: inline-block; 
    margin-right: 15px;
  }
}

</style>
