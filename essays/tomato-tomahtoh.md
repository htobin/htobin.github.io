---
layout: essay
type: essay
title: tomato tomahtoh
# All dates must be YYYY-MM-DD format!
date: 2018-02-07
labels:
  - Javascript
  - IntelliJ
---
<img class="ui medium centered rounded image" src="../images/tomato.png">

After about two semesters of coding. I've already begun to pick up on how to write code properly. By writing code properly, I mean commenting on most of the lines. For example:

```
public E add(String key, E value) {
		// make a variable to store the head
		KeyedNode<E> current = head;
		E result = null;
		// if list size is currently zero, no nodes!
		if (size == 0) {
			// make a node assign to head
			head = new KeyedNode<E>(key, value);
			size++;
		}
		// if there is a node(s)
		else {
			//we go into the list
			for (int i = 0; i < size; i++) {
				//if keys are the same
				if (current.getString().compareToIgnoreCase(key) == 0) {					
					//set the data of the older vaule as the key
					result = current.getData();
					current.setData(value);
					size++;
					return result;
				}
				// if current is lower in the alphabet than key
				else if (current.getString().compareToIgnoreCase(key) < 0) {
					
					// create a new node
					KeyedNode<E> newNode = new KeyedNode<E>(key, value);
					
					//check if there's another node
					if (current.getNextKNode() != null) {
						//if the next node is greater than current key then go into this loop
						if (current.getNextKNode().getString().compareToIgnoreCase(key) > 0) {
							//set the new node to reference the next
							newNode.setNextKNode(current.getNextKNode());
							//current node will reference the new one
							current.setNextKNode(newNode);
							size++;
							return null;
						}
					} else if (current.getNextKNode() == null) {
					  current.setNextKNode(newNode);
					  size++;
					  return null;					  
					}
					//set the new node to be after the current node
					current = current.getNextKNode();					
				}
			}
		}
		return null;
	}
```
This was an add function that I used for an ordered linked list data structure. I commented nearly every line for two reasons: 1) I didn't want to lose my train of thought, and 2) I wanted to make sure that if I ran into an issue, that I could send it to either a TA or the professor teaching the class and have them help me. This commenting also helped my fellow peers assist me with my development of algorithms. Another way to type "clean code" was tab spacing. I was pretty spoiled with the IDE eclipse, which had a function that cleaned up all of my tabs, and even when it came to making new lines as well. But I also think it's fair to say that my code that I've typed is not as efficient as it could be. There's a high reverence for those who can type as few lines of code as possible, and maybe with another couple of years I will also be able to find ways to tighten up my typing.

With my introduction to javascript, we didn't use a local IDE in order to type up code. We used a cloud based IDE with JS fiddle. The conclusion of our use of JS Fiddle allowed me to learn javascript while not really worrying too much about certain habits. Such as when using an arrow functions like filter:
```
_.filter(array, elements => {
return something});
```
Functional programming within itself can be a little finicky at times, but overall JS fiddle allowed me to find a style that would allow me to get comfortable with basic javascript functions. But it was when I was introduced to IntelliJ that I would learn that even if the syntax is right, if you're using eslint then it's wrong. 
<img class="ui medium centered rounded image" src="../images/error.jpg">
This is our first week using IntelliJ, and when it was intially introduced I was told it would be like Eclipse. It's very similar with the hot keys, it's even good at telling you what errors you have. One thing I noticed about IntelliJ was that it doesn't open multiple projects at the same time in the same window, which is one aspect of Eclipse that I liked. But one cool think that I thought was pretty neat was the wrapping feature that can be activated in IntelliJ, as in coding screen real estate is highly valuble. So overall I think IntelliJ is a great tool when it comes to finding errors in your code, and it takes a bit getting used to, but the learning curve isn't too bad. But then there's eslint, and holy MOLY! This little library drives me nuts. Eslint is one of the files that we use in order to find errors within our code. The problem is that it picks up a lot of errors. For example, here is my final code I did for a practice with IntelliJ and functional programming
```
const input = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

function squared(array){
  const fullArray = [];
  const filterSquare = _.filter(array, n => (Math.sqrt(n) % 1 === 0));
  fullArray.push(filterSquare);
  const filterNotSquare = _.filter(array, num => (Math.sqrt(num) % 1 !== 0));
  fullArray.push(filterNotSquare);
  return fullArray;
}
console.log(squared(input));
```
How I wanted to type it was 
```
const input = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

function squared(array){
  let fullArray=[];
  let filterSquare=_.filter(array, n => 
   {Math.sqrt(n)%1===0});
    fullArray.push(filterSquare);
  let filterNotSquare=_.filter(array, num => 
   {Math.sqrt(num)%1!==0});
    fullArray.push(filterNotSquare);
  return fullArray;
}
console.log(squared(input));
```
I didn't realize a couple of things before the use of eslint: "let" is only usable on variables that are changing( like a variable in a for loop, or an array that is increasing in elements or size), that you must have all functions on the same line when using arrow notiation, infix symbols for expressions needs to have a space around them, and that you can't just tab willy nilly, even if it looks cluttered. It was interesting though, when I tried a practice WOD I ended NOT getting an error when I had typed "fiter" vs "filter" and kept receiving an error. It's worth noting that IntelliJ has error notifications in the form of red lines on the code, and a red circle with a white exclamation point in the top right corner, and for some reason it still allowed me to open up the html file of the project with an error. Which was a little frustrating considering I found the error in the developer tools in Google Chrome. But overall the responsibility falls on me to make sure that my code is correct before doing anything, because when doing any whiteboard coding there's no such thing as intellisense. 

This experience was an enriching one, and although eslint may be slightly annoying. I'm actually learning good coding habits that will carry over long after this class is finished. And to be honest I need all the help I can get.
