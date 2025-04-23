## 无数次disk quota exceeded
1.可能是因为hugging face 的路径回去原来的目录了，改一下 `export HF_HOME=/path/to/your/quota/directory`

2. pip .cache 的路径也要改
`export PIP_CACHE_DIR=/path/to/your/quota/directory/.cache`

## stable diffusion 坑
- follow [这个链接](https://blog.csdn.net/sheex2012/article/details/138206606)
- 运行代码：`python ./scripts/txt2img.py --prompt "a professional photograph of an astronaut riding a horse" --ckpt ./checkpoints/v2-1_768-ema-pruned.ckpt --config ./configs/stable-diffusion/v2-inference-v.yaml --H 512 --W 512 --device cuda --dpm`
- `--device cuda` 这个得加上不然等一百年
- 不能用太垃圾的显卡， 如果用学校的显卡，最好用NVIDIA GeForce GTX TITAN X及以上的，11G内存的那个跑出来的都是彩色噪声...

## CUDA版本不匹配问题
`RuntimeError: CUDA error: CUBLAS_STATUS_NOT_SUPPORTED when calling `cublasGemmStridedBatchedEx(handle, opa, opb, (int)m, (int)n, (int)k, (void*)&falpha, a, CUDA_R_16BF, (int)lda, stridea, b, CUDA_R_16BF, (int)ldb, strideb, (void*)&fbeta, c, CUDA_R_16BF, (int)ldc, stridec, (int)num_batches, compute_type, CUBLAS_GEMM_DEFAULT_TENSOR_OP)`
- 原本我的环境是ok的，但是可能是因为用学校的节点，没有指定之前装环境用的那个节点。
- 所以最好用那个一开始用的那个环境来跑， 比如我就是用 `srun --gres=gpu:1 -w projgpu33 --pty /bin/bash`
