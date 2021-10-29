# zulip2TIL

Repository to extract stream help topic TIL from CodeRefinery zulip chat to keep history

- code to extract info `get-history.py` is from [zulip python api example](https://github.com/zulip/python-zulip-api/commit/26c85bb9ed2b2073eccafc263ea99abc64d982b2#diff-876ba800b4756c48d39d38d4fb37223e2e6f4436f2ea3777b665cef6d6e856b5).


## Installation and usage

- create new conda environment (from miniconda3)

```
conda create -n zulip python 
conda activate zulip
```

- Install zulip Python API:

```
pip install zulip
```

- Configure zulip api by creating a config file `$HOME/.zuliprc`

```
[api]
key=your_zulip_api_key
email=your_email_address
site=coderefinery.zulipchat.com
```
Make sure to set the key and email address properly. See [Configuring the Python bindings](https://zulip.com/api/configuring-python-bindings)

- Execute code to fetch history

```
./get-history.py --stream help --topic TIL --filename zulip_history.json --config-file $HOME/.zuliprc
```

The result will be in `zulip_history.json`.

## Formatting

- We will want to have a page similar to [https://www.wezm.net/v2/posts/2020/100-rust-binaries/](https://www.wezm.net/v2/posts/2020/100-rust-binaries/).
