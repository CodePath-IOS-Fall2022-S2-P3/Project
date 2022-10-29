# Project
iOS Fall 2022 Session 2 Pod 3 Project Repository

Original App Design Project - README Template
===
<img src=''![ProjectApp](https://user-images.githubusercontent.com/90231826/198814494-05978bc0-3d11-495f-a37f-d66e6e201feb.gif) title='Video Walkthrough' width='' alt='Video Walkthrough' />


# YouStudy

## Table of Contents
1. [Overview](#Overview)
1. [Product Spec](#Product-Spec)
1. [Wireframes](#Wireframes)
2. [Schema](#Schema)

## Overview
### Description
Our app is a YouTube study app with a streamlined interface that prevents users from getting distracted while watching educational videos. Users can select a topic to get started and then move from there. The recommendations are solely about the topic at hand, preventing users from going off-track while studying.

App that aggregates YouTube videos based on what subject you are studying. This lets you focus on your work and not get distracted by unrelated recommendations.

### App Evaluation
- **Category:** Videos / Productivity / Social
- **Mobile:** Simple easy to use app, allows users to search and scroll through videos and browse categories.
- **Story:** Allows users to browse and watch videos related to the topics they want to explore.
- **Market:** For students or people who want to work with fewer distractions
- **Habit:** Users can also explore endless videos in any category imaginable whenever they want, without the distractions that otherwise would have appeared with normal YouTube
- **Scope:** The main point of this app is to keep students focused on their studies without getting bombarded by distracting irrelevant video reccomendations that eventually makes them go down a rabbit hole of procastination. 

## Product Spec
 
### 1. User Stories (Required and Optional)

**Required Must-have Stories**

* Create table view with video recommendations
* Streamline YouTube to prevent distractions while studying
* Let users select subject and topics to curate videos for those.
* Let users watch the video they have selected
* Let users like videos and add them to playlists
* Let users view a profile page where they can view the playlist of videos
* Infinite scrolling for the recommendations and starter sample videos

**Optional Nice-to-have Stories**

* Let users pick different themes for the app.

### 2. Screen Archetypes

* Login Screen
   * User logs in to the app with Google
   
* Subject Selection Screen
   * User selects the subject that they want to focus on by tapping on an item in the TableView
  
* Subtopic Selection Screen
    * User selects a subtopic for the subject they chose by tapping on the item in the TableView

* Sample Video Screen
    * User gets a list of videos they can start with related to the subtopic they chose.
    * Users tap on a video to be taken to the Main Video Screen

* Main Video Screen with Recommendations
    * User gets streamlines video recommendations based on what they watched. The videos are related to the topic they picked and will build upon what they are learning.
    * Users can watch the video they tapped on, like the video, read a description of the video, read comments, and add the video to a study playlist.
    * When a user taps on a video in the recommendations, it sends them to a Main Video screen with a new video, description, and recommendations based on the new video.
    * Similar youtube UI, however recommended videos are actually related to your topic and not distracting

* Profile Screen with Playlists
    * User can see their Google profile and YouTube banner with a list of playlists that they created that are populated with videos they chose to add to the playlists.

### 3. Navigation

**Tab Navigation** (Tab to Screen)

Most of our app will be using flow navigation and not tab navigation. If we find any use for tab navigation in the future, we will update this portion of the README. Otherwise this will stay as is. Our app will mainly use flow navigation and not tab navigation.

**Flow Navigation** (Screen to Screen)

* Login Screen
   => Subject Screen
* Subject Category
   => Subtopic Screen
* Subtopic Screen
   => Sample Video Screen
* Sample Video Screen
   => Main Video Screen
* Main Video Screen
   => Selecting video from recommendations reloads Main Video Screen with a new video, description, and new recommendations
   => Profile Screen
* Profile Screen
   => Main Video Screen (User selects video in playlist)
   
## Wireframes
<img src="https://i.ibb.co/JKnnjtp/Whiteboard-1-01.png" width=600>

### [BONUS] Digital Wireframes & Mockups

### [BONUS] Interactive Prototype

## Schema 
[This section will be completed in Unit 9]
### Models
YouStudy
|Property|Type|Description|
|--------|----|-----------|
|image|File|image that user posts|
|caption|String|image caption by author|
|activity|Pointer to user|tells user what they did on the video|
|channel|Pointer to user|tells the channel name|
|comments|String|user gets to comment on a video|
|videoId|String|gets name of video|
|captions.download|list|retrieves caption for the video|

Caption can be retreived using:
GET https://www.googleapis.com/youtube/v3/captions

Video can be retrieved using:
GET https://www.googleapis.com/youtube/v3/videos



### Networking
Most of our app will Read and Update and not Create or Delete
* Login Screen
    * (Read) Login user and verify user's login went correct
* Sample Video Screen
    * (Read) Get recommendations for sample videos
* Main Video Screen With Recommendations
    * (Read) Get video
    * (Read) Get caption
    * (Read) Get list of recommendations
    * (Update) Add videos to playlists and update those playlists
    * (BONUS - Create) Create new playlists
* Profile Screen
    * (Read) Get user's profile picture and playlists
    * (Update) Show updated playlists
    * (BONUS - Create) Create new playlists
    


