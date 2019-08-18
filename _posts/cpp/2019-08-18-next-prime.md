---
layout: post
title:  "Show Next Prime !"
date:   2019-08-18 10:22:41 +0500
categories: posts cpp
---
Performs reversal of integer

```cpp
#include<iostream>
using namespace std;

bool IsPrime(int number);
int NextPrime(int start, int end);

int main(){
	int start = 1;
	int end = 100;
	int prime = NextPrime(start, end);
	while(prime != -1){
		cout<<"Prime Found : "<<prime<<endl;
		prime = NextPrime(prime + 1, end);
	}
	return 0;
}

int NextPrime(int start, int end){
	for(int i = start; i <= end; i++){
		if(IsPrime(i)){
			return i;
		}
	}
	return -1;
}

bool IsPrime(int number){
	if(number == 1){
		return true;
	}
	for(int i = 2; (i * i) < number; i++){
		if(number % i == 0){
			return false;
		}
	}
	return true;
}
```

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
