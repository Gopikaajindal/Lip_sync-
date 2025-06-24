# Lip_sync-

This repository contains a **complete pipeline for high-quality lip-syncing** of videos using **LatentSync** combined with **Whisper-based audio encoding**. The system generates realistic, synced mouth movements for a given speaker video using external audio input.

---

## 📝 **Project Description**

**LatentSync** is an advanced framework for generating accurate lip-sync in videos. Unlike basic frame-to-frame sync methods, **LatentSync works in the *latent feature space*** for better temporal consistency and realistic articulation.

This project allows you to:

* Upload any **video** of a person speaking
* Provide **custom external audio**
* Generate a **synchronized video output** where lip movements match the new audio
* Leverage **Whisper tiny model** for audio feature extraction
* Use **LatentSync UNet model** for generating the synced video

---

## 📂 **Folder Structure**

```
python -m scripts.inference \
  --unet_config_path configs/unet/stage2.yaml \
  --inference_ckpt_path checkpoints/latentsync_unet.pt \
  --inference_steps 20 \
  --guidance_scale 2.0 \
  --video_path /path/to/input_video.mp4 \
  --audio_path /path/to/input_audio.wav \
  --video_out_path /path/to/output_video.mp4

```

---


📂 Requirements
LatentSync UNet Checkpoint
Whisper Tiny Checkpoint

---


## ⚙️ **How to Run**

### ✅ **Step 1: Clone Repository**

```bash
git clone https://github.com/your-username/your-repo-name.git
```

### ✅ **Step 2: Install Requirements (Already configured in Colab)**

```bash
pip install -r requirements.txt
```

### ✅ **Step 3: Upload Inputs**

* Upload your **video (.mp4)** and **audio (.wav)** files.

### ✅ **Step 4: Run Inference**

```bash
!python -m scripts.inference \
  --unet_config_path configs/unet/stage2.yaml \
  --inference_ckpt_path checkpoints/latentsync_unet.pt \
  --video_path /path/to/your/video.mp4 \
  --audio_path /path/to/your/audio.wav \
  --video_out_path /path/to/output/result.mp4
```

---


## ⚠️ **Notes**

* **Video Length:** Long videos may take **30+ minutes**. For quick testing, use **short 5-10 second clips**.
* **Face Restoration:** After inference, faces are automatically restored for better visual quality.

---

## 🤝 **Contributing**

Pull requests and feature requests are welcome.

---

