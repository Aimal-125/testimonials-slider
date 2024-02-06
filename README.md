# Frontend Mentor - Coding bootcamp testimonials slider solution

This is a solution to the [Coding bootcamp testimonials slider challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/coding-bootcamp-testimonials-slider-4FNyLA8JL). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshots](#screenshots)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned) 
  - [Useful resources](#useful-resources)
- [Author](#author) 

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the component depending on their device's screen size
- Navigate the slider using either their mouse/trackpad or keyboard

### Screenshots

#### Desktop Design

![](./screenshots/desktop.png)

#### Mobile Design

![](./screenshots/mobile.png)

### Links

- Solution URL: [GitHub](https://github.com/Aimal-125/testimonials-slider.git)
- Live Site URL: [GitHub Pages](https://aimal-125.github.io/testimonials-slider/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Animations
- Mobile-first workflow
- [React](https://reactjs.org/) - JS library
- [Vite](https://vitejs.dev/) - Front-End Tool

### What I learned

```js
let App = () => {
  return (
    <div className="sliderContainer" >    
    <Slider slides={SliderData} />
    </div>
    );
};
```
```js
let Slider = ({slides}) => {
  let [current, setCurrent] = useState(0);
  let length = slides.length;
  let nextSlide = () => {
    setCurrent(current === length - 1 ? 0 : current + 1);
  };
  let prevSlide = () => {
    setCurrent(current === 0 ? length - 1 : current - 1);
  };
  return (
    <>
    <div className="textContainer" >
    <p>
    <q>{slides.map((v, i) => {
      return i === current && v.quote;
    })}</q>
    </p>
    <div className="nameContainer" >
    <span className="name" >{slides.map((v, i) => {
      return i === current && v.name;
    })}</span>
    <span className="work" >{slides.map((v, i) => {
      return i === current && v.work;
    })}</span>
    </div>
    </div>
    <div className="slider">
    {slides.map((slide, index) => {
      return (
        <div className={index === current ? "slide active" : "slide"} key={index} >
        {index === current && (<img src={slide.image} alt={slide.alt} />)}
        </div>
        );
    })}
    <div className="btnContainer">
    <button className="btn prevBtn" onClick={prevSlide} ><span className="btnLabel" >Previous Slide</span></button>
    <button className="btn nextBtn" onClick={nextSlide} ><span className="btnLabel" >Next Slide</span></button>
    </div>
    </div>
    </>
    );
};
``` 

### Useful resources

- [ReactJs Guru](https://reactjsguru.com/how-to-make-image-slider-in-react/) - This article helped me to create Slider in ReactJs.

- [Mediumn](https://medium.com/@badreddine.boudaoud21/create-a-react-app-with-vite-and-deploy-it-on-github-48b82e19f821) - This article 
helpled me to deploy react app with vite on Github Pages.

## Author

- Frontend Mentor - [@Aimal-125](https://www.frontendmentor.io/profile/Aimal-125)
- Twitter - [@aimal4910](https://www.twitter.com/aimal4910)
- LinkedIn - [@aimalkhan125](https://www.linkedin.com/in/aimalkhan125)