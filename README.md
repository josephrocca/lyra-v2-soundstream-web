[Lyra V2](https://github.com/google/lyra) (SoundStream) running in the browser.

### WIP demos:
 * https://josephrocca.github.io/lyra-v2-soundstream-web
 * https://josephrocca.github.io/lyra-v2-soundstream-web/onnx.html
 

Models: https://huggingface.co/rocca/lyra-v2-soundstream

tflite-to-onnx conversion: https://colab.research.google.com/gist/josephrocca/401efe82bf18ffe93d5f3deca7ed7515/notebook.ipynb

### Currently blocked by:

* tfjs-tflite:
   * https://github.com/tensorflow/tfjs/issues/6094#issuecomment-1267870990
   * https://github.com/tensorflow/tfjs/issues/6919
* onnx:
   * https://github.com/microsoft/onnxruntime/issues/13383
   * https://github.com/onnx/tensorflow-onnx/issues/2066
   
   
### Todo:

 * Update [this thread](https://github.com/onnx/tensorflow-onnx/issues/2059#issuecomment-1285372747) RE correctness when you have both tflite and onnx working.
