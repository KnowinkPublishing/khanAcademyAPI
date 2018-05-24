# Khan Academy API

## Purpose:
_To provide a reliable data map of the Khan Academy API. Specifically the node_slug key values._

## Khan Academy Documentation:
https://api-explorer.khanacademy.org/

## Base URL:

The base url for the Khan Academy API is: _https://www.khanacademy.org/api/v1_

## Main Topics

From this URL a developer can view the root list of topics by appending _topic/root_. (https://www.khanacademy.org/api/v1/topic/root)

This will return a JSON file. Filter for the _children_ key, which returns an array of dictionaries. Within each dictionary will be a _node_slug_ key, which will contain the topic, such as 'math'. The title key will contain a user friendly display of the topic, such as 'Math'. And the _relative_url_ key will give you the path to the subtopics, such as '/math'

## Subtopics

By replacing _root_ in the url to get all topcis with the _relative_url_ a developer can access the subtopics. To retrieve all the math subtopics, transform the url to https://www.khanacademy.org/api/v1/topic/math


