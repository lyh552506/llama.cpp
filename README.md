# llama.cpp

## **llama.cpp for riscv**

**Riscv-build**


```shell
cmake -B build-riscv \
-DCMAKE_SYSTEM_NAME=Linux \
-DCMAKE_SYSTEM_PROCESSOR=riscv64 \
-DCMAKE_C_COMPILER=riscv64-unknown-linux-gnu-gcc \
-DCMAKE_CXX_COMPILER=riscv64-unknown-linux-gnu-g++ \
-DCMAKE_BUILD_TYPE=Debug \
-DBUILD_SHARED_LIBS=OFF \
-GNinja

cmake --build build-riscv
```

**Docker Pull:**

```shell
docker run --platform linux/riscv64 -it drujensen/riscv-ubuntu bash
```

Optionally , you can mount a local directory by using  `-v`:

```shell
docker run --platform linux/riscv64 -v ${Your Local File}:${Continer File} -it drujensen/riscv-ubuntu bash
```

**how to use :**

here is some example:

```shell
# Prompt given by user
${workspaceFolder}/build-riscv/bin/llama-cli -m DeepSeek-R1-Distill-Qwen-1.5B-Q2_K_L.gguf -p "Hello"

# Prompt given by file (better to use when do perf)
${workspaceFolder}/build-riscv/bin/llama-cli -m DeepSeek-R1-Distill-Qwen-1.5B-Q2_K_L.gguf -f ./prompt.txt
```