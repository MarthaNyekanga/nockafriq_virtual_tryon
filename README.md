# **NOCKAFRIQ VOGUE VIRTUAL TRY-ON-AI**

This project is a lightweight AI-powered **virtual try-on system** designed for the Nockafriq Vogue brand.  
It uses **pose detection**, **body landmark extraction**, **background-removed outfit images**, and **image compositing** to place outfits onto a model’s body.

The system is built in **Google Colab & VS Code** and uses:
- MediaPipe (pose detection)
- OpenCV (image processing)
- Pillow (image compositing)
- Google Drive for file storage

This repository contains code, images, and instructions for generating automatic clothing overlays.

----

## ✨ Features

- Detects a model’s body pose using MediaPipe.
- Estimates shoulder width, torso height, and alignment angles.
- Resizes and aligns outfits automatically.
- Supports transparent clothing PNGs.
- Saves final images back to Drive.
- Easy to customize for new outfits and models.

----

## 📁 Project Structure

NockafriqVogue-VirtualTryOn/
│
├── virtual_tryon/
│ ├── model1.jpg
│ ├── model2.jpg
│ ├── outfits/
│ │ ├── outfit1_nobg.png
│ │ ├── outfit2_nobg.png
│ ├── outputs/
│ │ ├── tryon_auto_neck.png
│ │ ├── tryon_autoaligned.png
│
├── notebooks/
│ └── virtual_tryon.ipynb
│
├── README.md
├── LICENSE
└── requirements.txt


## 🧠 How It Works

1. **Upload model images**  
   Model images must be front-facing, clear, and high resolution.

2. **Upload outfits with transparent backgrounds**  
   (PNG files recommended)

3. **Run the Colab notebook**  
   It will:
   - Mount Google Drive  
   - Load images  
   - Perform pose detection  
   - Resize + align the outfit  
   - Overlay it on the model  
   - Save the output  

4. The final images will appear inside the `outputs/` folder.

---

## 🚀 Quickstart (Using Google Colab)

1. Open the notebook in `/notebooks/virtual_tryon.ipynb`
2. Run the first cell to mount Drive
3. Upload your:
   - `model1.jpg`, `model2.jpg`
   - Outfit PNGs (transparent)
4. Update filenames inside the config cell:
   ```python
   model_fname = 'model1.jpg'
   outfit_fname = 'outfits/outfit1_nobg.png'

Run the auto-alignment cell to generate the output:
output_fname = 'outputs/tryon_auto_neck.png'
outputs/tryon_auto_neck.png

🛠 Requirements
Install these dependencies (automatically installed in Colab):
Python 3.8+
mediapipe
opencv-python
pillow
numpy
google-colab (optional)
google drive mounted in Colab
The same list appears in requirements.txt.

📸IMAGE GUIDELINES
To get accurate results:
Use front-facing models
No extreme poses
High resolution
Outfits must be transparent PNGs
No shadows on the outfit

📝 Customization
You can adjust:
scale_extra   # size of outfit
lift_pixels   # how high the outfit sits on the body
rotation_angle # angle correction
This allows perfect control for each outfit.

🤝 Contributing
Pull requests are welcome.
If you’re adding a completely new method (e.g., segmentation or advanced warping), place code under /notebooks/experiments/.

📜 License
This project is licensed under the MIT License (see LICENSE file).

👩🏾‍💻 Author
Martha Yelademe Nyekanga
Co-Founder – Nockafriq Vogue
