// Author: Fırat Vural Çamlıca
// Project: # ideology
// Title: The Relationship Between Ideological Rhetoric and Emotional Expression on Reddit and Twitter

# The data from Twitter should be followed manually on the elaboration of profiles "

install.packages"rtweet")
library(rtweet)
install.packages("ROAuth")
library(ROAuth)
install.packages("twitteR")
library(twitteR)
install.packages("rtweet", repos = 'https://ropensci.r-universe.dev')
library(rtweet)

# TWITTER

consumer_key <- "Your consumer key"
consumer_secret <- "Your consumer secret"
access_token <- "Your access token"
access_token_secret <- "Your access token secret"

setup_twitter_oauth(consumer_key, consumer_secret, access_token, access_token_secret)

get_tokens

# You can check your connection testing with tweet by R
tw <- updateStatus ("x")


account <- "x" 
account.timeline <- userTimeline(account, n=300, includeRts=FALSE)

TrialRepublican <- twListToDF(account.timeline)
R1 = subset(TrialRepublican, select = c(text))
write.csv(R40, file="Republican1.csv")



# REDDIT

install.packages(RedditExtractoR)
library(RedditExtractoR)

RepublicanThreadsW <- find_thread_urls(subreddit="Republican", sort_by="new", period="week")

RepublicanCommentsW <- get_thread_content(RepublicanThreads$url)

RepublicanReddit = subset(RepublicanThreads, select = c(title))

write.csv(RepublicanReddit, file="RepublicanReddit.csv")

> View(RepublicanThreads)
> RepublicanComments <- get_thread_content(RepublicanThreads$url)
> View(RepublicanComments)
> View(RepublicanComments$threads)
> View(RepublicanComments$comments)

DemocratThreadsW <- find_thread_urls(subreddit="democrats", sort_by="new", period="week")

DemocratsComments <- get_thread_content(DemocratThreads$url)

DemocratsReddit = subset(DemocratThreads, select = c(title))

write.csv(DemocratsReddit, file="DemocratsReddit.csv")
