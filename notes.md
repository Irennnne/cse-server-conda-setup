### disk quota exceeded
1.可能是因为hugging face 的路径回去原来的目录了，改一下 `export HF_HOME=/path/to/your/quota/directory`

2. pip .cache 的路径也要改
`export PIP_CACHE_DIR=/research/d2/fyp24/jmyu1/.cache`

