# AgriVision AI — GitHub Pages UI

A responsive static recreation of the Gradio AgriVision AI interface, based on the supplied `crop_disease_demo.ipynb` design and verified project metrics.

## Included
- `index.html` — page structure
- `styles.css` — responsive dark-green agricultural theme
- `script.js` — local image preview, drag-and-drop, sample-category cards and honest API-not-connected state
- `.github/workflows/deploy.yml` — deploy to GitHub Pages on pushes to `main`

## Deploy
1. Copy the contents of this folder into the root of your GitHub repository.
2. Ensure the default branch is `main` (or update `.github/workflows/deploy.yml` if it differs).
3. On GitHub, open **Settings → Pages → Build and deployment → Source**, then select **GitHub Actions**.
4. Commit/push the files to `main`; open **Actions** and wait for the deployment workflow to finish.
5. Your URL will be `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/`.

## Important: model inference is not connected yet
GitHub Pages only serves static files; it does not execute the notebook, Python, TensorFlow Lite or the model. This UI supports image selection and preview but deliberately does not fabricate predictions. To enable real top-5 results, connect the JavaScript frontend to a separately hosted API that loads `plant_disease_mobilenetv2_quantized.tflite` and `labels.txt`.

## Reported project metrics shown in the UI
- Fine-tuned Keras model test accuracy: 92.55%
- Classification categories: 17
- Quantized TFLite model size: 2.41 MB

The model scores are not necessarily calibrated probabilities; predictions should be verified with an agricultural expert.
