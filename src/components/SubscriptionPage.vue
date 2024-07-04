<script>
export default {
  name: "SubscriptionPage",
  data() {
    return {
      plans: [
        { id: 1, name: 'Базовый', description: 'Доступ ко всем основным функциям сервиса, включая стандартное хранилище данных и базовую поддержку.', price: 100, duration: '1 месяц' },
        { id: 2, name: 'Стандарт', description: 'Включает все функции базового пакета, а также увеличенное хранилище данных и приоритетную поддержку.', price: 200, duration: '3 месяца' },
        { id: 3, name: 'Премиум', description: 'Включает все функции стандартного пакета, а также дополнительные инструменты аналитики и расширенные настройки безопасности.', price: 300, duration: '6 месяцев' },
        { id: 4, name: 'Ультра', description: 'Максимальный пакет услуг, включающий все функции премиум пакета, индивидуальные консультации и персонализированные решения.', price: 400, duration: '1 год' },
      ],
      addons: [
        { id: 1, name: 'Расширенное хранилище', description: 'Увеличьте объем доступного хранилища для ваших данных.', price: 50, duration: '1 месяц' },
        { id: 2, name: 'Продвинутая аналитика', description: 'Доступ к дополнительным инструментам аналитики для более глубокого анализа данных.', price: 75, duration: '3 месяца' },
        { id: 3, name: 'Приоритетная поддержка', description: 'Быстрая помощь от нашей команды поддержки 24/7.', price: 100, duration: '6 месяцев' },
        { id: 4, name: 'Персональные консультации', description: 'Индивидуальные сессии с нашими экспертами для оптимизации использования сервиса.', price: 125, duration: '1 год' },
        { id: 5, name: 'Эксклюзивные функции', description: 'Доступ к новым и экспериментальным функциям сервиса до их официального релиза.', price: 150, duration: '1 месяц' },
      ],
    }
  },
}
</script>

<template>
  <div class="container">
    <div class="content">
      <h1>Подписки</h1>
      <div class="grid">
        <div v-for="plan in plans" :key="plan.id" class="card">
          <h2>{{ plan.name }}</h2>
          <p>{{ plan.description }}</p>
          <p class="price">{{ plan.price }} ₽</p>
          <p class="duration">Срок действия: {{ plan.duration }}</p>
        </div>
      </div>
      <h2 class="addon-title">Дополнительные услуги</h2>
      <div class="grid addons">
        <div v-for="addon in addons" :key="addon.id" class="card">
          <h2>{{ addon.name }}</h2>
          <p>{{ addon.description }}</p>
          <p class="price">{{ addon.price }} ₽</p>
          <p class="duration">Срок действия: {{ addon.duration }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  min-height: 100vh;
  background-color: #f9f9f9;
  padding: 2rem;
}

.content {
  max-width: 80rem;
  margin: 0 auto;
  background: rgb(27,25,25);
  background: linear-gradient(90deg, rgba(27,25,25,1) 40%, rgba(255,0,0,1) 100%);
  padding: 2rem;
  border-radius: 1rem;
  box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.1);
}

h1 {
  font-size: 2.5rem;
  font-weight: bold;
  color: #fff;
  margin-bottom: 2rem;
  text-align: center;
}

.grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
}

@media (min-width: 768px) {
  .grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .grid {
    grid-template-columns: repeat(4, 1fr);
  }
}

.card {
  cursor: pointer;
  background-color: #4a90e2;
  color: #fff;
  padding: 2rem;
  border-radius: 1rem;
  box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.1);
  transition: transform 0.3s, box-shadow 0.3s;
}

.card:hover {
  transform: translateY(-0.5rem);
  box-shadow: 0 1rem 2rem rgba(0, 0, 0, 0.15);
}

.card h2 {
  font-size: 1.75rem;
  font-weight: bold;
  margin-bottom: 1rem;
}

.card p {
  font-size: 1rem;
  margin-top: 0.5rem;
}

.card .price {
  font-size: 1.25rem;
  font-weight: bold;
  margin-top: 1.5rem;
}

.addon-title {
  font-size: 2rem;
  font-weight: bold;
  margin-top: 2rem;
  margin-bottom: 1.5rem;
  text-align: center;
  color: #fff;
}

.addons {
  grid-template-columns: 1fr;
}

@media (min-width: 768px) {
  .addons {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .addons {
    grid-template-columns: repeat(3, 1fr);
  }
}

body {
  font-family: 'Roboto', sans-serif;
  background-color: #eceff1;
  color: #37474f;
}

h1, h2 {
  font-family: 'Montserrat', sans-serif;
}

.card {
  background: linear-gradient(135deg, #42a5f5 0%, #1e88e5 100%);
}

.card:hover {
  background: linear-gradient(135deg, #1e88e5 0%, #1976d2 100%);
}
</style>