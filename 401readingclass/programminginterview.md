# programming interview

## 7 tips to ace a programming interview

### 1) Take a few minutes.

* Speaking as an interview coach, this is one misstep that I see all the time during mock interviews. The canonical tip that everyone gives is, “talk more!”. What most of those well-meaning advice-givers overlook, however, is that talking and thinking at the same time is extremely hard. Nervous interviewees will jump straight into talking, passing up a great opportunity for concentrated thought.

Don’t waste precious minutes trying to fill the silence by saying everything you’re thinking, while simultaneously trying to solve the problem in your head.

Instead, wait until the interviewer is done explaining the problem. Ask any clarifying questions, and then tell your interviewer:

“Okay, got it. If it’s okay with you, I’m just going to take a minute or two here and think about the problem, and then I’ll start talking.”
Shut your eyes, stare at the ceiling, scribble on the whiteboard — whatever it takes. Think through the basics of the problem, and decide on an approach. Then re-engage the interviewer, and let him know what you’ve concluded. Don’t forget to provide your reasoning!

So, I think that, since the array is sorted, it makes the most sense to do something like a binary search here.
 Here are the general steps that I think are involved in the solution: …”

### 2) Write down the steps of the solution.

* Even after you have an idea of how to attack the problem, don’t start writing code down. Write down the general steps of how you will solve it on one side of the whiteboard, where it’s visible but won’t get in the way. You don’t need to be verbose, just get the steps in order and somewhat readable.

> Start at middle of array.

>  Keep variables tracking left and right boundaries of search area.

> If value equal to search_val, return true.

> If left and right boundaries are adjacent, return false.

> If value bigger than search_val, go halfway towards left boundary, and move the right boundary along with us.

> If value smaller than search_val, go halfway towards right boundary, and move the left boundary along with us.

### 3) Write pseudocode first.

* Time to write code? Nope. Take a “dry run” at writing the code by writing some pseudocode. Often we run into problems halfway through writing the code, and there’s no point wasting time over syntax when you might have to throw the code away. Instead, write some half-baked code-looking stuff that lays out the structure of how your code will work. Do it over on the side of the whiteboard, so you have space left to work.

```py
cur_idx = array.length / 2
l_marker = 0
r_marker = array.length
while (markers are more than 1 apart)
  if array[cur_idx] === search_val
    return true
  else if array[cur_idx] < search_val
    cur_idx goes halfway towards r_marker
    l_marker = cur_idx
  else if array[cur_idx] > search_val
    cur_idx goes halfway towards l_marker
    r_marker = cur_idx
return false
```

* No worrying about off-by-one issues, or index arithmetic; just verifying that our logic is correct.
Even if we never make it to writing code, many interviewers will consider this a solution to the problem. It proves that we understood the problem, devised the correct solution, and are well on our way towards implementing it in code.
From here, the pseudocode turns very neatly into any language we want it to — for example, JavaScript:

```py
function binarySearch(search_val, arr) {
  let i = arr.length / 2;
  let l_marker = 0, r_marker = arr.length;
  while (r_marker - l_marker > 1) {
    if (array[i] === search_val) return true;
    else if (array[i] < search_val) {
      i+= ((r_marker - i) / 2);
      l_marker = i;
    }
    else if (array[i] >search_val) {
      cur_idx -= ((i- l_marker) / 2);
      r_marker = i;
    }
  }
  return false;
}
```

### 4) Don’t sweat the small stuff.

* Programming interviews are not about how well you’ve remembered your semicolons, nor are they about being able to remember all of the flags on a TCP packet. They’re about demonstrating depth and breadth of knowledge, personality strengths, and problem-solving abilities. If you make a mistake, it’s okay. Brush it off and move on.

If you can’t remember something like this, it’s often acceptable to say that you’d look it up.

“…and here, I’d use whatever the list.contains() equivalent is in JavaScript. I know it’s not contains, but I can’t remember the method name right now, so we’ll call it contains() for now and I’d look it up right now if I were coding this.”

