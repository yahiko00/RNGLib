# RNGLib
Pseudo-Random Generator Library in TypeScript

This is a set of Pseudo-Random Generators written in TypeScript.
Available PRNGs are the following:

* Default browser's RNG
* Houle's Central Randomizer
* IBM RANDU
* C Standard Library
* Microsoft Windows (until XP)
* Xorshift
* Mersenne Twister

It also include a function to generate random numbers with a Gausian distribution.

## How to use it

Example using Xorshift and Mersenne Twister algorithms:

	/// <reference path='randXorshift.ts' />
	/// <reference path='randMersenne.ts' />
	
	let rng1 = new RNGLib.RandXorshift(); // Xorshift algorithm with the current time as seed
	let rng2 = new RNGLib.RandMersenne(2016); // Mersenne Twister algorithm with 2016 as seed
	
	// Display 10 random values with Xorshift algorithm
	for (let i = 0; i < 10; i++) {
	    console.log(rng1.rand());
	}
	
	// Reset the Xorshift RNG with previous seed
	rng1.reset();
	
	// Same identical random numbers
	for (let i = 0; i < 10; i++) {
	    console.log(rng1.rand());
	}
	
	// Reset the Xorshift RNG with a new seed
	rng1.reset(Date.now();
	
	// New random numbers
	for (let i = 0; i < 10; i++) {
	    console.log(rng1.rand());
	}
	
	// New random numbers with Gausian distribution
	for (let i = 0; i < 10; i++) {
	    console.log(RNGLib.randNorm(rng1.rand));
	}

## Importing

**To import**

	import RandXorshift = require('randXorshift');
	import randNorm = require('randNorm');

## API

All functions and classes are under the namespace `RNGLib`.

Classes:
Note that these classes' RNG are uniformly distributed.

* `RandCentral`: Central Randomizer by Paul Houle
* `RandU`: RANDU by IBM
* `RandCLib`: C language RNG
* `RandMSWin`: Windows API RNG
* `RandLCG`: Generic LCG
* `RandXorshift`: Xorshift
* `RandMersenne`: Mersenne Twister

Functions:

* `randNorm()`: Gausian distribution
