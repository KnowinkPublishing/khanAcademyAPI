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

```
description: "Watch videos and practice your skills for almost any math subject.",
internal_id: "x7a488390",
node_slug: "math",
icon_large: "https://cdn.kastatic.org/genfiles/topic-icons/icons/arithmetic.png-af7472-416.png",
key: "ag5zfmtoYW4tYWNhZGVteXIUCxIFVG9waWMiCXg3YTQ4ODM5MAw",
translated_title: "Math",
id: "math",
icon: "https://cdn.kastatic.org/genfiles/topic-icons/icons/arithmetic.png-af7472-128c.png",
kind: "Topic",
hide: false,
relative_url: "/math",
title: "Math",
url: "https://www.khanacademy.org/math",
edit_slug: "",
translated_description: "Watch videos and practice your skills for almost any math subject.",
translated_standalone_title: "Math",
standalone_title: "Math"
```
## Subtopics

By replacing _root_ in the url to get all topcis with the _relative_url_ a developer can access the subtopics. To retrieve all the math subtopics, transform the url to https://www.khanacademy.org/api/v1/topic/math

Use the pattern above, filter _children_, _node_slug_, to get the math subtopic. At this point the key _kind_ becomes relevant. If this value is _topic_ then there is another level of entries for this topic. 

```
description: "Learn early elementary math—counting, shapes, basic addition and subtraction, and more.",
internal_id: "xb5feb28c",
node_slug: "early-math",
icon_large: "https://cdn.kastatic.org/genfiles/topic-icons/icons/early_math.png-314b80-416.png",
key: "ag5zfmtoYW4tYWNhZGVteXIUCxIFVG9waWMiCXhiNWZlYjI4Yww",
translated_title: "Early math",
id: "early-math",
icon: "https://cdn.kastatic.org/genfiles/topic-icons/icons/early_math.png-314b80-128c.png",
kind: "Topic",
hide: false,
relative_url: "/math/early-math",
title: "Early math",
url: "https://www.khanacademy.org/math/early-math",
edit_slug: "",
translated_description: "Learn early elementary math—counting, shapes, basic addition and subtraction, and more.",
translated_standalone_title: "Early math",
standalone_title: "Early math"
```

However, if it has something other than _topic_ as a value, then you have reached a lesson. The key _url_ will provide you with the location of the lesson so it can be embedded your app. 

```
description: "Sal counts squirrels and horses.",
internal_id: "x9b4a5e7a",
node_slug: "v/counting-with-small-numbers",
icon_large: null,
key: "ag5zfmtoYW4tYWNhZGVteXIUCxIFVmlkZW8iCXg5YjRhNWU3YQw",
translated_title: "Counting with small numbers",
id: "counting-with-small-numbers",
icon: null,
kind: "Video",
hide: false,
relative_url: "/video/counting-with-small-numbers",
title: "Counting with small numbers",
url: "https://www.khanacademy.org/video/counting-with-small-numbers",
edit_slug: "edit/v/x9b4a5e7a",
translated_description: "Sal counts squirrels and horses.",
translated_standalone_title: null
```
## Subtopic Node Slugs

Something to note here are the node slug values, as you reach the actual topic content the node slug will be prefaced with the type of content - v for video, e for exercise, etc. 

    math

      early-math

         cc-early-math-counting-topic 

             cc-early-math-counting

                 v/counting-with-small-numbers

                 e/counting-out-1-20-objects

                 v/counting-in-order

                 e/counting-objects

                 e/one-more--one-less

             cc-early-math-numbers-120