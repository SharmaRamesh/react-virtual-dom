## Introduction

A simple project to illustrate the advantage of ReactJS's use of virtual DOMs. Virtual DOMs are not a new concept. However, their use in ReactJS is quite effective.

Unlike other rendering libraries or frameworks, React.js uses the notion of a virtual DOM that represents the real HTML DOM (which in turn represents the rendered UI) on a web page.

Any time the objects created using React have a state change, their corresponding sub-trees or nodes are marked dirty by a setState() method. Whenever this happens, ReactJS creates the entire Virtual DOM from scratch which is quite fast. At any given time ReactJS maintains two virtual DOMs - one with the updated state, and the other with the previous state. ReactJS uses observables to find the modified components in the DOMs instead of using a dirty checking process that is used in AngularJS which is less efficient, and reduces the performance as the application grows.

## Steps taken by ReactJS to find the differences in both the Virtual DOMS.

1. Re-render all the children if parent state has changed
2. Use a breadth first search

## Updating the Real DOM

1. [Reconciliation](https://reactjs.org/docs/reconciliation.html) - this is the process to determine which parts of the Real DOM need to be updated.
2. Batch update

## Whats in the sample

Sample inspired by one of the videos in the [Learning ReactJS](https://learning.oreilly.com/videos/learning-reactjs/9781785887079) video series by [Samer Buna](https://medium.com/@samerbuna).

It is a very minimalistic example, which makes it elegant, IMHO. It consists of two files

- index.html
- script.js

## How to test it

Simply download the project and open index.html in your browser. You should see two sections/divs

1. Titled <b>Hello JS</b> this is rendered by manipulating the Real DOM directly. In essence each time this div is rendered, it is rendered in its entirety. It contains two child elements - an input box and a date field that shows the current date and time which gets updated every 1 second.
2. Titled <b> Hello React</b> this is rendered by React. It also has two child elements as above.

The page is set up to re-render every 1 second, thus you will see the time updating every second. However, if you attempt to enter something in the input field in the first div, it is impossible to do so, because the entire div is updated every second, thus clearing out your input.

On the other hand, the second div is updated by React, and it only updates the date/time field every second, since only the state of that field changes every second. This leaves the input field alone and thus you are able to input text into it!

## Attributions

Some of the concepts above are explained in detail at [Virtual DOM in ReactJS](https://hackernoon.com/virtual-dom-in-reactjs-43a3fdb1d130)
