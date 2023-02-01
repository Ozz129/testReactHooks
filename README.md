# testReactHooks

import React from "react";
import "./App.css";
import { useEffect, useState } from 'react';


function App() {
  
const images = [
  'https://www.nintenderos.com/wp-content/uploads/2022/10/goku-super-saiyan-347x195.webp',
  'https://thumb.sfmlab.com/item-preview/item_thumb_next/56885/Thumb-Vegeta.detail.webp'
  ]

const [character, setCharacter] = useState('goku');
const [personaje, setPersonaje] = useState('goku2');

const [image, setImage] = useState(images[0]);

useEffect( () => {
    //alert(character)
    if (character === 'vegeta') {
        setImage(images[1])
    } else {
        setImage(images[0])
    }

}, [character])

  return (
    <div className="App">
        <input type="text" onKeyUp={(event) => {
            setCharacter(event.target.value)
        }} />
        <hr />
        <input type="text" onKeyUp={(e) => {
            setPersonaje(e.target.value)
        }} />
        <h1>{character} -- {personaje}</h1>
        <img src={image} alt="" />
    </div>
  );
}

export default App;
