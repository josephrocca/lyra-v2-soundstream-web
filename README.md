### Looks like someone beat me to it! → https://github.com/shiguredo/lyra-wasm

### Just found another → https://github.com/neuvideo/lyra-js

IIUC, the above-linked repos are direct Emscripten ports of the C++ Lyra code - so they don't use [TFjs-TFLite](https://github.com/tensorflow/tfjs/tree/master/tfjs-tflite) or [ONNX Runtime Web](https://github.com/microsoft/onnxruntime/tree/main/js/web). They seem to work great, so I'll probably not update this repo unless it turns out it'd be handy to have a WebGL version, or if there's reason to believe that using TFjs-TFLite or ONNX Runtime Web would be significantly faster in general.

---

[Lyra V2](https://github.com/google/lyra) (SoundStream) running in the browser.

### WIP Web Demos:
 * https://josephrocca.github.io/lyra-v2-soundstream-web/onnx-simple.html
 * https://josephrocca.github.io/lyra-v2-soundstream-web/tflite-simple.html
 * https://josephrocca.github.io/lyra-v2-soundstream-web/onnx.html
 * https://josephrocca.github.io/lyra-v2-soundstream-web/tflite.html

### Currently blocked by:
* ONNX:
   * TFLite-to-ONNX conversion process is producing a LyraGAN ORT model which doesn't have matching outputs between ONNX Web and ONNX Python runtimes at inference. https://github.com/microsoft/onnxruntime/issues/13670
   * TFLite "VAR" ops conversion issues? https://github.com/onnx/tensorflow-onnx/issues/2059#issuecomment-1317139150 and https://github.com/google/lyra/issues/99#issuecomment-1318229554
* tfjs-tflite:
   * Errors (and infinite loop if cross-origin isolated) on soundstream_encoder: https://github.com/tensorflow/tfjs/issues/7055
   * https://github.com/tensorflow/tfjs/issues/6094#issuecomment-1267870990 (can likely work around this by running each in its own worker, or worst case, in its own iframe)

### TFLite-to-ONNX conversion:
 * https://colab.research.google.com/gist/josephrocca/401efe82bf18ffe93d5f3deca7ed7515

### Inference Comparison:
 * Python ONNX: https://colab.research.google.com/gist/josephrocca/605006bbeb49df6c9ab7efd18a9cdd0d
 * Web ONNX: https://josephrocca.github.io/lyra-v2-soundstream-web/onnx-simple.html
 * Python TFLite: https://colab.research.google.com/gist/josephrocca/ba3021195dfb4f91ffc7898cea6f8596
 
 ### Models:
 * ONNX: https://huggingface.co/rocca/lyra-v2-soundstream/tree/main/onnx
 * ORT: https://huggingface.co/rocca/lyra-v2-soundstream/tree/main/ort
 * TFLite: https://huggingface.co/rocca/lyra-v2-soundstream/tree/main/tflite
   
### Todo:
 * Update [this thread](https://github.com/onnx/tensorflow-onnx/issues/2059#issuecomment-1285372747) RE correctness when you have both tflite and onnx working.
