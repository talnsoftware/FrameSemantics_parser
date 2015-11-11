# FrameSemantics_parser
A tool that, given a PTB dependency tree, creates FrameNet structures over all the content-bearing units of the sentence.

----------
  README
----------
Welcome to the UPF Frame-Semantics parser!

(v0.1) - 11/11/2015

Authors: Simon Mille, Roberto Carlini (firstname.lastname@upf.edu)


-------------
Requirements
-------------
Java 1.6 or posterior

-------------
Introduction
-------------
* <b>Structures</b>: this tool produces structures as found in FrameNet (https://framenet.icsi.berkeley.edu/fndrupal/). The important difference with the FrameNet structures is that <b>all content-bearing units</b> are connected with one another. In other words, this parser does not consider spans of text as Frame Fillers. One other difference with the other Frame Semantics parsers is we aim at eventually making our tool multilingual.
The ouput provided by our tool is an adaptation of the CoNLL 2009 format (http://ufal.mff.cuni.cz/conll2009-st/task-description.html); the two differences are: (i) we only use 14 columns (the first 14, from "ID" to "PRED"); (ii) the "HEAD" and "DEPREL" columns can contain more than one element, in order to allow for multiple heads for one word.

* <b>Tool</b>: the tool is developed on two independent aspects:
  (i) the resources (grammars and dictionaries), which contain all the linguistic knowledge; the updates affect the content of the produced file;
  (ii) the graph transduction environment, which uses the resources in order to generate the output; the updates affect the way the file is produced.


--------
Releases
--------
<b>v0.1</b>
* English only
  - Input: Dependency Penn Treebank structure, in the 2009 CoNLL Shared Task format
  - Version of graph-transduction grammars and dictionaries: v0.5 (see at the bottom of the page)


--------------------------
How to run the conversion
--------------------------
(0) Download the .jar from the "release" section of the folder; if it does not appear towards the top of this page, click on "FrameSemantics_parser" in the path "talnsoftware/FrameSemantics_parser".

(i) <b>IMPORTANT!</b>
* Input file should be in the CoNLL 2009 format; see http://ufal.mff.cuni.cz/conll2009-st/task-description.html (predicted columns and the columns after the 14th are ignored).
* All empty lines (betwen two consecutive sentences) must be empty! No spaces or tabs! (The evaluation set of the PTB for example can have these tabs)
* Input file should have .conll extension
* Input file should be encoded as UTF-8 (preferrably without BOM)

(ii) Command line
* Through the command line, go to the directory containing the desired version of converter.jar.
* Execute:
 java -jar FrameSemParser.jar -i inputfile.conll -o outputFolder

Example: 
  The FrameSemParser_V0.1.jar is located under 'C:\Users\smille\Desktop\TALN\Corpus\DSynt Converter\tests_framenet'.
  So, I go to the directory:
    C:> cd "C:\Users\smille\Desktop\TALN\Corpus\DSynt Converter\tests_framenet"
  And then, execute:
    C:\Users\smille\Desktop\TALN\Corpus\DSynt Converter\tests_framenet>java -jar FrameSemParser_V0.1.jar -i test_PTB_str.conll -o out

* Accepts absolute paths in input file (-i) and output folder (-o) parameters, if the input file is not in the same folder as the .jar.

-----------------
Grammar versions
-----------------
<b>v0.5</b>
TBD ...
