[Lyra V2](https://github.com/google/lyra) (SoundStream) running in the browser.

### WIP Web Demos:
 * https://josephrocca.github.io/lyra-v2-soundstream-web/onnx-simple.html
 * https://josephrocca.github.io/lyra-v2-soundstream-web/onnx.html
 * https://josephrocca.github.io/lyra-v2-soundstream-web/tflite.html

### Models:
 * ONNX: https://huggingface.co/rocca/lyra-v2-soundstream/tree/main/onnx
 * TFLite: https://huggingface.co/rocca/lyra-v2-soundstream/tree/main/tflite

### TFLite-to-ONNX conversion:
 * https://colab.research.google.com/gist/josephrocca/401efe82bf18ffe93d5f3deca7ed7515

### Inference Comparison:
 * Python ONNX: https://colab.research.google.com/gist/josephrocca/605006bbeb49df6c9ab7efd18a9cdd0d
 * Web ONNX: https://josephrocca.github.io/lyra-v2-soundstream-web/onnx-simple.html
 * Python TFLite: https://colab.research.google.com/gist/josephrocca/ba3021195dfb4f91ffc7898cea6f8596

### Currently blocked by:
* ONNX:
   * TFLite-to-ONNX conversion process is producing models which don't have matching outputs at inference, except for the quantization decoder model.
* tfjs-tflite:
   * The Lyra 1.2.0 soundstream_encoder model just outputs zeros for some reason, and the 1.3.0 soundstream_encoder model has an infinite loop or something. Need to investigate - latter seems like a tfjs-tflite bug.
   * https://github.com/tensorflow/tfjs/issues/6094#issuecomment-1267870990 (can likely work around this by running each in its own worker, or worst case, in its own iframe)
   
   
### Todo:
 * Update [this thread](https://github.com/onnx/tensorflow-onnx/issues/2059#issuecomment-1285372747) RE correctness when you have both tflite and onnx working.
