---
author: 
categories:
date: 
draft: false
excerpt: Optimize call center employees allocation with genetic algorithms
layout: single
links:
subtitle: Optimize call center employees allocation with genetic algorithms
tags:
- hugo-site
title: Call Centers & Genetic Algorithms
---

### High Level Overview

##### Client

Developed a solution for an Italian company that provides other companies with qualified virtual assistants to support their customers.   

##### Problem

They were looking for a way to automate the insertion of breaks in their [turn allocation matrix](https://patents.google.com/patent/WO1999060766A1/en), taking into considerations some constraints on the employees contract type (part-time, full-time) and role (team leader, inbound agent).   

##### Solution

A genetic algorithm that takes in input the turn allocation matrix with no breaks allocated and generates a high number of constraints-compliant assignments at each iteration.   
The fitness function takes into consideration an *understaffing* term and an *ovestaffing* term, giving more importance to samples that minimize such quantities.
