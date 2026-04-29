This repo contains bundled binaries for llvm 21 built on rocky linux 8. Also contained in this repo is the bundle split up in three ways.

In split100, the tarball was split into 100MB files. In split50, the tarball was split into 50MB files. In split10, the tarball was split into 10MB files.

To recreate the original tarball out of the parts in a split folder, navigate into the split folder and run this command: `cat part_* > llvm21.1.8.tar.xz`

This will recreate the tarball which can then be unzipped using: `tar -xf llvm21.1.8.tar.xz`

**IMPORTANT NOTE**

It is possible to checkout this repo normally, but it will take a long time and download many large files which could be unnecessary. The most efficient way to access the tarball from this repo is to download only a single split folder and then recreate it as laid out above. To checkout only one split folder (split10 in this example) run these commands:

`git clone --filter=blob:none --no-checkout github.com/andre-mig/llvm21`

`cd llvm21`

`git sparse-checkout init --cone`

`git sparse-checkout set split10`

`git checkout`