Let’s be honest, half of being a programmer is knowing how to Google stuff and how to interpret search results. We use the internet as a giant cache for all the information that we “almost” remember but don’t bother to, since we can just look it up at any time. It’d be hard to fault an answer like the one above. So don’t waste time memorizing keywords in your interview prep. Focus on the big picture.

### 5) Sit down. Be humble.

* A programming interview isn’t just a written exam. It’s an assessment of your programming abilities, and there are plenty of things that fall into that category beyond mere coding prowess. For example:

> Are you able to express your ideas and solutions clearly and effectively?

> Do you treat the interviewer with respect?

> How do you accept criticism (technical, constructive or otherwise)?

> Are you able to collaborate with others to come up with solutions?

> Do you communicate in a way that demonstrates empathy?

> Are you honest (especially about yourself)?

* If you are given criticism in an interview, you need to take it and be grateful for it. No snide remarks, no “oh, I was gonna do that in a second anyway”, no anger or raised voice. The interviewer has their opinion, and they didn’t have to share it — they could’ve just written it down silently and rejected you as a candidate later. They’ve given you a chance to correct course because they think you’re worth it, and they’ve extended an opportunity for you to demonstrate how you accept feedback from your peers. Don’t waste it.


### 6) Come prepared.

* When it comes to programming interviews, there is no substitute for HOBIS (which stands for Hours of Butt-In-Seat). If you want to be ready, you have to put in the time. It’s important in order to maximize your chances of acing the interview, but it’s also important for your peace of mind during the interview and afterwards. 

In the interview, knowing that you’ve done all you can to prepare helps you stay calm and cool, and increases your chances of success. And afterwards, regardless of the outcome, knowing that you could not have reasonably done more to prepare helps you feel proud of your work and start moving towards your next goal.

To pretty much everyone that I coach through interviews, I recommend the same personal interview prep bible: Cracking the Coding Interview, by Gail Laakman McDowell. Like myself, Gail’s been at Facebook and Google, but as a former member of the Google Hiring Committee, Gail is qualified to speak authoritatively on the software hiring process (and able to speak in detail about the Google hiring process, which I cannot due to my employment contract).

 This book’s been around for years and almost every engineer I’ve met at Google or Facebook (including myself) has completed it cover-to-cover. If you want to get the most value out of your HOBIS, I cannot recommend CtCI enough.
No matter what material you use, make sure you get enough HOBIS and your next interview will be a much better experience.

### 7) Review your work.


* You won’t always finish questions in the time permitted, but occasionally you’ll have extra time after coming up with a solution. If this happens, it’s tempting to say “Well, I’m done!”. Interviews are stressful and we want them to be over as fast as possible. This is reasonable, but:

Think about how silly you look if your solution is not right.

Instead, if you have the time, review your code as you would in a peer review. Show the interviewer that you are committed to producing accurate, high-quality work, and that they can trust you to do so without being prompted.

In particular, focus on these two areas, as they receive heavy scrutiny in interviews:

**Algorithmic efficiency**. Have you found the fastest and most optimal solution given the requirements? Take some time and consider other approaches. It’s worth noting two things here: 1) If the problem involves a sorted dataset, you can bet your pants there’s a solution involving ` O(log(n)) lookup time (even if there’s additional cost, the total complexity will still contain the log(n), for example, O(n * log(n)) if iterating over an array, as sorting algorithms do), and 2) For a disgustingly large number of programming interview questions, the answer involves a hash table and O(1) lookup time — so if you’re seeking a better algorithm, try a hash table.
**Correctness**. Sure, you’ve solved for the simple, easy use case, but have you checked for edge cases? Off-by-one errors? Issues with negative numbers or empty arrays or missing keys or strings with weird patterns of characters? Maybe you won’t find all of them, but failing to at least LOOK for edge cases before declaring your solution to be correct is a pretty hefty mistake in an interview.