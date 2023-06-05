# WebAssembly Basics

![WebAssembly Logo](https://avatars.githubusercontent.com/u/11578470?s=200&v=4)

This repository contains information, references, and samples about running
WebAssembly (Wasm) outside the browser.

## WebAssembly: Why? What?

### Wasm in the browser

[WebAssembly](https://webassembly.org/) (Wasm) is a technology that allows you
to compile code written in over 40+ languages and run it inside sandboxed
environments in a fast, efficient, and safe way. The original use cases were
focused on running native code in web browsers and supported by all major
browsers. For example, there are frameworks like Blazor that enable running C# /
ASP.NET code in the browser running on .NET runtime implemented in WebAssembly.

### Wasm outside the browser

More recently, there’s an attempt to get WebAssembly run outside the browser
with the [WASI](https://wasi.dev/) project. The idea is instead of running apps
as VMs or containers, you can run them as faster, smaller, more secure, and more
portable WebAssembly modules:

* **Faster**: Wasm apps start 10x to 500x faster than containers with no cold-start. 
* **Smaller**: A HelloWorld Rust app in Wasm is 10x smaller than in an OCI container.
* **More secure**: Containers execute in an allow-by-default model whereas Wasm apps execute in a deny-by-default sandbox.
* **More portable**: A container built for `linux/amd64` won’t work on `windows/amd64` or even `linux/arm64`. Wasm creates a single `wasm32/wasi` module that runs everywhere in a Wasm runtime on any host. 