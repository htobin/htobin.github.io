---
layout: essay
type: essay
title: Question!
# All dates must be YYYY-MM-DD format!
date: 2018-01-24
labels:
  - Stack Overflow
  - Problem solving
---
<img class="ui medium centered rounded image" src="../images/question.png">

"There's no such thing as a stupid question" is something people like to say, until they work in either retail or food service.
For example "can I get a caesar wrap without the tortilla?", to which you reply "one caesar salad coming right up". Now most customers leave
it at that. But some then insist "No, I want a caesar wrap without the tortilla". Let's just keep in mind that caesar wraps have the same 
amount of ingredients as a salad, all except the wrap which costs extra. This was my life as a manager, sometimes you just need to "give
um what they came for". Even if it's not in their best interest.

After breifly going over what a "stupid question" is thanks to <a href="http://www.catb.org/esr/faqs/smart-questions.html"> (this neat little guide)</a>I found out that having that it seems most "stupid questions" are just poorly articulated ones. It doesn't make them any less annoying to read/answer, but it definitely doesn't fall within the realm of stupid. Stupid quesitons are "Why doesn't my laptop power on?", "How come I can't open this link?", "Why is my screen so small?". You'll notice that not only are these questions simply answered via a google search, but also they are so general there are way to many possibilities to consider. I'll post an actual question right here:
```
How can one send an email to 100,000 users on a weekly basis in PHP? This 
includes mail to subscribers using the following providers:

AOL

G-Mail

Hotmail

Yahoo


It is important that all e-mail actually be delivered, to the extent that it is
possible. Obviously, just sending the mail conventionally would do nothing but 
create problems. Is there a library for PHP that makes this simpler? 
```
This was met with much criticism within the thread. In fact it was closed and then locked because not only was it not constructive but it was so general that it wasn't worth it. But I will say that I respect the people who actually took the time out of their day to answer this person's question. If you look at the top response, the responder goes into details on how to do it. They even give their best input as they possibly can and hope for the best.

This was a question that was asked. It was simple and not too technically challenging. But It was well put. A programmer had developed a program that took in two times that were one second apart. We see that the programmer has not only put their code. But their results, as well as java details such as the version as well as where they are getting his information for the timezone as well as the date.

If I run the following program, which parses two strings that are a times that are one second apart. 

```
public static void main(String[] args) throws ParseException {

    SimpleDateFormat sf = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");

    String str3 = "1927-12-31 23:54:07";

   String str4 = "1927-12-31 23:54:08";

   Date sDt3 = sf.parse(str3);

   Date sDt4 = sf.parse(str4);
   
   long ld3 = sDt3.getTime() /1000;
    
   long ld4 = sDt4.getTime() /1000;
    
   System.out.println(ld4-ld3);
}
The output is:

353

Why is ld4-ld3 not 1 (as I would expect from the one-second difference in 
the times), but 353?

If I change the dates to times 1 second later:

String str3 = "1927-12-31 23:54:08";

String str4 = "1927-12-31 23:54:09";

Then ld4-ld3 will be 1.

Java version:

java version "1.6.0_22"

Java(TM) SE Runtime Environment (build 1.6.0_22-b04)

Dynamic Code Evolution Client VM (build 0.2-b02-internal, 19.0-b04-internal,
mixed mode)


Timezone(`TimeZone.getDefault()`):

sun.util.calendar.ZoneInfo[id="Asia/Shanghai",

offset=28800000,dstSavings=0,

useDaylight=false,

transitions=19,

lastRule=null]


Locale(Locale.getDefault()): zh_CN
```


We then see how they get their answer, and it turns out there's an error in the library of times that they are getting the times from. This isn't an obvious answer. A simple google search may have not given this answer they were getting as to why this didn't work. The programmer simply thought that their was a bug in their code, and was trying to help get out the bug in their code that they typed. When the actual bug was from a library issue with the timezone, where the clocks got set back. Therefore there were two instances of a certain time, and the library simply referenced the first one. What a cool bug!

