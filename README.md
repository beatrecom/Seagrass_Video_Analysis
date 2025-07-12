# Seagrass Video and Image Recognition 

### Expanded Summary  
As part of a COMIT-supported research effort, Bea Combs-Hintze has developed an image-recognition pipeline that began with a training database. The goal is to transform hours of underwater video footage from autonomous surface vessels (ASVs) into searchable, structured seagrass data.

- **Habitat Features Identified**  
  - Seagrass presence  
  - Species type (e.g., *Thalassia*, *Syringodium*, *Halodule*)  
  - Canopy density  
  - Structural complexity  
- **Data Fusion**  
  - Video frames are georeferenced and time-synced with acoustic sonar data where possible (e.g., multibeam water column data)  
  - Enables visual confirmation and sonar-based prediction of seagrass structures  

---

### How It Works  
1. **Data Collection**  
   ASV surveys gather sonar and video in shallow coastal zones. Along with potentially other environmental data like DO and PAR. 
2. **Frame Extraction & Annotation**  
   Video is broken into still frames, randomly but methodically by humans, each representing a "unique" habitat, these still frames are annotated using seagrass ID guides and expert advice. Time stamp and other feature data are recorded  
3. **Database Building**  
   Labeled images populate a growing library of known visual features.  
4. **Model Training**  
   Machine-learning algorithms learn to ask:  
   - Is it seagrass or algae?  
   - Which species are present?  
   - How dense is the canopy within this area?  
5. **Integrated Output**  
   Researchers can rapidly process new video, linking each observation directly to its acoustic signature or other data where possible.

---

### Why This Matters  
- **Faster**  
  Cuts down on tedious, frame-by-frame manual review.  
- **Smarter**  
  Improves accuracy of sonar models with real-world visual training data. This tool is tailored to our immediate needs for shallow water habitat mapping. 
- **Scalable**  
  Enables broader habitat classification across vast coastal areas.  
- **Educational**  
  Serves as a hands-on tool for interns and early-career scientists.

---

*By merging AI-driven image recognition with georeferenced sonar, this system sets the stage for fully automated seagrass mapping—where one day sonar alone, informed by AI, will unveil the seafloor’s hidden tapestry.*  




````markdown
## Tutorial: Using the ASV Video Tool

Follow these steps to get up and running with the ASV video processing repository:

### 1. Clone the Repository
```bash
git clone https://github.com/your-org/asv-video-tool.git
cd asv-video-tool
````

### 2. Set Up Your Python Environment

```bash
python3 -m venv venv
source venv/bin/activate   # macOS/Linux
# or on Windows:
venv\Scripts\activate
pip install --upgrade pip
pip install -r requirements.txt
```

### 3. Prepare Your Annotations File

* Open `annotations.csv` in your favorite editor.
* Ensure there’s a `timestamp` column formatted as `HH:MM:SS:FF` (hours\:minutes\:seconds\:frames).

### 4. Extract Video Clips

Use the `show_clip.py` script to pull out a short sample around your timestamp:

```bash
python show_clip.py \
  --video-path path/to/video.mp4 \
  --annotations path/to/annotations.csv \
  --sample-nr 0 \
  --cliplength 10
```

### 5. Tweak Color & Length Settings

* In `show_clip.py`, adjust:

  * `increase_saturation(frame, factor=…)` to fine-tune colors.
  * `cliplength` for longer or shorter clips.
  * `width` for playback size.

### 6. Contribute & Collaborate

1. Create a feature branch:

   ```bash
   git checkout -b feature/your-feature-name
   ```
2. Commit your changes:

   ```bash
   git commit -m "Add awesome feature"
   ```
3. Push and open a pull request:

   ```bash
   git push origin feature/your-feature-name
   ```


