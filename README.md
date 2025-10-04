<h1>ExpNo 5 : Implement Simple Hill Climbing Algorithm</h1> 

```
Name         : Shivaram M.
Register No. : 212223040195
```

<H3>Aim:</H3>
<p>Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration </p>
<h2> Theory: </h2>
<p>Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space.
Feedback is provided in terms of heuristic function
</p>


<h2>Algorithm:</h2>
<p>
<ol>
 <li> Evaluate the initial state.If it is a goal state then return it and quit. Otherwise, continue with initial state as current state.</li> 
<li>Loop until a solution is found or there are no new operators left to be applied in current state:
<ul><li>Select an operator that has not yet been applied to the current state and apply it to produce a new state</li>
<li>Evaluate the new state:
  <ul>
<li>if it is a goal state, then return it and quit</li>
<li>if it is not a goal state but better than current state then make new state as current state</li>
<li>if it is not better than current state then continue in the loop</li>
    </ul>
</li>
</ul>
</li>
</ol>

## Code:
```
import random, string

target = "Artificial Intelligence"
chars = string.ascii_letters + " !?."
rand_str = lambda n: ''.join(random.choice(chars) for _ in range(n))
score = lambda s: sum(abs(ord(a) - ord(b)) for a, b in zip(s, target))
mutate = lambda s: s[:i] + random.choice(chars) + s[i+1:]

best = rand_str(len(target))
best_score = score(best)

for step in range(100000):
    i = random.randrange(len(target))
    new = mutate(best)
    new_score = score(new)
    if new_score < best_score:
        best, best_score = new, new_score
    if step % 1000 == 0:
        print(f"{step}: {best} ({best_score})")
    if best_score == 0:
        break

print("\nFinal:", best)

```

</p>
<hr>
<h3> Steps Applied:</h3>
<h3>Step-1</h3>
<p> Generate Random String of the length equal to the given String</p>
<h3>Step-2</h3>
<p>Mutate the randomized string each character at a time</p>
<h3>Step-3</h3>
<p> Evaluate the fitness function or Heuristic Function</p>
<h3>Step-4:</h3>
<p> Lopp Step -2 and Step-3  until we achieve the score to be Zero to achieve Global Minima.</p>

<hr>
<h2>Sample Input and Output</h2>
<h2>Sample String:</h2> Artificial Intelligence
<h2>Output:</h2>
Score: 643  Solution :  8RzF:oG ]%;CPORRMe!zGvk<br>
Score: 609  Solution :  8RzF:oG ]%;CPqRRMe!zGvk<br>
Score: 604  Solution :  8RzF:oG ]%;CPqRRMe!zGqk<br>
Score: 594  Solution :  8RzF:oG ]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
....................................................<br>
..................................................<br>
................................................<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 1  Solution :  Artificial Intelligencf<br>
Score: 0  Solution :  Artificial Intelligence<br>
<img width="997" height="226" alt="output" src="https://github.com/user-attachments/assets/fec5191c-90f7-42fe-9a7b-c13fcc554b95" />
<img width="1680" height="1050" alt="code" src="https://github.com/user-attachments/assets/8748f49e-2554-48ee-9966-40fdadf76b34" />

## Result:
An simplle Hill Climbing algorithm has been implemented successfullly.
