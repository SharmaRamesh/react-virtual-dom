## Introduction

A simple project to illustrate the advantage of React.js's use of virtual DOMs. Virtual DOMs are not a new concept. However, their use in React.js is quite effective.

Unlike other rendering libraries or frameworks, React.js uses the notion of a virtual DOM that represents the real HTML DOM (which in turn represents the rendered UI) on a web page.

Any time the objects created using React have a state change, their corresponding sub-trees or nodes are marked dirty by a setState() method. Whenever this happens, ReactJS creates the entire Virtual DOM from scratch which is quite fast. At any given time ReactJS maintains two virtual DOMs - one with the updated state, and the other with the previous state. ReactJS uses observables to find the modified components in the DOMs instead of using a dirty checking process that is used in AngularJS which is less efficient, and reduces the performance as the application grows.

## Steps taken by ReactJS to find the differences in both the Virtual DOMS.

1. Re-render all the children if parent state has changed
2. Use a breadth first search
3. [Reconciliation](https://reactjs.org/docs/reconciliation.html) - this is the process to determine which parts of the Real DOM need to be updated.
4. Batch update

## Whats in the sample

Sample inspired by one of the videos in the [Learning ReactJS](https://learning.oreilly.com/videos/learning-reactjs/9781785887079) video series by [Samer Buna](https://medium.com/@samerbuna).

It is a very minimalistic example, which makes it elegant, IMHO. It consists of two files

- index.html
- script.js
