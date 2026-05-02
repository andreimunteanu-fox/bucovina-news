<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Bucovina TV</title>

  <script src="https://aframe.io/releases/1.5.0/aframe.min.js"></script>
</head>

<body>

<a-scene background="color:#0a0a1a">

  <!-- ===== LUMINI DE STUDIO ===== -->
  <a-light type="ambient" intensity="0.3"></a-light>
  <a-light type="directional" position="5 8 5" intensity="1.2" cast-shadow="true"></a-light>
  <a-light type="point" position="0 4 -6" intensity="1.5" color="#ff3300" decay="1.5"></a-light>
  <a-light type="spot" position="0 6 0" angle="45" intensity="1.8" penumbra="0.5" cast-shadow="true"></a-light>
  <a-light type="point" position="-8 3 -5" intensity="0.6" color="#4444ff"></a-light>
  <a-light type="point" position="8 3 -5" intensity="0.6" color="#4444ff"></a-light>

  <!-- SKY - Noapte de studio -->
  <a-sky color="#0a0a1a"></a-sky>

  <!-- PODEA DE STUDIO (reflectivă, cu margini LED) -->
  <a-plane rotation="-90 0 0" width="50" height="50"
           material="color:#1a1a2e; roughness:0.3; metalness:0.6; envMapIntensity:0.5"
           shadow="receive:true"></a-plane>
  
  <!-- Margini LED podea -->
  <a-plane position="0 0.01 -25" rotation="-90 0 0" width="50" height="0.2" material="color:#00ff88; emissive:#00ff88; emissiveIntensity:1.5"></a-plane>
  <a-plane position="0 0.01 15" rotation="-90 0 0" width="50" height="0.2" material="color:#00ff88; emissive:#00ff88; emissiveIntensity:1.5"></a-plane>
  <a-plane position="-25 0.01 -5" rotation="-90 0 90" width="50" height="0.2" material="color:#00ff88; emissive:#00ff88; emissiveIntensity:1.5"></a-plane>
  <a-plane position="25 0.01 -5" rotation="-90 0 90" width="50" height="0.2" material="color:#00ff88; emissive:#00ff88; emissiveIntensity:1.5"></a-plane>

  <!-- PERETE SPATE - Panou texturat studio -->
  <a-box position="0 4 -25" width="40" height="12" depth="1"
         material="color:#16162a; roughness:0.7; metalness:0.2; side:double" shadow="cast:true; receive:true">
  </a-box>
  
  <!-- Sigla TV pe perete spate -->
  <a-text value="BUCOVINA\nTV" position="0 7 -24.55" align="center"
          color="#ff3300" width="12" font="https://cdn.aframe.io/fonts/mozillavr.fnt"
          rotation="0 0 0"></a-text>
  
  <a-text value="STUDIO" position="0 5.5 -24.55" align="center"
          color="#00ff88" width="10" font="https://cdn.aframe.io/fonts/mozillavr.fnt"></a-text>

  <!-- PERETE STÂNGA - Cu panouri decorative -->
  <a-box position="-20 4 -12" width="1" height="10" depth="20"
         material="color:#16162a; roughness:0.7" shadow="cast:true; receive:true"></a-box>
  
  <a-box position="-20 8 -15" width="0.8" height="2" depth="0.8"
         material="color:#2a2a4a"></a-box>
  <a-box position="-20 8 -8" width="0.8" height="2" depth="0.8"
         material="color:#2a2a4a"></a-box>
  <a-box position="-20 8 -2" width="0.8" height="2" depth="0.8"
         material="color:#2a2a4a"></a-box>

  <!-- PERETE DREAPTA - Cu panouri decorative -->
  <a-box position="20 4 -12" width="1" height="10" depth="20"
         material="color:#16162a; roughness:0.7" shadow="cast:true; receive:true"></a-box>
  
  <a-box position="20 8 -15" width="0.8" height="2" depth="0.8"
         material="color:#2a2a4a"></a-box>
  <a-box position="20 8 -8" width="0.8" height="2" depth="0.8"
         material="color:#2a2a4a"></a-box>
  <a-box position="20 8 -2" width="0.8" height="2" depth="0.8"
         material="color:#2a2a4a"></a-box>

  <!-- TAVAN - Cu ring LED -->
  <a-box position="0 12 -15" width="40" height="1" depth="20"
         material="color:#0a0a1a; roughness:0.5"></a-box>
  
  <!-- Ring LED tavan -->
  <a-torus position="0 11.5 -15" rotation="90 0 0" radius="18" radius-tubular="0.15"
           material="color:#00ff88; emissive:#00ff88; emissiveIntensity:2" opacity="0.8"></a-torus>

  <!-- Pupitru prezentator -->
  <a-entity position="0 1.5 -8">
    <!-- Blat pupitru -->
    <a-box width="6" height="0.1" depth="3"
           material="color:#2a2a3a; roughness:0.5; metalness:0.4"></a-box>
    <!-- Picioare pupitru -->
    <a-box position="-2.5 1 -10" width="0.2" height="2" depth="0.2"
           material="color:#3a3a4a; metalness:0.6"></a-box>
    <a-box position="2.5 1 -10" width="0.2" height="2" depth="0.2"
           material="color:#3a3a4a; metalness:0.6"></a-box>
    <!-- Mic ecran pe pupitru -->
    <a-box position="0 1.15 -11" width="2" height="1" depth="0.1"
           material="color:#001122; roughness:0.3; metalness:0.5"></a-box>
    <a-text value="LIVE" position="0 1.25 -10.95" align="center"
            color="#ff3300" width="3"></a-text>
  </a-entity>

  <!-- CAMERA -->
  <a-entity position="0 1.6 6">
    <a-camera look-controls wasd-controls>
      <a-cursor
        cursor="rayOrigin: mouse"
        raycaster="objects: .news, .clickable, .popup-bg, .popup-close"
        material="color:#00ff88; shader:flat"></a-cursor>
    </a-camera>
  </a-entity>

  <!-- TITLU -->
  <a-text value="BUCOVINA TV - NEWS STUDIO" position="0 6 -6"
          align="center" color="#ff3300" width="14" font="https://cdn.aframe.io/fonts/mozillavr.fnt"
          shadow="cast:true"></a-text>

  <!-- ECRAN TV -->
  <a-box position="0 3 -8" width="8" height="4.5" depth="0.3"
         material="color:#0a0a1a; roughness:0.5; metalness:0.7" shadow="cast:true">
  </a-box>
  
  <!-- Ecrane TV (mici) -->
  <a-plane position="0 3 -7.85" width="7.6" height="4.1"
           material="color:#111; emissive:#002244; emissiveIntensity:0.5; side:double"
           shadow="cast:true">
    <a-text id="screenTitle" value="BREAKING NEWS" position="0 1.5 0.05"
            align="center" color="#ff3300" width="10" font="https://cdn.aframe.io/fonts/mozillavr.fnt"></a-text>
    <a-text id="screenText" value="Click pe o stire" position="0 0.2 0.05"
            align="center" color="#00ff88" width="8"></a-text>
  </a-plane>

  <!-- TICKER STATIC -->
  <a-entity position="0 1.5 -7.7">
    <a-text value="● LIVE" position="0 0 0" color="#ff3300" width="5"
            font="https://cdn.aframe.io/fonts/mozillavr.fnt"></a-text>
    <a-text value="ACTUALITATE" position="1.5 0 0" color="#aaa" width="4"
            font="https://cdn.aframe.io/fonts/mozillavr.fnt"></a-text>
    <a-text value="SPORT" position="3.3 0 0" color="#aaa" width="3"
            font="https://cdn.aframe.io/fonts/mozillavr.fnt"></a-text>
  </a-entity>

  <!-- MICROFON -->
  <a-entity position="-2 2.5 -7.5">
    <a-cylinder position="0 0.8 0" radius="0.05" height="1.5"
                material="color:#333; metalness:0.8"></a-cylinder>
    <a-sphere position="0 1.6 0" radius="0.15"
              material="color:#222; metalness:0.8"></a-sphere>
    <a-cylinder position="0 1.7 0" radius="0.08" height="0.3"
                material="color:#ff3300; emissive:#ff3300; emissiveIntensity:1"></a-cylinder>
  </a-entity>

  <!-- CAFETERIE / BAR în fundal stânga -->
  <a-entity position="-18 2 -18">
    <a-box width="4" height="3" depth="1.5" material="color:#1a1a2a"></a-box>
    <a-text value="CAFEA" position="0 2 0.8" align="center" color="#aaa" width="5"></a-text>
  </a-entity>

  <!-- Plante decorative -->
  <a-entity position="-8 1.5 -20">
    <a-cylinder position="0 0.5 0" radius="0.3" height="1" material="color:#2a4a2a"></a-cylinder>
    <a-cone position="0 1.3 0" radius-bottom="0.8" radius-top="0" height="1.5" material="color:#2a6a2a"></a-cone>
  </a-entity>

  <a-entity position="8 1.5 -20">
    <a-cylinder position="0 0.5 0" radius="0.3" height="1" material="color:#2a4a2a"></a-cylinder>
    <a-cone position="0 1.3 0" radius-bottom="0.8" radius-top="0" height="1.5" material="color:#2a6a2a"></a-cone>
  </a-entity>

  <!-- Scaun de studio (pentru invitat) -->
  <a-entity position="3 1 -18">
    <!-- Spătar -->
    <a-box position="0 1 0" width="0.1" height="2" depth="1" material="color:#2a2a3a"></a-box>
    <!-- Șezut -->
    <a-box position="0 0.5 0.4" width="1" height="0.1" depth="0.8" material="color:#2a2a3a"></a-box>
    <!-- Picioare -->
    <a-cylinder position="-0.4 0.25 0.8" radius="0.05" height="0.5" material="color:#333"></a-cylinder>
    <a-cylinder position="0.4 0.25 0.8" radius="0.05" height="0.5" material="color:#333"></a-cylinder>
  </a-entity>

  <!-- RIGLETĂ decorativă pe podea -->
  <a-plane position="0 0.02 -15" rotation="-90 0 0" width="30" height="0.3"
           material="color:#ff3300; emissive:#ff3300; emissiveIntensity:1"></a-plane>

  <!-- Puncte luminoase pe podea -->
  <a-entity position="-6 0.1 -10">
    <a-sphere radius="0.1" material="color:#00ff88; emissive:#00ff88; emissiveIntensity:1"></a-sphere>
  </a-entity>
  <a-entity position="6 0.1 -10">
    <a-sphere radius="0.1" material="color:#00ff88; emissive:#00ff88; emissiveIntensity:1"></a-sphere>
  </a-entity>

  <!-- PERETE SPATE -->
  <a-box position="0 2 -10" width="20" height="5" depth="1" color="#222"></a-box>

  <!-- TITLU -->
  <a-text value="BUCOVINA TV - NEWS STUDIO"
          position="0 4 -4"
          align="center"
          color="red"
          width="10"></a-text>

  <!-- ===== ECRAN TV (FIXAT) ===== -->
  <a-plane position="0 2 -6" width="6" height="3"
           material="color:#111; emissive:#ff0000; emissiveIntensity:0.3; side:double"
           animation="property: material.emissiveIntensity; dir:alternate; dur:2000; loop:true; to:0.8">

    <a-text id="screenTitle"
            value="BREAKING NEWS"
            position="0 0.8 0.1"
            align="center"
            color="yellow"
            width="8"></a-text>

    <a-text id="screenText"
            value="Click pe o stire"
            position="0 -0.2 0.1"
            align="center"
            color="white"
            width="7"></a-text>

  </a-plane>

  <!-- TICKER -->
  <a-text value="BREAKING NEWS: E momentul adevarului, azi aflu daca e bun proiectul ITRMV"
          position="0 0.5 -3"
          color="red"
          width="10"
          animation="property: position; to: -10 0.5 -3; dur: 8000; loop: true">
  </a-text>

  <!-- ===== STÂNGA ===== -->

  <a-entity position="-6 2.5 -7">
    <a-image class="news" data-id="1" src="images/AND_8292.jpg" width="1.8" height="1.2"></a-image>
    <a-text value="Accident grav" position="0 -2.5 0" align="center" color="#ff3300" font="https://cdn.aframe.io/fonts/mozillavr.fnt"></a-text>
  </a-entity>

  <a-entity position="-6 2.5 -5">
    <a-image class="news" data-id="2" src="images/AND_8293.jpg" width="1.8" height="1.2"></a-image>
    <a-text value="Masina implicata" position="0 -2.5 0" align="center" color="#ff3300" font="https://cdn.aframe.io/fonts/mozillavr.fnt"></a-text>
  </a-entity>

  <a-entity position="-6 2.5 -3">
    <a-image class="news" data-id="3" src="images/AND_8294.jpg" width="1.8" height="1.2"></a-image>
    <a-text value="Barbat ranit" position="0 -2.5 0" align="center" color="#ff3300" font="https://cdn.aframe.io/fonts/mozillavr.fnt"></a-text>
  </a-entity>

  <!-- ===== DREAPTA ===== -->

  <a-entity position="6 2.5 -7">
    <a-image class="news" data-id="4" src="images/AND_8295.jpg" width="1.8" height="1.2"></a-image>
    <a-text value="Om lovit" position="0 -2.5 0" align="center" color="#ff3300" font="https://cdn.aframe.io/fonts/mozillavr.fnt"></a-text>
  </a-entity>

  <a-entity position="6 2.5 -5">
    <a-image class="news" data-id="5" src="images/AND_8296.jpg" width="1.8" height="1.2"></a-image>
    <a-text value="Copac rupt" position="0 -1.8 0" align="center" color="#ff3300" font="https://cdn.aframe.io/fonts/mozillavr.fnt"></a-text>
  </a-entity>

  <a-entity position="6 2.5 -3">
    <a-image class="news" data-id="6" src="images/AND_8297.jpg" width="1.8" height="1.2"></a-image>
    <a-text value="Accident" position="0 -2.5 0" align="center" color="#ff3300" font="https://cdn.aframe.io/fonts/mozillavr.fnt"></a-text>
  </a-entity>

  <!-- POPUP -->
  <a-entity id="popup" visible="false" position="0 4 -1" scale="0 0 0">

      <a-plane class="popup-bg clickable" width="5" height="2.5" color="#111" opacity="0.95"></a-plane>

      <a-text id="popupTitle"
              position="0 0.9 0.1"
              align="center"
              color="#ff3300"
              width="7"
              font="https://cdn.aframe.io/fonts/mozillavr.fnt"></a-text>

      <a-text id="popupText"
              position="0 0.1 0.1"
              align="center"
              color="#ffffff"
              width="6.5"></a-text>

      <a-text class="popup-close"
              position="0 -1 0.1"
              align="center"
              color="#666"
              font="https://cdn.aframe.io/fonts/mozillavr.fnt"
              value="Click pentru inchidere"></a-text>

  </a-entity>

