# Krace: Data Race Fuzzing for Kernel File System

* Data races occur when two threads fail to use proper synchronization when accessing shared data. In kernel file systems, which are highly concurrent by design, data races are common mistakes and often wreak havoc on the users, causing inconsistent states or data losses. Prior fuzzing practices on file systems have been effective in uncovering hundreds of bugs, but they mostly focus on the sequential aspect of file system execution and do not comprehensively explore the concurrency dimension and hence, forgo the opportunity to catch data races.

* We bring coverage-guided fuzzing to the concurrency dimension with three new constructs: 
  1. a new coverage tracking metric, alias coverage, specially designed to capture the exploration progress in the concurrency dimension; 
  2. an evolution algorithm for generating, mutating, and merging multithreaded syscall sequences as inputs for concurrency fuzzing;
  3. a comprehensive lockset and happens-before modeling for kernel synchronization primitives for precise data race detection. 

* These components are integrated into KRACE, an end-to-end fuzzing framework that has discovered 23 data races in ext4, btrfs, and the VFS layer so far, and 9 are confirmed to be harmful

* More information here, https://github.com/sslab-gatech/krace 
