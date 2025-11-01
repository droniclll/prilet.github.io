# prilet.github.io
<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8" />
<title>Обратный отсчет</title>
<style>
  body {
    font-family: Arial, sans-serif;
    text-align: center;
    margin-top: 50px;
  }
  #countdown {
    font-size: 3em;
    color: #333;
  }
</style>
</head>
<body>

<h1>Обратный отсчет до 2 ноября 18:45</h1>
<div id="countdown">Загрузка...</div>

<script>
  // Целевая дата и время
  const countdownDate = new Date('2025-11-02T18:45:00').getTime();

  const countdownEl = document.getElementById('countdown');

  // Обновление таймера каждую секунду
  const interval = setInterval(() => {
    const now = new Date().getTime();
    const distance = countdownDate - now;

    if (distance <= 0) {
      clearInterval(interval);
      countdownEl.textContent = 'Время истекло';
      return;
    }

    const days = Math.floor(distance / (1000 * 60 * 60 * 24));
    const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
    const seconds = Math.floor((distance % (1000 * 60)) / 1000);

    countdownEl.textContent = `${days} дн ${hours} час ${minutes} мин ${seconds} сек`;
  }, 1000);
</script>

</body>
</html>
