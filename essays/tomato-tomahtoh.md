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

With my introduction to javascript, we didn't use a local IDE in order to type up code. We used a cloud based IDE with JS fiddle. The conclusion of our use of JS Fiddle allowed me to learn javascript while not really worrying too much about 
