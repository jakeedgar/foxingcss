
```scss

// Cool buttons:
@import url(https://fonts.googleapis.com/css?family=Roboto:400,100,900);

//colors
$red: #E1332D;
$white: #fff;

//base styles

* {
  box-sizing: inherit;
  transition-property: all;
  transition-duration: .6s;
  transition-timing-function: ease;
}

html,
body {
  box-sizing: border-box;
  height: 100%;
  width: 100%;
}

body {
  background: $red;
  font-family: 'Roboto', sans-serif;
  font-weight: 400;
}

// Main wrap
.buttons {
    display: flex;
    flex-direction: column;
    height: 100%;
    justify-content: center;
    text-align: center;
    width: 100%;
}

// Button wrap
.container { 
    align-items: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 1em;
    text-align: center; 
    
    @media (min-width: 600px) {
        flex-direction: row;
        justify-content: space-between;
    }
}

h1 {
  color: $white;
  font-size: 1.25em;
  font-weight: 900;
  margin: 0 0 2em;
  
  @media (min-width: 450px) {
    font-size: 1.75em;
  }
  
  @media (min-width: 760px) {
    font-size: 3.25em;
  }
  
  @media (min-width: 900px) {
    font-size: 5.25em;
    margin: 0 0 1em;
  }
}

p {
  color: $white;
  font-size: 12px;
  
  @media(min-width: 600px) {
    left: 50%;
    position: absolute; 
    transform: translate(-50%, 0);
    top: 90%;
  }
  
  @media(max-height: 500px) {
    left: 0;
    position: relative;
    top: 0;
    transform: translate(0, 0);
  }
  
  a {
    background: rgba($white, 0);
    border-bottom: 1px solid;
    color: $white;
    line-height: 1.4;
    padding: .25em;
    text-decoration: none;
    
    &:hover {
      background: rgba($white, 1);
      color: $red;
    }
  }
}
//button styles


//default button
.btn {
  color: #fff;
  cursor: pointer;
  // display: block;
  font-size:16px;
  font-weight: 400;
  line-height: 45px;
  margin: 0 0 2em;
  max-width: 160px; 
  position: relative;
  text-decoration: none;
  text-transform: uppercase;
  width: 100%; 
  
//   @media(min-width: 400px) {
//     display: inline-block;
//     margin-right: 2.5em;
  
//     &:nth-of-type(even) {
//       margin-right: 0;
//     }
//   }
  
  @media(min-width: 600px) {
      
    margin: 0 1em 2em;
  
//     &:nth-of-type(even) {
//       margin-right: 2.5em;
//     }
    
//     &:nth-of-type(5) {
//       margin-right: 0;
//     }
    
  }
  
  &:hover { text-decoration: none; }
  
}

////////////////////////////
//button
//////////////////////////
.btn-2 {
    letter-spacing: 0;
}

.btn-2:hover,
.btn-2:active {
  letter-spacing: 5px;
}

.btn-2:after,
.btn-2:before {
  backface-visibility: hidden;
  border: 1px solid rgba(#fff, 0);
  bottom: 0px;
  content: " ";
  display: block;
  margin: 0 auto;
  position: relative;
  transition: all 280ms ease-in-out;
  width: 0;
}

.btn-2:hover:after,
.btn-2:hover:before {
  backface-visibility: hidden;
  border-color: #fff;
  transition: width 350ms ease-in-out;
  width: 70%;
}

.btn-2:hover:before {
  bottom: auto;
  top: 0;
  width: 70%;
}


// Cool Background Effect
@mixin dots($count) {
  $text-shadow: ();
  @for $i from 0 through $count {
    $text-shadow: $text-shadow,
                 (-.5+(random()) * 3) + em
                 (-.5+(random()) * 3) + em
                 7px
                 hsla(random() * 360, 100%, 50%,.9);
  }
  text-shadow: $text-shadow;
}

html {
  font: 5vmin/1.3 Serif;
  overflow: hidden;
  background: #123;
}

body, head {
  display: block;
  font-size: 52px;
  color: transparent;
}

head::before, head::after,
body::before, body::after {
  position: fixed;
  top: 50%;
  left: 50%;
  width: 3em;
  height: 3em;
  content: '.';
  mix-blend-mode: screen;
  animation: 44s -27s move infinite ease-in-out alternate;
}


body::before {
  @include dots(40);
  animation-duration: 44s;
  animation-delay: -27s;
}

body::after {
  @include dots(40);
  animation-duration: 43s;
  animation-delay: -32s;
}

head::before {
  @include dots(40);
  animation-duration: 42s;
  animation-delay: -23s;
}

head::after {
  @include dots(40);
  animation-duration: 41s;
  animation-delay: -19s;
}


@keyframes move {
  from {
    transform: rotate(0deg) scale(12) translateX(-20px);
  }
  to {
    transform: rotate(360deg) scale(18) translateX(20px);
  }
}
```