</a-scene>

<script>

  const scene = document.querySelector('a-scene');
  if (!scene) throw new Error('A-Frame scene not found');

   function init() {

      const data = {
       1:{t:"Accident grav",d:"Interventie de urgenta in parcul Universitatii, cad copaci."},
       2:{t:"Masina implicata",d:"Detalii despre accident rutier."},
       3:{t:"Barbat ranit",d:"O persoana a suferit rani."},
       4:{t:"Masina care a distrus un om",d:"Pieton lovit grav de o masina."},
       5:{t:"Copacirupti la USV",d:"Vantul a pus la pamant copacii din parc"},
       6:{t:"Impact la spital",d:"Doua masini implicate in accident la spital."}
     };

     const popup = document.querySelector("#popup");
     const popupTitle = document.querySelector("#popupTitle");
     const popupText = document.querySelector("#popupText");

     const screenTitle = document.querySelector("#screenTitle");
     const screenText = document.querySelector("#screenText");

      popup.addEventListener("click",(evt)=>{
        if (evt.target.classList.contains("popup-close") || evt.target.classList.contains("popup-bg")) {
          // Resetăm elementul care e în starea expandată
          const expandedEl = document.querySelector(".news[data-centered='true']");
          if (expandedEl) {
            const parentEl = expandedEl.parentElement;
            const originalPos = expandedEl.getAttribute("data-original-position");
            const originalScale = expandedEl.getAttribute("data-original-scale");
            if (originalPos) parentEl.setAttribute("position", originalPos);
            if (originalScale) expandedEl.setAttribute("scale", originalScale);
            expandedEl.setAttribute("data-centered", "false");
          }

            popup.removeAttribute("animation");
            popup.removeAttribute("animation__scale");
            popup.removeAttribute("animation__fade");
            popup.setAttribute("animation__fade_out", "property: material.opacity; to: 0; dur: 200; easing: easeInQuad");
            popup.setAttribute("animation__scale_down", "property: scale; to: 0.8 0.8 0.8; dur: 200; easing: easeInQuad");
            setTimeout(()=>{
              popup.setAttribute("visible", false);
              popup.removeAttribute("animation__fade_out");
              popup.removeAttribute("animation__scale_down");
            },200);
        }
      });

      document.querySelectorAll(".news").forEach(el=>{

         el.addEventListener("mouseenter", ()=>{
          if (el.getAttribute("data-centered") !== "true") {
            el.setAttribute("scale","1.2 1.2 1.2");
          }
        });

        el.addEventListener("mouseleave", ()=>{
          if (el.getAttribute("data-centered") !== "true") {
            el.setAttribute("scale","1 1 1");
          }
        });

        el.addEventListener("click",()=>{
          const id = el.getAttribute("data-id");
          const parent = el.parentElement;
          const isCentered = el.getAttribute("data-centered") === "true";

          if (isCentered) {
            const originalPos = el.getAttribute("data-original-position");
            const originalScale = el.getAttribute("data-original-scale");
            if (originalPos) parent.setAttribute("position", originalPos);
            if (originalScale) {
              el.setAttribute("animation__collapse", "property: scale; to: " + originalScale + "; dur: 300; easing: easeInQuad");
              setTimeout(() => {
                el.setAttribute("scale", originalScale);
                el.removeAttribute("animation__collapse");
              }, 310);
            } else {
              el.setAttribute("scale", "1 1 1");
            }
            el.setAttribute("animation__rotate_back", "property: rotation; to: 0 0 0; dur: 300; easing: easeInCubic");
            el.setAttribute("data-centered", "false");

            // Arată textul din nou când se restrânge
            const textEl = parent.querySelector("a-text");
            if (textEl) textEl.setAttribute("visible", true);

            if (popup.getAttribute("visible") === "true") {
              popup.removeAttribute("animation");
              popup.setAttribute("animation","property: scale; to:0 0 0; dur:200");
              setTimeout(()=>{
                popup.setAttribute("visible", false);
              },200);
            }
          } else {
            document.querySelectorAll(".news[data-centered='true']").forEach(centeredEl => {
              const parentEl = centeredEl.parentElement;
              const pos = centeredEl.getAttribute("data-original-position");
              const scale = centeredEl.getAttribute("data-original-scale");
              if (pos) parentEl.setAttribute("position", pos);
              if (scale) centeredEl.setAttribute("scale", scale);
              centeredEl.setAttribute("data-centered", "false");
              // Arată textul pentru elementul restrâns
              const txt = parentEl.querySelector("a-text");
              if (txt) txt.setAttribute("visible", true);
            });

            const currentPos = parent.getAttribute("position");
            const currentScale = el.getAttribute("scale");
            let scaleString;
            if (typeof currentScale === 'string') {
              scaleString = currentScale;
            } else if (currentScale && typeof currentScale === 'object') {
              scaleString = `${currentScale.x} ${currentScale.y} ${currentScale.z}`;
            } else {
              scaleString = "1 1 1";
            }
            let posString;
            if (typeof currentPos === 'string') {
              posString = currentPos;
            } else if (currentPos && typeof currentPos === 'object') {
              posString = `${currentPos.x} ${currentPos.y} ${currentPos.z}`;
            } else {
              posString = "0 2 -3";
            }
            el.setAttribute("data-original-position", posString);
            el.setAttribute("data-original-scale", scaleString);
            parent.setAttribute("position", "0 3 -2");
            el.setAttribute("scale", "1 1 1");
            el.setAttribute("animation__expand", "property: scale; to: 4 4 4; dur: 400; easing: easeOutQuad");
            el.setAttribute("animation__rotate", "property: rotation; to: 0 5 0; dur: 600; easing: easeOutCubic");
            el.setAttribute("data-centered", "true");

            // Ascunde textul când se expandează
            const textEl = parent.querySelector("a-text");
            if (textEl) textEl.setAttribute("visible", false);
          }

          screenTitle.setAttribute("value", data[id].t);
          screenText.setAttribute("value", data[id].d);

          popupTitle.setAttribute("value", data[id].t);
          popupText.setAttribute("value", data[id].d);

          const isPopupVisible = popup.getAttribute("visible") === "true";
          if (!isPopupVisible) {
            popup.removeAttribute("animation");
            popup.setAttribute("visible", true);
            popup.setAttribute("scale", "0 0 0");
            setTimeout(() => {
              popup.setAttribute("animation", "property: scale; to:1 1 1; dur:300");
            }, 10);
          }
        });
      });

  }

  if (scene.hasLoaded) {
    init();
  } else {
    scene.addEventListener('loaded', init);
  }

</script>

</body>
</html>
