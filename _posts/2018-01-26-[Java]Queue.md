---
layout: default
title: [Java]Queue
---

{{ page.title }}
================

	static class Queue{
		int head;
		int tail;
		int data[][];
		Queue(){
			head = 0;
			tail = 0;
			data = new int[SIZE][2];
		}
		boolean isEmpty(){
			return head == tail;
		}
		int[] pop(){
			int result[] = data[head % SIZE];
			head++;
			return result;
		}
		void push(int x, int y){
			data[tail % SIZE][0] = x;
			data[tail % SIZE][1] = y;
			tail++;
		}
	}