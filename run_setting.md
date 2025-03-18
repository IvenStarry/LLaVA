需要三个终端

模型启动命令如下：
1. Launch a controller
python -m llava.serve.controller --host 0.0.0.0 --port 1234
2. Launch a gradio web server
python -m llava.serve.gradio_web_server --controller http://localhost:1234 --model-list-mode reload
3. Launch a model worker
python -m llava.serve.model_worker --host 0.0.0.0 --controller http://localhost:1234 --port 40000 --worker http://localhost:40000 --model-path llava-v1.5