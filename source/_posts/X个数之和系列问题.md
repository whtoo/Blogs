---
layout: photo
title: X个数之和系列问题
date: 2020-07-29 15:28:45
tags: 
- Algorithm
- CPP
categories:
- Leetcode & Quiz
---
# 从零开始的算法历险 -- 0x01

## 1. 从两数之和(2-Sum)开始

### 1.1 问题描述

{% blockquote @Leetcode-cn https://leetcode-cn.com/problems/two-sum/description/%}
给定一个整数数组 nums 和一个目标值 target，请你在该数组中找出和为目标值的那 两个 整数，并返回他们的数组下标。

你可以假设每种输入只会对应一个答案。但是，数组中同一个元素不能使用两遍。

示例:

给定 nums = [2, 7, 11, 15], target = 9

因为 nums[0] + nums[1] = 2 + 7 = 9
所以返回 [0, 1]
{% endblockquote %}

### 1.2 问题分析


### 1.3 实现代码
{% include_code lang:cpp from:7 to:25 twosum.cpp %}