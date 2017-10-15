turtles-own [edad energia msubita]

to config
  clear-all
  create-turtles 20 [
  set shape "person"
  setxy random-xcor random-ycor
  set edad 0
  set energia 10
  set msubita random 10
  ]
  ask patches [
 set pcolor blue
  ]
end

to program

  move
  eat
  dead

end

to move
  ask turtles[
    set heading heading + random 100
    forward 1
    set edad edad + random 4
     set energia energia - 1
     set pcolor green
  ]
end

to eat
  ask turtles[
    if (pcolor = green)[
      set energia energia + 2]
  ]
end

to dead
  ask turtles[
    if energia < 0
    [die]
    if edad > 120
    [die]
    if msubita = 7
    [die]
  ]
end
