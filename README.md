# Design Document for Language Detection
### Adam Carroll and Christopher Nadeau
### adam_carroll@my.uri.edu
### cmnadeau@my.uri.edu

## Problems to Solve
- Taking a file input
- Breaking down the document into trigrams
- Assembling the trigrams into a frequency vector
- Computing the cosine similarity between two vectors

## How will we solve them?
- readFile function - returning a string ot the entire text input
- createTrigrams - adapted code of translate() from DNA class
- createTrigrams - makes the frequency vector
- computeCosineSimilarity - function with two loops to compute
 - The dot product of the two vectors
  - The magnitudes of the vectors multiplied together

## What classes/subclasses should we create?
- Language Class - Will contain the data for each language provided
- Constructor will take in file name to read and compute frequency trigram

## What instance variables/methods/functions do we need, what will their types be?
- (std::string) readFile (function) - This will serve as an abstraction to read the language documents in the language class
- (std::string) languageList (variable) - contains all of the non-query languages
- (std::string) createTrigrams (function) - This function will parse the string of text for a given language documentand map the trigrams to the corresponding vectorof trigram frequencies
-(double) computeCosineSimilarity (function) - compute similarity between query document and given known language document
- (std::vector) trigramFrequency (variable) - the vector containing the frequency of trigrams for the given language document
- (std::vector) getTrigramFrequency(method) - This function will live inside the language class and return the trigram variable so that clients will have read-only access to it
- (std::string) compareQueryToKnownLanguage (function) - This function will return the language most closely associated with the query after it compares the query to all of the provided baseline languages

## What files dowe need to create?
- main.cpp - This file will be the main file for the program. It will take the command line arguments and use the necessary functions to compare the query to the other languages and return the most similar language to the user
- language.cpp - This will contain the implementation details of te functions prototyped in language.h to hide them from the user
- language.h- This will include the prototype constructors for creating a new instance of the language class as well as the other related functions
- Compile script (./compile) - This will implement clang++ to compile our program, resulting in an executable called 'language'

## For Milestone 1, hwo will main() be structured?
- Take a string input, argv[1]
- Generate the trigram via createTrigrams(), storing them in vector<string> v
- cout all elements of vector v

## For Milestone 2, how will main() be structured?

## What libraries will we need?
- string - The text of the language documents will be read in strings
- vector - This type will be used to store teh trigram frequencies
- algorithm - contains functions used to help with computing cosine frequencies
- cstdlib- EXIT_FAILURE
- fstream - used to read the language documents
- iostream - used to output text to the console for the user to see

## What files will our compile script have to compile?
- main.cpp
- language.cpp
->>into 'language' executable
