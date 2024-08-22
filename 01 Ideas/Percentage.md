10 / 5 = `[2] [2] [2] [2] [2]` 

lets say you've scored 250 out of 500, means 

250/500 gives you 0.5

the 0.5 is a representation of a single part out of 500 parts where 250 is distributed evenly

it goes like

```
[0.5] [0.5] [0.5] ...246[0.5]... [0.5]
```

the divide operation gives you the value of the single part `[0.5]`

once you got the single part, we can extrapolate that into any range of values with multiplication

```
[0.5] * 100 = [0.5] + [0.5] + ...98[0.5] = 50
```

Means that only 50 parts of 100 can be filled because `[0.5]+[0.5]` is actually one part

its just humans like to use 100 parts to get overall idea about any progress, and it is overused in many areas, charging, speed, progress and many

in fact we can extrapolate this into any range, say 50

```
[0.5] * 50 = 25
```

You've got 25 parts out of 50 done/finished/wrote/filled/worked