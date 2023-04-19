# Graffiti Chat Lab

This lab provides a basic working chat application that supports direct messaging and channel-based discussion.
You can try out the app [here](https://graffiti.garden/chat-lab/).

The app is built using the [Graffiti infrastructure](https://graffiti.garden).
You can find reference material on Graffiti's Vue interface [here](https://graffiti.garden/vue-plugin).

## Overview of Graffiti

Graffiti apps are designed to be both *interoperable* and *flexible*.
That means that you should be able to send messages from one chat app and receive them in another
while **also** having the freedom to add features to your chat app that might change that data schema it uses.

To meet both of those design goals, Graffiti uses the following pattern:
- Find a large collection of potentially relevant data.
- Filter out any data that your app cannot use.
- Process the remaining data for display in your interface.

This chat app uses this work flow to:
- Fetch all data in your "inbox" or a channel, filter that data for message data, and display those messages.
- Fetch all data related to a user's identity, filter that data for the user's most recent profile data, and display name in the profile.

## Graffiti Objects

The data that we're filtering is an array of special JSON objects that have the following default properties:

- `published`: This is the timestamp that the data was published.
- `updated`: This is the timestamp that the data was last updated
- `id`: This is a unique identifier for the object itself.
- `actor`: This actor is a unique identifier corresponding to the creator of the object.
