# AdapterCardGameStart
## Setup
* See if not done from the last lab [https://stgit.dcs.gla.ac.uk/DerekSomerville/javagetstarted/-/wikis/home/setup](https://stgit.dcs.gla.ac.uk/DerekSomerville/javagetstarted/-/wikis/home/setup)
* Fork [AdapterCardGameStart](https://stgit.dcs.gla.ac.uk/oose-2021-22-teaching-team/adaptercardgamestart.git) see [https://stgit.dcs.gla.ac.uk/DerekSomerville/javagetstarted/-/wikis/home/Git/Project_Setup](https://stgit.dcs.gla.ac.uk/DerekSomerville/javagetstarted/-/wikis/home/Git/Project_Setup)
* Make sure you have invited Derek Somerville and your tutor as Developer Members

## Overview
* The lab will look at doubling using the Adapter Design Pattern. Please refer to week six lecture on the Adapter Design Pattern. 
* This lab will create adapters for calls to the file system, adapters for input from the console and output to the console.
* This will allow the testing of the card games wih out the need to go to the file system or get inputs from the console.
* Please find a video overview of what you need to know from the Adapter Design Pattern lecture for the lab [https://uofglasgow.zoom.us/rec/share/QjQt1zbjuwQGYgMrX1tDDBc-PUqa_CpvxJGI0gV1gvEStOTcGnn55ls_TQVRVbfD.N9qsbYv71kE0iBtJ?startTime=1644928799000](https://uofglasgow.zoom.us/rec/share/QjQt1zbjuwQGYgMrX1tDDBc-PUqa_CpvxJGI0gV1gvEStOTcGnn55ls_TQVRVbfD.N9qsbYv71kE0iBtJ?startTime=1644928799000). Please see slides [https://gla.sharepoint.com/:f:/s/COMPSCI2008OBJECT-ORIENTEDSOFTWAREENGINEERING22/EqkJHUJO_1dOssa-Au6gvNUBl4iSNeniTN5QeLV1wL0xYw?e=Hr7IlR](https://gla.sharepoint.com/:f:/s/COMPSCI2008OBJECT-ORIENTEDSOFTWAREENGINEERING22/EqkJHUJO_1dOssa-Au6gvNUBl4iSNeniTN5QeLV1wL0xYw?e=Hr7IlR).
* If you are interested in pair programming, it is optional, see [video](https://uofglasgow.zoom.us/rec/share/QjQt1zbjuwQGYgMrX1tDDBc-PUqa_CpvxJGI0gV1gvEStOTcGnn55ls_TQVRVbfD.N9qsbYv71kE0iBtJ?startTime=1644928799000) 
  * and [wiki](https://stgit.dcs.gla.ac.uk/DerekSomerville/javagetstarted/-/wikis/home/Pair-Programming) and 
  * register on the [form](https://forms.office.com/Pages/ResponsePage.aspx?id=KVxybjp2UE-B8i4lTwEzyELpM2ZClsRNrJBn7A_b41VUMlFPTUpPMjlCSkRQQTE5NUpYQ01INUJLSy4u)
* Pre-reading - Chapter 7 pg243 - pg255 - The Adapter & Facade Design Pattern. 2009 Eric Freeman, Elisabeth Robson, Bert Bates, and Kathy Sierra. "Head First Design Patterns". See University Library for free online copy. ~ 20 minutes

## Adapter classes Names
The below is guidance for you to create and amend the classes. We have not created these in advance for you.
* Create a new abstract named Input in the console package, if it is an abstract you only need one getInteger
  * This abstract should contain the getString method to implement
  * This abstract should implement the getInteger method
  * So match the methods of ConsoleInput
* Create a new interface/abstract name output in the Console package
  * Contains the methods of ConsoleOutput
* Create a new adapter name InputTestAdapter that implements the input abstract in the Console package
* Create a new adapter name OutputTestAdapter that implments the output interface/abstract in the Console package
* Create a new interface/Abstract name Config in the Structure Package
  * Contains the public methods of LoadConfig
* Create a new adapter LoadTestAdapter in the Structure Package that implements the Config interface

## Adapter Steps
* Create an interface/abstract with defined methods and parameters
* Each Adapter to implements the interface
* Each Adapter implements the interface methods
* Client (CardGame) has an adapter variable of interface type
* Client setter to amend the adapter variable
Please see the [video](https://uofglasgow.zoom.us/rec/share/QjQt1zbjuwQGYgMrX1tDDBc-PUqa_CpvxJGI0gV1gvEStOTcGnn55ls_TQVRVbfD.N9qsbYv71kE0iBtJ?startTime=1644928799000) or lectures for more details.

## Game.CardGame Tests
* Create a test for getComputerPlayersNames, create an adapter for LoadConfig, note there is CardGame.setLoadConfig.
  * Moderate - Test name getComputerPlayersNamesAdapter you can get a list of at least three names. Use different names to the playersNames.cfg
* Create two tests for createComputerPlayers
  * Easy after previous - Test name createComputerPlayersAdapter for a list of three names and check the name of the third computer player is correct
  * Easy - Test name createComputerPlayersSizeAdapter to see three players have been created. Not you pass four as the noOfPlayers to create three players, it assumes a human player is created.
* Create a test for createHumanPlayerAdapter
  * Easy - Test name createHumanPlayer, check the name of the human player
* Create a test for initiatePlayersAdapter
  * Easy - Test name initiatePlayers, check the number of players created
* Create a test for initiateAdapter
  * Easy - Test name initiate, check at least one player has been dealt cards
* Create a test for playAdapter
  * Moderate - Test name play, think about the play while condition, try to run the game end to end

## Game.BlackJack
* Create a test for "play", so an end to end test using the adpaters
  * Advanced - Test name is "playAdapter", check if the game has finished and the user has three cards

## Game.Sevens
* Create a test for "play", so an end to end test using the adpaters
  * Advanced - Test name is "playAdapter", the game should play and finsh. Sevens is won when a user has no cards. Note you can override the deck and don't need to use a full pack
  
## Submit
* Before you commit your final solution, double check it can build and all the test you completed can run.
* Go to the Week 7 section and open the assessment
* In text paste the https .git for the forked project
* Zip the project and submit