---
layout: default
title: OOP Basics
parent: OOP
---

অবজেক্ট ওরিয়েন্টেড প্রোগ্রামিং এর মেইন প্রিন্সিপাল ৪ টা। আমি যেভাবে মনে রাখতে চেষ্টা করছি।

**Class** = blueprint of homes

**Objects** = homes, what's instantiated from Class

**১। Abstractions:**

এটি Class এবং Objects এর মধ্যে প্রয়োজনীয় ডাটা দেখায় এবং অপ্রয়জনীয় ডাটা হাইড করে।

**২। Encapsulation:**

এটি Class এবং Objects এর মধ্যের প্রাইভেট ডাটা গুলোকে প্রাইভেট করে রাখে, যার ফলে তা পাব্লিকালি ব্যবহার করা যাবে না।

**৩। Inheritance:**

সম্পর্ক তৈরি করে। ধরা যাক, আমাদের একটি User(parent class) আছে, Admin(child class) এবং Author(child class) দুজনই প্যারেন্ট ক্লাস থেকে Inherited. অর্থাৎ এখানে hierarchical relationship.

**৪। Polymorphism:**

এটি একটি মেথড কে পুনরায় লিখতে পারে অর্থাৎ overwrite করতে পারে। আগের মত, ধরা যাক, আমাদের একটি User(parent class) আছে, Admin(child class) এবং Author(child class) দুজনই(our homes, what's come from blueprint) প্যারেন্ট ক্লাস থেকে Inherited.

সে ক্ষেত্রে দুজন চাইল্ড, প্যারেন্ট এর থেকে মেথড(লগিন,সেন্ডমেছেজ) গুলো তাদের Prototypes এ পেয়ে গিয়েছে। কিন্তু Admin ভাবছে কি আমার লগইন মেথড টা আরো সিকিউর করতে হবে, তখন সে মেথডটি overwrite করে আনন্দিত হল।
ওহ হ্যাঁ, সকল চাইল্ড ক্লাস দেরও নিজেদের মেথড থাকতে পারে।

Source: Talk.js FB Group
