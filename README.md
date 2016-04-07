
Airport Challenge
=================
Makers Academy weekend challenge 1 - 24 Jan 2016
------------------------------------------------

[![Build Status](https://travis-ci.org/makersacademy/airport_challenge.svg?branch=master)](https://travis-ci.org/innlouvate/airport_challenge)
Includes: gems, ruby classes & rspec unit tests

```
        ______
        _\____\___
=  = ==(____MA____)
          \_____\___________________,-~~~~~~~`-.._
          /     o o o o o o o o o o o o o o o o  |\_
          `~-.__       __..----..__                  )
                `---~~\___________/------------`````
                =  ===(_________)

```

Task
-----

We have a request from a client to write the software to control the flow of planes at an airport. The planes can land and take off provided that the weather is sunny. Occasionally it may be stormy, in which case no planes can land or take off.  Here are the user stories that we worked out in collaboration with the client:

```
As an air traffic controller 
So I can get passengers to a destination 
I want to instruct a plane to land at an airport and confirm that it has landed 

As an air traffic controller 
So I can get passengers on the way to their destination 
I want to instruct a plane to take off from an airport and confirm that it is no longer in the airport

As an air traffic controller 
To ensure safety 
I want to prevent takeoff when weather is stormy 

As an air traffic controller 
To ensure safety 
I want to prevent landing when weather is stormy 

As an air traffic controller 
To ensure safety 
I want to prevent landing when the airport is full 

As the system designer
So that the software can be used for many different airports
I would like a default airport capacity that can be overridden as appropriate
```

Your task is to test drive the creation of a set of classes/modules to satisfy all the above user stories. You will need to use a random number generator to set the weather (it is normally sunny but on rare occasions it may be stormy). In your tests, you'll need to use a stub to override random weather to ensure consistent test behaviour.

Your code should defend against edge cases such as inconsistent states of the system ensuring that planes can only take off from airports they are in; planes that are already flying cannot takes off and/or be in an airport; planes that are landed cannot land again and must be in an airport, etc.

Approach:
--------
This programme uses a number of different classes;
* AirTrafficControl - which carries all inflight planes and is responsible for instructing landing and take-off sequences. 
* Airport - which captures all planes landing at a particular airport. 
* PlaneContainer module - which consolidates methods used by both AirTrafficControl and Airport to sign planes in/out and set default capacity and full criteria. 
* Airplane - which captures each planes status (landed/inflight) and reference location. 
* Weather - which produces a random assignment of stormy weather (1/10 chance of bad weather).

I wanted to use the ability to include mixins as learnt during the boris bikes
exercise and to create a contained system where planes would always belong in
one place (hence landing/take-off actions undertaken by the air traffic control
have automatic knock-on to check planes in/out of an airport). This is a little
more complicated than necessary, but I wanted to test how this might work and
be unit/feature tested.

Install:
-------
```
git clone https://github.com/innlouvate/airport_challenge.git
cd airport_challenge
```
