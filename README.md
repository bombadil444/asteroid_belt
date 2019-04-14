# Asteroid Belt

A bullet hell game written in python that fits on a business card.

Inspired by Frank Force's Tiny Ski: http://frankforce.com/?p=5826

Limited to 40 characters wide by 35 characters tall (max 1400 bytes).

## Compatibility
Only runs on Linux consoles due to use of the curses library.

Compiles in python 2.7 and 3.X

## Controls
* WASD keys to move
* P key to shoot
* 0 key to quit

## Features
* Fast paced bullet hell gameplay
* Randomly generated asteroids
* Adjustable difficulty (make the console screen smaller for a harder difficulty)
* Scoring system

## The Code
```python
class A:             # ~~ASTEROID BELT~~
  w=0;a=4;t=2          # By u/Bombadil44
  def m(_):     # github.com/bombadil444
    _.x+=_.z;_.w+=1  # WASD=move P=shoot
    try:      # Don't Panic! Have Fun :D
      for i in 0,1: p(_.x,_.w+i,"O"*4)
    except: o.remove(_)
  def __init__(_): _.x=r(t);_.z=r(-1,2)
class Z: #                       OOOO 0
  def __init__(_): _.x=x+3;_.y=y#OOOO
  def m(_): #                        AA
    _.y-=1;p(_.x,_.y,"0") #    OOOO <==>
    if _.y<=0: global m;m=0 #  OOOO  **
from curses import*;from random import*
z=initscr();r=randrange;q,t=z.getmaxyx()
l=[" AA","<==>"," **"];d=a=m=n=0;y=q-9
def p(h,e,w): z.addstr(e,h,w)
def k(e=100,w=1,l=0):
  if e in u: global d;global a;d=w;a=l
z.keypad(1);z.nodelay(1);o=u=[];x=10
while 48 not in u:
  u=[];U=0;r(7)<5 and o.append(A())
  while U!=-1: U=z.getch();u+=U,
  m=(m,Z())[112 in u];k();k(97,-1)
  k(115,0,1);k(119,0,-1);z.clear()
  x+=d;y+=a;y-=(0,a)[y<0 or y+3>q]
  x-=(0,d)[x<=0 or x+7>t];m and m.m()
  for i in 0,1,2: p(x,y+i,l[i])
  for e in o:
    v=e.x;g=e.w;e.m();(v+e.a>x+3>=v
    and g+e.t>y+2>=g and u.append(48))
    if (m and v<=m.x<v+e.a and g<=m.y<
     g+e.t): o.remove(e);m=0;n+=1000
  p(10,0,"SCORE: %s"%(n));napms(50)
napms(5000);z.keypad(0);endwin()
```

## Screenshot
![alt text](https://github.com/bombadil444/asteroid_belt/blob/master/screenshot.png "Asteroids Everywhere!")
