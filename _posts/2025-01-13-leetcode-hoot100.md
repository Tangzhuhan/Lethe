---
layout: post
title: Leetcode record
subtitle: Leetcode Hot100 using c++
author: Lethe
categories: leetcode c++
banner:
  #video: https://vjs.zencdn.net/v/oceans.mp4
  loop: true
  #volume: 0.8
  #start_at: 8.5
  image: /img/leetcode-1.jpg
  opacity: 0.618
  background: "#000"
  height: "100vh"
  min_height: "38vh"
  heading_style: "font-size: 4.25em; font-weight: bold "
  subheading_style: "color: gold"
tags: leetcode c++
top: 1
sidebar: []
---

## Introduction

* 刷题的过程中感觉知识没进脑子，遂尝试记笔记

## 哈希

* 两数之和

    **给定一个整数数组 nums 和一个整数目标值 target，请你在该数组中找出 和为目标值 target的那两个整数，并返回它们的数组下标。你可以假设每种输入只会对应一个答案，并且你不能使用两次相同的元素。**

    note : <br>
        1.创建哈希表 'unordered_map< int, int > map' 前一个是键(key), 后一个是值(value)<br>
        2.key: 用于标记每一个元素，键是唯一的，每个键只能对应一个值。<br>
        3.value: 与键关联的数据，值可以是任意类型的数据。<br>
        4.map.find(): find方法用于查找给定key的value，如果找到z了，find()会返回一个指向该键值对的迭代器；没找到，find()返回end迭代器<br>
        5.map.insert(): 插入单个键值对，如果键已经存在，操作不执行。<br>


    ```c++
    class Solution {
    public:
        vector<int> twoSum(vector<int>& nums, int target) {
            std::unordered_map<int,int> map;
            for (int i=0; i < nums.size();i++){
                auto iter = map.find(target-nums[i]);
                if(iter!=map.end()){ //map.end():当没找到的时候返回
                    return {iter->second, i}; //second: 指向value
                }

                map.insert(pair<int,int>(nums[i],i));
            }
            return {};
            
        }
    };
    ```

* 字母异位词分组

    **给你一个字符串数组，请你将 字母异位词 组合在一起。可以按任意顺序返回结果列表。字母异位词 是由重新排列源单词的所有字母得到的一个新单词。**

    note : <br>
    1.

    ```c++
    class Solution {
    public:
        vector<vector<string>> groupAnagrams(vector<string>& strs) {
            unordered_map<string, vector<string>> mp;
            for (string& str: strs) {
                string key = str;
                sort(key.begin(), key.end());
                mp[key].emplace_back(str);
            }
            vector<vector<string>> ans;
            for (auto it = mp.begin(); it != mp.end(); ++it) {
                ans.emplace_back(it->second);
            }
            return ans;
        }
    };

    ```

