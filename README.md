# llama2_api

#### api.py: a flask for llama2

```
# run the code with flask
torchrun --nproc_per_node 1 api.py  --ckpt_dir /home1/llms/llama2-weights/llama-2-7b-chat/ --tokenizer_path /home1/llms/llama2-weights/tokenizer.model --max_seq_len 512 --max_batch_size 4
```

#### run_api.sh: deploying llama2 api in public

```
./run_api.sh
```

- HOST: 127.0.0.1
- PORT: 5000
- MODEL: '7b-chat'
- MAX-SEQ_LEN: 1024
- MAX-BATCH_SIZE: 4
- NPROC_PER_NODE: 1

#### request in python

```
import requests
print(requests.post('http://10.236.11.64:5000/chat', json={'messages':[{"role": "user", "content": "hi"}] }).text)
```
