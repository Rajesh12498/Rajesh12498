<!DOCTYPE html>
<html>
<head>
  <title>Task2 </title>
  <style>
    .slider-container {
      width: 100%;
      height: 400px;
      overflow: hidden;
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 2;
    }

    .slider {
      width: 400px;
      height: 200px;
      position: relative;
      overflow: hidden;
    }

    .slider-inner {
      display: flex;
      width: max-content;
      animation: slide 15s infinite;
    }

    .slider-item {
      width: 400px;
      height: 200px;
    }

    .slider-item img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .slider-button {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      width: 30px;
      height: 30px;
      background-color: rgba(0, 0, 0, 0.5);
      color: #fff;
      text-align: center;
      font-size: 20px;
      line-height: 30px;
      cursor: pointer;
    }

    .slider-button.left {
      left: 10px;
    }

    .slider-button.right {
      right: 10px;
    }

    @keyframes slide {
      0% {
        transform: translateX(0);
      }
      100% {
        transform: translateX(-100%);
      }
    }
  </style>
</head>
<body>
  <div class="slider-container">
    <div class="slider">
      <div class="slider-inner">
        <div class="slider-item">
          <img src="https://img.freepik.com/free-photo/coffee-latte-with-cookies-coffiee-beans_141793-17440.jpg?w=740&t=st=1689145979~exp=1689146579~hmac=bbc3a36a904bb0de9007197c326b6130878e2c5137121d0dc6fa8fd039b9aa94" alt="Image 1">
        </div>
        <div class="slider-item">
          <img src="https://img.freepik.com/free-photo/cup-coffee-with-heart-drawn-foam_1286-70.jpg?1&w=740&t=st=1689146051~exp=1689146651~hmac=d3b07d7aebfcd9bbfdb5271a1a7c7dca1ab9a0ce9d8cce67a606e633b1311ace" alt="Image 2">
        </div>
        <div class="slider-item">
          <img src="https://img.freepik.com/free-photo/view-coffee-machine_23-2149709953.jpg?w=740&t=st=1689146081~exp=1689146681~hmac=19415fed94eb96a010b5cde334ba6f9b784fac0598e710f073bd10e63f7d51ad" alt="Image 3">
        </div>
        <div class="slider-item">
            <img src="https://img.freepik.com/premium-photo/roasted-coffee-beans-with-aromatic-smoke_168171-901.jpg?w=360" alt="Image 3">
          </div>
          <div class="slider-item">
            <img src="https://img.freepik.com/free-photo/cup-coffee-with-pile-coffee-beans_1112-438.jpg?w=740&t=st=1689146140~exp=1689146740~hmac=83de681115883e6d090d7e0e0f4b6e7c63c76659a4611c8ef22113f24ed205a1" alt="Image 3">
          </div>
      </div>
    </div>

    <div class="slider-button left" onclick="slideLeft()">&lt;</div>
    <div class="slider-button right" onclick="slideRight()">&gt;</div>
  </div>

  <script>
    var slider = document.querySelector('.slider-inner');
    var sliderItems = document.querySelectorAll('.slider-item');
    var sliderWidth = slider.offsetWidth;
    var slideIndex = 0;

    // Function to slide the slider to the left
    function slideLeft() {
      slideIndex--;
      if (slideIndex < 0) {
        slideIndex = sliderItems.length - 2;
      }
      updateSliderPosition();
    }

    // Function to slide the slider to the right
    function slideRight() {
      slideIndex++;
      if (slideIndex >= sliderItems.length) {
        slideIndex = 0;
      }
      updateSliderPosition();
    }

    // Function to update the position of the slider
    function updateSliderPosition() {
      var position = slideIndex * -sliderWidth;
      slider.style.transform = 'translateX(' + position + 'px)';
    }
  </script>
</body>
</html>

