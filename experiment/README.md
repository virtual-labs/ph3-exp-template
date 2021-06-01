## README
### Quiz V2.0
The new format of quiz has multiple new additions. The details for which have been described below.  
The format of json would bas linked [here](./pretest.json)  

**version**
The very first field is absolutely necessary. This ensures that the quiz supports the new features.
```
"version": 2.0
```   

**Explanations**[OPTIONAL]  
Just like we mention answers, we can have a section for explanation so that they show up after an answer is marked. This is optional and can completely be left out. The three ways of defining (Assuming there are 4 answers a, b, c, d):

1. All answers have explanations
```
"explanations": {
    "a" : "Explanation 1,
    "b" : "Explanation 2"
    "c" : "Explanation 3"
    "d" : "Explanation 4"
},
```  
2. Some answers have explanations
```
"explanations": {
    "a" : "Explanation 1,
    "d" : "Explanation 4"
},
```

3. No answers have explanations
```
/* Can be excluded from json */
```  

*An extra functionality of explanation is the ability to add an external link. It will work just like in html.*  
```
"explanations": {
    "a" : "Explanation 1  <a href='www.google.com'>here</a>",
    "b" : "Explanation 2"
},
```

**Difficulty**[OPTIONAL]
Adds an ability to filter questions based on difficulty, if no difficulty is mentioned by default the question is assumed to be Begginer level.
The three available difficulty levels are:
```
['beginner', 'intermediate', 'advanced']
```
Using any other will not work. The format for the same:
```
"difficulty" : "beginner"
```