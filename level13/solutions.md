# Level 13  - Bandit
**Goal**: Extract the password from a hexdump file that has been repeatedly compressed with multiple algorithms.


## Concepts

**Compression Formats and Commands**: 

| **Format** | **Extension** | **Decompression Command** | **Notes** |
|------------|---------------|---------------------------|-----------|
| **gzip**   | `.gz`         | `gunzip archivo.gz`       | Original file is deleted after decompression |
| **bzip2**  | `.bz2`        | `bunzip2 archivo.bz2`     | Original file is deleted |
| **tar**    | `.tar`        | `tar xf archivo.tar`      | Extracts contents, keeps original |
| **zip**    | `.zip`        | `unzip archivo.zip`       | Original file is kept |

**Hexdump conversion**: Text representation of binary data

**`xxd`**: Command to convert to hexdump (e.g., `xxd archivo.bin > archivo_hex.txt`)

`xxd -r archivo_hex.txt > archivo_recuperado.bin` -> Reverse command, from hexdump to binary

## Extension vs Content

Linux doesn't care about extensions: `file` reads actual content

Add proper extensions to make command work smoothly

## Why Rename Files with Extensions?

- **Visual aid**: Quick identification of file types.

- **Tool compatibility**: Some commands (like `gunzip`) expect specific extensions.

- **Organization**: Helps manage multiple files in complex extraction chains.

## Linux Doesn't Care About Extensions:

- `file` command reads the **magic number** (file signature) not the extension.

- You can decompress without proper extensions, but it requires extra flags:
  ```bash
  gunzip -S "" file_without_extension
```

## Commands used (Workflow for decompression)

1 -> Use `file` to identify actual type -> `file data1`

2 -> Rename with proper extension for clarity and smooth workflow -> `mv data1 data1.gz`

3 -> Use standart decompression command -> `gunzip data1.gz`

4 -> Repeat until finding the oringinal content 
