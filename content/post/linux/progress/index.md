+++
author = "Feiyizhou"
title = "Linux进程创建流程"
date = "2023-04-24"
description = "从内核源码函数顺序过程分析Linux进程创建的整理流程"
tags = [
"Linux",
"kernel",
"progress",
]
categories = [
"Linux",
"kernel",
"progress",
]
series = ["Linux kernel source code analyse"]
aliases = ["Linux kernel source code analyse"]
image = "linux.jpg"
comments = true
hidden = true
+++

# 进程的结构体定义
在版本为3.10.0-1160.el7的内核源码中，进程的结构体定义在文件`include/linux/sched.h`中，省略部分字段定义，本文关心的属性定义如下所示：

```h
struct task_struct {
    //2.1 进程状态 
    volatile long state;	/* -1 unrunnable, 0 runnable, >0 stopped */

    //2.2 进程线程的pid
    pid_t pid;
    pid_t tgid;

    //2.3 进程树关系：父进程、子进程、兄弟进程
    struct task_struct __rcu *real_parent; /* real parent process */
    struct task_struct __rcu *parent; /* recipient of SIGCHLD, wait4() reports */
    struct list_head children; 
    struct list_head sibling;
    struct task_struct *group_leader; 

    //2.4 进程调度优先级
    int prio, static_prio, normal_prio;
    unsigned int rt_priority;

    //2.5 进程地址空间
    struct mm_struct *mm, *active_mm;

    //2.6 进程文件系统信息（当前目录等）
    struct fs_struct *fs;

    //2.7 进程打开的文件信息
    struct files_struct *files;

    //2.8 namespaces 
    struct nsproxy *nsproxy;
}
```

## 进程状态
## 进程pid
## 进程地址空间

