# The AutoVlog Experiment
*AutoVlog is a set of ML enhancements to make recording video diaries simpler.*

**Note: still in active development. Check the issues for what's not done yet.**

## About
In one line: AutoVlog is an intelligent camera.

### Motivation
With development first starting as part of the 2019 Clark Summer Research
Program at The University of Texas at Dallas, AutoVlog was made in an attempt
to help me edit a daily video diary series I produce for YouTube.

In typical computer science fashion, I decided to spend 100 hours building a
machine learning algorithms to edit one video instead of spending the same
amount of time editing three dozen.

The real motivation was: if I could actually create something during my time in
Clark with the knowledge I've learned, why not do it?

While the original concept was to literally build a camera app that could keep
recording almost all the time as footage would be automatically analyzed and
edited, AutoVlog's goals have expanded to encompass much more.

### Objectives and Key Results
**AutoVlog's main goal: reduce the amount of time it takes to create a vlog.** 

Key results:
 - Reducing the amount of time it takes to assemble raw footage by half.
 - Increasing the amount of sleep a video editor gets by 2 hours a night.

### Features
#### Simple video recording [WIP]
Want to simply point and shoot knowing that the camera will capture something
cool? AutoVlog can do that.

AutoVlog will intelligently choose what shots are worth something to you, rank
them, and backup the most important ones.

In the background after you record a clip, AutoVlog will segment them for you
and group similar shots together.

#### Intelligent backup [WIP]
Ever end up recording a lot more than you should just to get that perfect shot?

AutoVlog allows you to backup your footage to a place of your choosing, whether
to Google Drive, to AutoVlog's cloud, and/or a Google Cloud Storage bucket,
~~or even your own FTP server.~~

Also, with your approval, AutoVlog will only backup the good shots to your
personal content library using machine learning. You provide a few examples of a
"good" shot, and it will backup similar clips.

No matter what, you're always in control of what gets saved and what gets deleted.

#### Content suggestions and guidance [WIP]
Want to discover the most salient parts of your videos? AutoVlog can help.

AutoVlog will generate a sentiment map of each of your clips, showing when the
most intense or calm events are happening.

Also, AutoVlog will point out points of interest of your choosing in your clips,
such as profanity or other key words/phrases.

#### Comprehensive shot lists [WIP]
In a rush and just need to know where to start and stop clips? AutoVlog can
do that, too.

AutoVlog generates a list of instructions for editing, clustering clips and
grouping them into logical scenes for easier editing.

Now you don't have to watch the same clip five times during assembly - only
three times!

#### Content library [WIP]
Want to keep track of what subjects for which you've recorded? AutoVlog's
ML-powered entity recognition keeps an index of reoccurring people, places, and
other things throughout your recordings.

This ensures you will ensure that you will never forget when you got the perfect
shot of your cute labrador swimming in the kiddie pool.

### Other Info
The name is probably temporary, but, personally, I think AutoVlog sounds like
a cool codename.

This is primarily an experiment, most of whose features will be modularized and
moved into another more ambitious project, LogDate, the world's most personal
journal.


## Architecture
AutoVlog (AV)'s primary features hinge on the usage of a few different types
of machine learning algorithms.

TODO(docs): Move architecture into its own section.
TODO(docs): Flesh out feature descriptions.

### Simple video recording (SVP)
Probably some form of unsupervised learning with clustering. Maybe the use of
autoencoders to learn simple representations of clip scenes.

### Intelligent Backup (IB)
This will likely use some combination of semi-supervised learning. Users will be
able to suggest what get backed up, but most clips will inevitably be backed up.
Users will also be able to specify a few clips to define the "boundaries" of
what clips should be saved.

If one-shot learning was more developed, then it would work perfectly here for
a user to pick a video that best represents his/her "style" and have the system
create 

### Content Library (CL)
Given that AutoVlog works with video, some kind of CNN + RNN pair might be used
to recognize people and other entities. This is easily supervised learning.
Maybe semi-supervised if users can make suggestions and retrain the model.

Then, like Google Photos, AV could use transfer learning to train a model on
user-specific interests/entities.

Question: is it possible to have word embeddings, but for photos? Maybe this
could be the basis for entity recognition across different contexts.

### Content Suggestions and Guidance (CSG)
Some sort of RNN, maybe an LSTM trained with video, might be used to extract
sentiment from recorded clips.

Some sort of federated learning can help determine what the population of AV
users find interesting.

Also, some kind of survey system like Google Maps could be used to train a model.
Heck, we could develop a whole framework/service for rewarding people for
training models for watching video. Like reCAPTCHA, this system could enforce a
quality dataset by using a known classified example to verify that users aren't
just guessing or deceiving the system.

### Comprehensive shot lists (CSL)
Definitely supervised learning. Maybe semi-supervised at some point with a
sufficiently developed model.

Some sort of deep neural network that accepts inputs for the video and edit
decision lists and outputs a list of timestamps and commands, like "save this"
or "definitely cut this out."

## Development
Open the project in Android Studio or run `./gradle build`.

TODO(docs): Finish development overview.

## License
This project uses the MIT License. Go crazy.