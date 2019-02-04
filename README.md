# dataminingtwitter
data mining twitter
#The best way to learn R is by doing.

#Different components of Data analysis with R 
#Packages: bundles of code that can be viewed as a set predefined instructions(commands) that will get the software to do what you want it to do
#Importing data: flat files , excel files , statistical software, databases or web
#Data manipulation:turning raw data into well structured data, important for analysis
#Data Visualisation: allows you to create images, maps, graphs of your result


#for this simple excerise we will focus on collecting data "Data Mining" and importing the data from the web (social networks)
#we will be interacting with social media website twitter to collect data 
#packages needed are the following:

#rtweet
#TwitterR
#Roauth

#so now we input commands to get it to install these packages so we can begin our "Data Mining"

install.packages("ROAuth")  #allows for authentication (connect with twitter)
install.packages("rtweet")
install.packages("twitterR")   #use the help button and type in twitterR and Rtweet for more information on these packages

#once install you upload the packages using the library() function

library(twitteR)
library(rtweet)
library(ROAuth)

#now we set up a connection with twitter API and use a special set of keys I already generated that will allow you to access twitter data

setup_twitter_oauth("A9GDuLttu4r00xS1hRflqPIPh", "oYoDdmL7vACGrXuUUbbYi4i44p1Zc8eRNY1dYpwMcyMuXhRX2t","592560842-IFL9MhuSW6ZGkFqC317hOUK2a2icv3BwcE9Y8Zl7","cG5vYXNg8hUQD49JntyGdgwJH47hsNqqtOR4AfMGrJ6J3")

#connection should now be set and now we search any term we want on twitter
#here we are creating an object called dscience

dscience <- twListToDF(searchTwitter("#datascience", n=500, lang=NULL,since=NULL, until=NULL,locale=NULL, geocode=NULL, sinceID=NULL, maxID=NULL,resultType=NULL, retryOnRateLimit=120))

#twlisttoDF turns the list of randomly selected tweets that its originally created into a dataframe we can utilise for analysis
#searchtwitter is a function(command) from TwitterR that tells R to search twitter for the chosen keyword.

#save tweets as .csv
write.csv(dscience, "science.csv") 

#results will show on the environment. click to view results

