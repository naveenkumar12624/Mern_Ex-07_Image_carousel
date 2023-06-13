# Exp-7 Image Carousel in react using hooks
## AIM:
To create react app to develop Image Carousel using hooks.
## PROCEDURE:
### STEP 1:
Create react app by npm create-react-app.
### STEP 2:
Make changes to ImageCarousel.js where the Application works.
### STEP 3:
Include Style in the react using ImageCarousel.css and import it to ImageCarousel.js.
### STEP 4:
Import to App.js and there include ImageCarousel Component into App Component. 
### STEP 5:
Verify the output by running the Web-Layout in any web browser. 
## PROGRAM:
### App.css
```css
.app {
  text-align: center;
  margin-top: 2rem;
}
```
### App.js
```js
iimport React from 'react';
import ImageCarousel from './ImageCarousel';
import './App.css';

const App = () => {
  const images = [
    'https://picsum.photos/id/237/200/300',
    'https://picsum.photos/seed/picsum/200/300',
    'https://picsum.photos/200/300?grayscale',
  ];

  return (
    <div className="app">
      <h1>Image Carousel</h1>
      <ImageCarousel images={images} />
    </div>
  );
};

export default App;
```
### ImageCarousel.css
```css
.image-carousel {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .carousel-image {
    width: 500px;
    height: 400px;
    object-fit: cover;
  }
  
  .carousel-button {
    width: 30px;
    height: 30px;
    font-size: 1.2rem;
    font-weight: bold;
    background-color: #f2f2f2;
    border: none;
    border-radius: 50%;
    cursor: pointer;
    margin: 0 0.5rem;
  }
  
  .carousel-button:hover {
    background-color: #d3d3d3;
  }
```
### ImageCarousel.js
```js
import React, { useState } from 'react';
import './ImageCarousel.css';

const ImageCarousel = ({ images }) => {
  const [currentImageIndex, setCurrentImageIndex] = useState(0);

  const previousImage = () => {
    const newIndex = (currentImageIndex - 1 + images.length) % images.length;
    setCurrentImageIndex(newIndex);
  };

  const nextImage = () => {
    const newIndex = (currentImageIndex + 1) % images.length;
    setCurrentImageIndex(newIndex);
  };

  return (
    <div className="image-carousel">
      <button className="carousel-button" onClick={previousImage}>
        &lt;
      </button>
      <img
        className="carousel-image"
        src={images[currentImageIndex]}
        alt="Carousel"
      />
      <button className="carousel-button" onClick={nextImage}>
        &gt;
      </button>
    </div>
  );
};

export default ImageCarousel;
```
### index.css
```css
body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

code {
  font-family: source-code-pro, Menlo, Monaco, Consolas, 'Courier New',
    monospace;
}
```
### index.js
```js
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

// If you want to start measuring performance in your app, pass a function
// to log results (for example: reportWebVitals(console.log))
// or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
reportWebVitals();
```
## OUTPUT:
![image](https://github.com/Karthikeyan21001828/MERN_EX07/assets/93427303/6c0ca85a-7b14-4676-b3a1-7bb5bfba1161)

![image](https://github.com/Karthikeyan21001828/MERN_EX07/assets/93427303/566cc15c-57f4-4d68-84e3-7b2f08e0024c)

![image](https://github.com/Karthikeyan21001828/MERN_EX07/assets/93427303/eb7360d9-222a-4431-ad0d-a6dfdbebc266)
## RESULT:
React app to develop a Image Carousel using hooks has been created and output has been verified.
