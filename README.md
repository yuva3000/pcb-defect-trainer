# PCB Defect Trainer

Static website: train the c8-c16-c32 PCB defect CNN in the browser (TensorFlow.js, WebGL), quantize it to INT8 and
download the ROM weight files (`hardware_weights/*.mem`, `rtl/generated/*.sv`, `checkpoints/quantized_model.npz`)
for the 14-pin accelerator RTL. No server or build step: everything runs in the visitor's browser.

## Deploy on Vercel

**Option A - drag and drop (no Git):**
1. Install the CLI once: `npm i -g vercel`
2. In this folder run `vercel` and log in when asked, accept the defaults (no build command, output = this folder).
3. Run `vercel --prod` to get the production URL (e.g. `https://pcb-defect-trainer.vercel.app`).

**Option B - from GitHub:**
1. Push this folder to a GitHub repository.
2. On vercel.com choose **Add New -> Project**, import the repository.
3. Framework preset: **Other**. Leave build command and output directory empty. Click **Deploy**.

## Files
- `index.html` - the whole application (TensorFlow.js 4.20.0 and JSZip 3.10.1 load from jsDelivr / cdnjs).
- `vercel.json` - static hosting settings.
