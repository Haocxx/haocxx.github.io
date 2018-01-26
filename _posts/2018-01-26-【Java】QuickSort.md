---
layout: default
title: [Java]QuickSort
---

{{ page.title }}
================

public class QuickSort {
	static int map[];

	public static void main(String[] args) {
		Scanner in = new Scanner(System.in);
		map = new int[10];
		for(int i = 0; i < 10; i++)
			map[i] = in.nextInt();
		quickSort(0,9);
		for(int i = 0; i < 10; i++){
			System.out.println(map[i] + " ");
		}
		in.close();
	}
	
	static void swap(int x, int y){
		int temp = map[x];
		map[x] = map[y];
		map[y] = temp;
	}
	
	static void quickSort(int l, int r){
		if(l >= r)
			return;
		int pos = runQSort(l, r);
		quickSort(l, pos - 1);
		quickSort(pos + 1, r);
	}
	
	static int runQSort(int l, int r){
		int x = l;
		int key = map[l];
		for(int y = l + 1; y <= r; y++){
			if(map[y] < key){
				x++;
				swap(x, y);
			}
		}
		swap(l, x);
		return x;
	}
}