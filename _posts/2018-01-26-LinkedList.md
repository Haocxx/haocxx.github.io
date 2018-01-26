---
layout: default
title: LinkedList
---

{{ page.title }}
================

	static void initHead(Node head){
		head.next = head;
		head.pre = head;
	}
	
	static void insert(Node target, int value){
		Node newNode= new Node();
		newNode.value = value;
		newNode.pre = target;
		newNode.next = target.next;
		target.next = newNode;
		newNode.next.pre = newNode;
	}
	
	static void insertSort(int value){
		Node cur = head.next;
		while(cur != head){
			if(cur.value >= value){
				insert(cur.pre, value);
				return;
			}else if(cur.next == head){
				insert(cur, value);
				return;
			}
			cur = cur.next;
		}
		insert(head, value);
	}
	
	static class Node{
		Node pre;
		Node next;
		int value;
	}