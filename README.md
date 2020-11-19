# Legislative Voting Data

## Motivation
I originally started thinking about this data while working on this paper: <a href="https://arxiv.org/abs/1611.02530"> A Random Dot Product Model for Weighted Networks</a> joint with Dan Rockmore, where we detected the party structure in the US Senate using an inference technique associated to dot product networks. A natural follow up question is attempting to apply this method to legislatures that have more than two parties. This led me to compare voting data from both houses of the US Congress to voting data from the European Parliament. 

## Data Sources
I obtained the US voting data from the <a href="https://voteview.com/data">Voteview</a> site[1], extracting the Member Ideology and Members' Votes datasets for the 115th Congress and the 114th Senate. The European Parliament data comes from a study of voting and twitter behavior documented at the <a href="https://www.clarin.si/repository/xmlui/handle/11356/1071"> Clarin.si</a> repository. 

## Processing Steps
Some processing needed to be performed for both data sets. The main issue for the US data is that the information about the legislators is stored in a wide format, with rows indexed by the legislator and columns providing their name and party details, while the roll call votes themselves were reported in a long format with one row per vote. The scripts Process_Votes_House and Process_Votes_Senate join these datasets together into a single dataframe with rows indexed by legislator and  columns containing both the legislators information, as well as how they voted on each bill. The European Parliament data for the votes was already sorted by the id of the legislator, so it was simply a matter of appending the relevant party information to the voting data. This is performed in Process_Votes_EP notebook. 

In addition to combining the information about the legislators and their respective votes, the vote codes differ significantly between the data sets. The recorded values in the 
<table>
  <tr><td>Data Value</td><td>US Congress</td><td> Eurpoean Parliament</td></tr>
  
  </table>

## Visualizations

## Analysis

## Descriptions of Code and Materials
The raw data downloaded from the sources described above is contained in the `Raw_Data` folder, while the .csv files generated as a result of the processing procedures are contained in `Processed_Data`. There is one Jupyter notebook for each legislative body that does the processing and generates the relevant figures. 

## References
[1] Lewis, Jeffrey B., Keith Poole, Howard Rosenthal, Adam Boche, Aaron Rudkin, and Luke Sonnet (2020). Voteview: Congressional Roll-Call Votes Database. https://voteview.com/ 

[2] Cherepnalkoski, Darko; Karpf, Andreas; Mozetič, Igor and Grčar, Miha, 2016, Dataset of European Parliament roll-call votes and Twitter activities MEP 1.0, Slovenian language resource repository CLARIN.SI, http://hdl.handle.net/11356/1071. 
