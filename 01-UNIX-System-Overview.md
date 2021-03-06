# UNIX System Overview

## Introduction

Actually, the Operating System (or OS) is a program that runs programs. For example, some people like play games like the PUBG, We all know that this game is essentially a program, so you may need a palce to run this game program, such as a xbox, PC even a mobile phone. So there are different operating systems support you to run this game with different experience by gamepad, keyboard & mouse or a touch screen. The focus of this text is to describe that OS is a program that provide various basic services and ability to run programs.

As web browsers' user, you may wanna ask if the  browser is OS or not. Well, let see, you could tweets with both Twitter.com (on browsers) and it's App (on Android, iOS or  other operating systems), it seems like the browser is on the same level  like OS.

However, browser is not OS. Cause a web browser never has ability for websites to directly interact with hardware. The OS, as software, provide more basic functions, such as reading or  writting files on your hard disk, controlling peripherals devices like a keyboard, and allowing your programs to understand what you want when you press the keyboard, click the mouse or tap the touchscreen. Well, what if we provide these basic functions to a browser? Does it become OS?

It become true in the case of Chrome OS, where the browser itself is still separate from the OS kernel, though it doesn't appear so. But  it's enough for us to dream about the next generation of OS, with very thin layer of  hardware and full-energy of cloud services.

Popular operating systems you heard might be Windows Mac or Linux. While UNIX sounds like a unfamiliar OS and historical or may be old in someone's  opinion, why we should learn Unix instead of formers?

In fact, Unix is a family of multitasking, multiuser computer operating systems that including BSD, Mac OSX, Linux and so on. With the huge family of operating systems, it could help us to learn from more orginal system. I bet you will be interested.

Learn the Unix system  with traditional C language and old-fashioned descriptions, is a  difficult task (and could require many extra learning that can be avoid). This chapter provides a encapsulated tour of Unix System from JavaScript programmer's perspective.

We’ll give some brief JavaScript code examples of terms and concepts that used to be describeb by C. We'll talk about these features in much more detail in later chapters. This chapter also provides an introduction to and overview of the functions provided by the Unix System for programmers new to this environment.

## UNIX Architecture

As we mentioned before, operating system managers your hardware resources. So, there is a very clear relationship between hardware and software, that's a bridge suspending at middle which is usually called **kernel**.

```text
┌──────────────┐
|   Software   |
└──────────────┘
    | |  | |
    |kernel|
    | |  | |
┌──────────────┐
|   Hardware   |
└──────────────┘
```

Due to the events like [Zero-day attack](https://en.wikipedia.org/wiki/Zero-day_(computing)), you can always find reasons to upgrade a lot of things named patch or feature to our OS. Therefore, it's no doubt that kernel is  implemented as software. But, we still dislike the frequent updating, so the great programmers try hard to make it as small as possible, which means beautiful and stable.

So, the kernel become a program which is the small but core part of a operating system, with miracly complete control over everything in the system (Dftba, LOL).

On most systems, kernel is one of the first programs loaded on start-up. It handles the rest of start-up as well as input/output requests from software, translating them into data-processing instructions for the CPU. It handles memory and peripherals like keyboards, monitors, printers, and speakers (open [wiki](https://en.wikipedia.org/wiki/Kernel_(operating_system)) for more).

```text
┌────────────────────────────┐
|        Application         |
└────────────────────────────┘
             |  |
┌────────────────────────────┐
|        k e r n e l         |
└────────────────────────────┘
   | |       |  |       | |
┌───────┐ ┌────────┐ ┌───────┐
| C P U | | Memory | |Devices|
└───────┘ └────────┘ └───────┘
```

There is only way for applications to use the computer resources encapsulated by kernel is *System Call*, which provided by kernel the same time.
