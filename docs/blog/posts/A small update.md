---
date:
  created: 2025-10-31
description: test test test
---
This time I have set out to achieve a few small things. I wanted my blog to feel a little bit more personal with a logo and favicon and on the rare occasion where I would like to share a link to this page, I don't want to see an error message about Open Graph info missing.

I fixed both things. I will, full of shame, admit that I have used an LLM to generate a basic icon/logo which I touched up in GIMP. The generation process was frustrating, though. The "AI" spat out unappealing graphics most of the time. You could immediately tell it was generated, be it style or plain retardation of the imagery.. Was it faster or better than just using an existing design from an icon pack? I am not sure, but no time savings were made.

My second issue was resolved by activating the `social` plugin and modifying the pipeline to install additional depndencies before building the site. After adding the `site_description` social cards started appearing properly when linking to my site.
What I am missing from the `mkdocs-material` documentaion is a clear indication where I need to put the Open Graph meta information for all pages inside my project. In posts I just yolo'd it and put `description: ` beneath `date: `. Manually setting the desciption for carefully curated pages is ok, but this will not work long term for blog posts.

There probably is an automated way to make the description be the first paragraph of the post. I just haven't found it yet.
