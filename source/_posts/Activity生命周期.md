---
title: Activity生命周期
reward: false
tags: Android基础知识
---

Activity生命周期 一些不太寻常的要点
<!--more-->

 - 从Activity A启动Activity B
   onPause(A) --> onCreate(B) --> onStart(B) --> onResume(B) --> onStop(A)
   所以耗时的数据保存工作最好在onStop方法里进行，避免在启动新的Activity的过程中出现卡顿的问题。
   但是在有些时候onStop方法并不会在启动别的Activity的时候或按Home键之后执行，原因是采用了透明主题。
 - 当Activity A采用了透明主题时
   从Activity A启动Activity B，不会执行onStop(A)过程