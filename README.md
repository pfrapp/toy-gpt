# toy-gpt
Toy Example ChatGPT

## Original source

I follow along this video by A.K.
https://www.youtube.com/watch?v=kCc8FmEb1nY

## venv

The venv associated with this project
is in ~/venv/toygpt

Create and activate via
```
	$ python3 -m venv ~/venv/toygpt
	$ . ~/venv/toygpt/bin/activate
```

On Linux with and nvidia card and CUDA 12.2, install pytorch via
```
	$ pip3 install numpy
	$ pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu122
```

If you want to play around with the tokenizer, install it via
```
	$ pip3 install tiktoken
```
## Tokenization

Try this code yourself
```
	>>> import tiktoken
	>>> enc = tiktoken.get_encoding('gpt2')
	>>> enc.n_vocab
	    --> This gives you 50257
	    # Encode
	>>> enc.encode("Hello world")
	    --> This gives you [15496, 995]
	    # Decode
	>>> enc.decode([15496, 995])
	    --> This gives you "Hello world"
```

A large vocabulary size allows for short sequences of integers.
A small vocabulary size results in a larger sequence of integers.
In our example code, we encode on character level. That is, we have a small vocabulary
and hence a rather large sequence of integers.


