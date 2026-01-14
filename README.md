# Real-Time Location Tracker 📍

This repository contains a real-time location tracking web application that continuously tracks users' geographical positions and displays them on a live interactive map. The implementation follows the exact workflow shown below.

---

## 📌 Workflow Overview

1. **Browser Geolocation Check**
   The application first verifies whether the browser supports the Geolocation API.

2. **Geolocation Options Setup**
   Location tracking is configured with:

   * High accuracy enabled
   * 5-second timeout
   * No cached location data

3. **Continuous Location Tracking**
   Uses `navigator.geolocation.watchPosition()` to track the user’s location continuously.

4. **Send Location via Socket**
   Latitude and longitude are emitted to the server using Socket.IO with the event:

   ```
   send-location
   ```

   Any geolocation errors are logged to the browser console.

5. **Map Initialization**

   * Initializes a Leaflet map centered at coordinates `(0, 0)`
   * Default zoom level set to `15`
   * OpenStreetMap tiles are added to the map

6. **Marker Storage**
   An empty `markers` object is created to manage user markers dynamically.

7. **Receive & Render Locations**
   When location data is received via Socket.IO:

   * Extracts user `id`, `latitude`, and `longitude`
   * Centers the map on the new coordinates
   * Updates an existing marker if present
   * Creates a new marker if none exists

8. **Handle User Disconnect**
   When a user disconnects:

   * Their marker is removed from the map
   * The marker reference is deleted from the `markers` object

---

## 🛠 Tech Stack

* Node.js
* Express.js
* Socket.IO
* Leaflet.js
* OpenStreetMap
* JavaScript (Geolocation API)

---

## 🎯 Use Cases

* Live user tracking
* Real-time map-based applications
* Location-sharing systems
* Learning WebSockets and geolocation

---

## 🚀 Getting Started

```bash
npm install
node app.js
```

Open your browser and visit:

```
http://localhost:3000
```

---

## 📄 License

This project is intended for educational and demonstration purposes.

---

**Author:** Amar
