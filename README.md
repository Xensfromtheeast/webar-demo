# 🕶️ Entumo AR — Agendas & Directions

An interactive **Web Augmented Reality (WebAR)** experience built using **A-Frame** and **AR.js**, designed for the **Entumo Conference Center** in Naivasha, Kenya.  
Attendees can use their smartphones to scan AR markers placed around the venue to view live agendas and follow GPS-based 3D navigation arrows to different rooms and stages.

---

## 📱 Features

### 🧭 Navigation & Guidance
- **GPS-based AR arrows** guide users to specific rooms and stages.
- Each stage or room has **3–5 arrow markers** placed along walking paths for accurate direction.
- Arrows orient automatically toward the user’s position (using `look-at="[gps-camera]"`).

### 🎟️ Marker-based Agendas
- Unique **.patt markers** for each room trigger the corresponding **A4-sized agenda PNG**.
- Attendees scan markers using their phone camera (no app installation needed).
- Each marker displays the agenda in **portrait orientation**, resizable with pinch gestures.

### 🕹️ Interactive UI
- A **sliding side menu** to select “Stage 1,” “Stage 2,” or the “Podcast Room.”
- A **Help panel** with a ✕ close button and smooth animations.
- Built-in **gesture support** to rotate and resize agenda content.
- Optional **VR headset mode** using A-Frame’s built-in VR interface.

### 🌐 Web-first Experience
- Runs entirely in the browser — no app store or downloads required.
- Works on modern mobile browsers supporting **WebXR** and **camera access**.
- Hosted securely via **GitHub Pages** (HTTPS required for AR camera).

---

## 🧠 Tech Stack

| Layer | Technology | Purpose |
|-------|-------------|----------|
| **Frontend** | [A-Frame](https://aframe.io) | WebVR/AR framework |
| **AR Engine** | [AR.js](https://ar-js-org.github.io/AR.js-Docs/) | Marker & GPS tracking |
| **Gesture Control** | [arjs-gestures](https://github.com/fcor/arjs-gestures) | Pinch, rotate, drag gestures |
| **3D Assets** | `.glb` models | Directional arrows and visual cues |
| **Hosting** | GitHub Pages | Free HTTPS hosting |
| **Design Tools** | Custom `.patt` generator | For unique room markers |

---

## 🧰 Project Structure

```

project-root/
│
├── index.html                # Main AR web app
│
├── assets/
│   ├── images/
│   │   ├── agenda_stage1.png
│   │   ├── agenda_stage2.png
│   │   ├── agenda_podcast.png
│   │
│   ├── markers/
│   │   ├── onguan.patt
│   │   ├── nabo.patt
│   │   ├── podcast.patt
│   │
│   └── models/
│       └── arrow.glb
│
└── README.md

````

---

## ⚙️ How It Works

1. **QR codes** on attendee badges link to the hosted web app (GitHub Pages).
2. Upon loading, the browser requests **camera and location permissions**.
3. When the user scans a marker:
   - The corresponding `.patt` file is recognized.
   - A 3D agenda panel (PNG/GLB) appears in AR view.
4. When the user selects a room from the **side menu**, multiple **GPS arrows** appear in sequence, guiding them toward that location.
5. The user can toggle **VR mode** using A-Frame’s built-in headset icon.

---

## 🧩 Setup & Deployment

### 🧠 Prerequisites
- Basic knowledge of HTML and JavaScript.
- Modern browser (Chrome / Safari).
- HTTPS hosting (e.g., GitHub Pages).

### 🔧 Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/entumo-ar.git
2. Place your agenda images inside `/assets/images/`.
3. Generate custom `.patt` files for each room at:
   [AR.js Marker Generator](https://jeromeetienne.github.io/AR.js/three.js/examples/marker-training/examples/generator.html)
4. Add or update GPS coordinates for each arrow under `<a-entity gps-entity-place="...">`.
5. Deploy to GitHub Pages:
   * Go to your repository → **Settings → Pages → Source → main branch / root**.
   * Copy the link (e.g., `https://yourusername.github.io/entumo-ar`).
6. Print and place your AR markers at their respective locations.


## 🧭 Known Issues

| Issue                    | Description                 | Fix                                                             |
| ------------------------ | --------------------------- | --------------------------------------------------------------- |
| **Markers not detected** | Low light or blurry print   | Use good lighting and high-contrast patterns                    |
| **Arrows misaligned**    | GPS drift in mobile sensors | Average coordinates for stable placement                        |
| **Slow loading on 4G**   | Large `.glb` models         | Compress with [gltfpack](https://github.com/zeux/meshoptimizer) |
| **Double VR icons**      | Custom + A-Frame default    | Remove custom button if keeping built-in VR                     |



## ✨ Future Enhancements

* Animated arrow glow/pulse effect for better direction tracking.
* Voice navigation or audio cues when nearing destinations.
* Support for live agenda updates (via JSON or API).
* Offline caching with Service Workers.



## 👨🏽‍💻 Author

**James Gichuki**
Sound Engineer & AR Developer
🎧Creating immersive event experiences for Kenya’s tech & creative industry.



## 🪪 License

This project is released under the [MIT License](LICENSE).
You’re free to use, modify, and distribute with credit.


## 📚 References

* [AR.js Official Docs](https://ar-js-org.github.io/AR.js-Docs/)
* [A-Frame Documentation](https://aframe.io/docs/)
* [Gesture Controls for AR.js](https://medium.com/@fabiojcortes/manipulate-your-3d-content-with-gestures-in-ar-js-78da4c076607)
* [WebAR with QR Codes](https://medium.com/chialab-open-source/how-to-deliver-ar-on-the-web-only-with-a-qr-code-e24b7b61f8cb)



> “Turning event maps into experiences — one marker at a time.”
