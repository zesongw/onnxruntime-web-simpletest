# Simple test to run onnxruntime-web with float16 adn float32 model
Copy onnxruntime web to current folder with:
```bash
cp -r <onnxruntime-path>/js/web/dist ./onnxruntime-web
```
The model can be converted to fp16 by [onnxconverter-common](https://github.com/microsoft/onnxconverter-common)

This simple test will generate random inputs and compare the result of different EP.

WebNN option `deviceType` can be `'cpu'|'gpu'`, but fp16 is only supported in `'gpu'` for now.

I use [float16](https://www.jsdelivr.com/package/npm/@petamoriken/float16) for fp16 data as input and the printed result has been transferred to fp32.

To run a fp32 or fp16 model, use `run()` or `run16()` with modelpath, inputs name, outputs name and inputs shape.

Host this folder with http-sever or serve with
`
http-server .
`
