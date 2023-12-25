# rust_candle_noodling

I'm trying out huggingface's new candle library for machine learning in Rust, following the [documentation](https://huggingface.github.io/candle/index.html)

I'm not an expert in any of this, so this is learning in public.

I'm using google colab for my environment, which is a cheap way to get gpus. This should also work in kaggle, or other gpu providing environments.

Check you have an nvidia gpu:

```
!nvcc --version
```

```
!nvidia-smi --query-gpu=compute_cap --format=csv
```

Install the rust toolchain:
```
!apt install cargo
```

Make a new Rust app:

```
!cargo new myapp
%cd myapp
```

Add candle to your app:
```
!cargo add --git https://github.com/huggingface/candle.git candle-core --features "cuda"
```

This produced an error for me,  'error: unrecognized feature for crate candle-core "cuda"', but the next step to verify the app worked, so I'm pressing on. 

```
!cargo build
```

I'm now at the sample app stage (https://huggingface.github.io/candle/guide/hello_world.html) hello world in MNIST.

The src/main.rs contains the initial app.

Notes: It uses f32, which in late 2023 is huge, but also for this tiny model, not a problem.

I believe ? means the operation may fail or not produce a result. [1] Yeah, it's error propagation.

[1](https://doc.rust-lang.org/book/appendix-02-operators.html)

## Compiling
