Member 1 → mkfs_builder (Filesystem Creator)

Implement CLI parsing for --image, --size-kib, --inodes.

Compute layout (superblock, bitmaps, inode table, data region).

Initialize superblock, bitmaps, and root directory inode.

Write the complete image to disk.

Deliverable: a working mkfs_builder.c that produces a valid .img.




Member 2 → mkfs_adder (File Inserter)

Implement CLI parsing for --input, --output, --file.

Open and validate input image.

Implement first-fit allocation (new inode + free data blocks).

Write file contents, create directory entry, update root inode.

Handle edge cases (no space, file > 12 blocks).

Deliverable: a working mkfs_adder.c that adds files into the root directory.





Member 3 → Shared Infrastructure & QA

Complete struct definitions (superblock_t, inode_t, dirent64_t) in both skeletons.

Write bitmap helpers (set/test/clear bit, find first free).

Integrate checksums (superblock_crc_finalize, inode_crc_finalize, dirent_checksum_finalize).

Implement error handling (bad CLI, invalid parameters, out of space).

Test everything: run builder → add sample files → inspect with xxd/HxD → confirm correctness.

Deliverable: helper code + tests + final integration; ensure both programs compile and run smoothly.
