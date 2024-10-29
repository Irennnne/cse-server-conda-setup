# CUHK CSE Server - conda setup 環境部署
This repo includes the detailed steps to set up **Miniconda3** using your own cse server account.

## Preparation
Before installing miniconda3, make sure you have enough space in your directory. Use `du -sh .` to check the availability. If you don't have enough space, you can apply for more storage through _CSE intranet>>technical support>>big data storage>>application form_.

## Step 1: Download miniconda
Use`Miniconda3-py38_23.10.0-1-Linux-x86_64.sh` as an example.
```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-py38_23.10.0-1-Linux-x86_64.sh \
chmod +x Miniconda3-py38_23.10.0-1-Linux-x86_64.sh \ #run as a user
./Miniconda3-py38_23.10.0-1-Linux-x86_64.sh
```
press `ENTER` until see `please enter 'yes' or 'no'`.

Enter yes and then you will see sth like this to ask you to confirm your installation:
```
Miniconda3 will now be installed into this location:
/home/username/miniconda3

  - Press ENTER to confirm the location
  - Press CTRL-C to abort the installation
  - Or specify a different location below

[/home/username/miniconda3] >>>
```
You should change the destination to the new directory assigned by CSE if your original directory is out of storage.
`[/home/username/miniconda3] >>> /path/to/your/dir/miniconda3`
## step 2: Configs
```
Preparing transaction: done
Executing transaction: done
installation finished.
Do you wish to update your shell profile to automatically initialize conda?
This will activate conda on startup and change the command prompt when activated.
If you'd prefer that conda's base environment not be activated on startup,
run the following command when conda is activated:
conda config --set auto_activate_base false
You can undo this by running conda init --reverse $SHELL ? [yes|no]
[no] >>> 
```

Here I choose yes to initialize conda automatically.

Run this code and you will see 熟悉的 `(base)` in your command prompt
``` bash
eval "$(/path/to/your/miniconda3/bin/conda shell.bash hook)"
```
Also do this to specify your miniconda3 path.
``` bash
export PATH="/path/to/your/miniconda3/bin:$PATH"
```
-------_done_-------

## Reference
https://kxz18.github.io/2021/01/18/Miniconda/

https://developer.aliyun.com/article/1542746


