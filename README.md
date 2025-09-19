<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Do You Like Me?</title>
  <style>
    body {
      background-color: #ffe6f2; /* light pink */
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      flex-direction: column;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }
    img {
      max-width: 250px;
      height: auto;
    }
    h2 {
      margin-top: 15px;
      font-size: 28px;
      color: black;
      font-weight: bold;
    }
    .btn-container {
      margin-top: 20px;
      position: relative;
      width: 300px;
      height: 120px;
    }
    .btn {
      padding: 12px 28px;
      border: none;
      font-size: 18px;
      border-radius: 10px;
      cursor: pointer;
      transition: transform 0.2s ease, background 0.3s ease;
    }
    .btn-yes {
      background-color: #d63384; /* dark pink */
      color: white;
      font-weight: bold;
    }
    .btn-yes:hover {
      background-color: #b02a6f;
      transform: scale(1.1);
    }
    .btn-no {
      background-color: white;
      border: 2px solid #ccc;
      color: black;
      position: absolute;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);
      transition: all 0.2s ease;
    }
  </style>
</head>
<body>

  <img src="hhh.gif" alt="Cute Image">
  <h2>Do you like me ?</h2>

  <div class="btn-container">
    <button id="yesBtn" class="btn btn-yes">Yes</button>
    <button id="noBtn" class="btn btn-no">No</button>
  </div>

  <script>
    const noBtn = document.getElementById("noBtn");
    const yesBtn = document.getElementById("yesBtn");

    function moveButton() {
      const container = noBtn.parentElement;
      const containerWidth = container.offsetWidth - noBtn.offsetWidth;
      const containerHeight = container.offsetHeight - noBtn.offsetHeight;

      const newX = Math.floor(Math.random() * containerWidth);
      const newY = Math.floor(Math.random() * containerHeight);

      noBtn.style.left = `${newX}px`;
      noBtn.style.top = `${newY}px`;
    }

    noBtn.addEventListener("mouseenter", moveButton);
    noBtn.addEventListener("touchstart", moveButton);

    yesBtn.addEventListener("click", () => {
      window.location.href = "first.html"; // seedha next page
    });
  </script>

</body>
</html>


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>I Knew It</title>
  <style>
    body {
      background-color: #ffe6f2;
      margin: 0;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      text-align: center;
    }
    .slide {
      display: none;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }
    img {
      max-width: 250px;
      height: auto;
      margin-bottom: 15px;
    }
    h2 {
      font-size: 26px;
      color: #d63384;
      font-weight: bold;
    }
    .fade {
      animation: fadeIn 1s ease-in-out;
    }
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
  </style>
</head>
<body>

  <div id="slides">
    <!-- 1st -->
    <div class="slide">
      <img src="1000027627.jpg" alt="Pic1">
      <h2>I knew it 😍</h2>
    </div>
    <!-- 2nd (hug funny) -->
    <div class="slide">
      <img src="1000027624.jpg" alt="Hug Pic">
      <h2>Awwwwwww You're so good! 😂❤️</h2>
    </div>
    <!-- 3rd (kiss shy emoji only) -->
    <div class="slide">
      <img src="1000027622.jpg" alt="Kiss Pic">
      <h2>🙈</h2>
    </div>
    <!-- 4th (flower funny) -->
    <div class="slide">
      <img src="1000027625.jpg" alt="Flower Pic">
      <h2>You deserve this ... mere bure insan 💐😂</h2>
    </div>
  </div>

  <script>
    const slides = document.querySelectorAll(".slide");
    let current = 0;

    function showSlide(index) {
      slides.forEach((slide, i) => {
        if (i === index) {
          slide.style.display = "flex";
          slide.classList.add("fade");
        } else {
          slide.style.display = "none";
          slide.classList.remove("fade");
        }
      });
    }

    function nextSlide() {
      showSlide(current);
      current++;
      if (current < slides.length) {
        setTimeout(nextSlide, 2000); // 3 sec delay
      }
    }

    // Start slideshow
    nextSlide();
  </script>

</body>
</html>
