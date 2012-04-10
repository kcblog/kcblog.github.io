---
layout: post
title: "SVG Gradient Maker"
comments: true
categories: [CSS,SVG]
description: SVG Gradient Maker creates CSS background-image for all browsers.
---
Browsers' CSS incompatibilities always an issue for web developers and designers. There are a lot of alternatives to solve the problems. Most of the people opt to use static images for backgrounds.

Here I created [SVG Gradient Maker](http://svggradmaker.kcblog.net/) to create cross browsers gradient backgrounds with SVG in CSS.

## SVG Gradient Maker 1.0

### Features

- Directions of vertical, horizontal, diagonal, and radial gradients
- Cross browser CSS output optimized and encoded in base64
- Accepts multiple colour offsets in percentages
- More coming soon!

### How to use?

- Pick a direction
- Pick a colour in the start position
- Pick a colour in the end position
- Check the output in the preview area
- Copy the CSS and paste in your style

### Example

![Example 01](http://s3.kcblog.net/images/svggradmaker01.png)

In this example, I pick the direction from top-left to bottom-right, #0088cc as starting colour and #88cc00 as ending colour.

I can now see the output in the preview area with the generated CSS in export area.

{% codeblock %}
background-image: url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxIDEiIHByZXNlcnZlQXNwZWN0UmF0aW89Im5vbmUiPjxsaW5lYXJHcmFkaWVudCBpZD0iZ3JhZCIgZ3JhZGllbnRVbml0cz0idXNlclNwYWNlT25Vc2UiIHgxPSIwJSIgeTE9IjAlIiB4Mj0iMTAwJSIgeTI9IjEwMCUiPjxzdG9wIHN0b3AtY29sb3I9IiMwMDg4Y2MiIG9mZnNldD0iMCIvPjxzdG9wIHN0b3AtY29sb3I9IiM4OGNjMDAiIG9mZnNldD0iMSIgLz48L2xpbmVhckdyYWRpZW50PjxyZWN0IHg9IjAiIHk9IjAiIHdpZHRoPSIxIiBoZWlnaHQ9IjEiIGZpbGw9InVybCgjZ3JhZCkiIC8+PC9zdmc+'); background-size: 100% 100%;
{% endcodeblock %}

Let us try the export CSS now.

{% codeblock %}
<div style="background-image: url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxIDEiIHByZXNlcnZlQXNwZWN0UmF0aW89Im5vbmUiPjxsaW5lYXJHcmFkaWVudCBpZD0iZ3JhZCIgZ3JhZGllbnRVbml0cz0idXNlclNwYWNlT25Vc2UiIHgxPSIwJSIgeTE9IjAlIiB4Mj0iMTAwJSIgeTI9IjEwMCUiPjxzdG9wIHN0b3AtY29sb3I9IiMwMDg4Y2MiIG9mZnNldD0iMCIvPjxzdG9wIHN0b3AtY29sb3I9IiM4OGNjMDAiIG9mZnNldD0iMSIgLz48L2xpbmVhckdyYWRpZW50PjxyZWN0IHg9IjAiIHk9IjAiIHdpZHRoPSIxIiBoZWlnaHQ9IjEiIGZpbGw9InVybCgjZ3JhZCkiIC8+PC9zdmc+'); background-size: 100% 100%; color: #fff; font-size: 24px; padding: 80px 0; text-align: center; text-shadow: 0 0 5px rgba(0, 0, 0, 0.5);">I Love SVG Gradient Maker</div>
{% endcodeblock %}

<div style="background-image: url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxIDEiIHByZXNlcnZlQXNwZWN0UmF0aW89Im5vbmUiPjxsaW5lYXJHcmFkaWVudCBpZD0iZ3JhZCIgZ3JhZGllbnRVbml0cz0idXNlclNwYWNlT25Vc2UiIHgxPSIwJSIgeTE9IjAlIiB4Mj0iMTAwJSIgeTI9IjEwMCUiPjxzdG9wIHN0b3AtY29sb3I9IiMwMDg4Y2MiIG9mZnNldD0iMCIvPjxzdG9wIHN0b3AtY29sb3I9IiM4OGNjMDAiIG9mZnNldD0iMSIgLz48L2xpbmVhckdyYWRpZW50PjxyZWN0IHg9IjAiIHk9IjAiIHdpZHRoPSIxIiBoZWlnaHQ9IjEiIGZpbGw9InVybCgjZ3JhZCkiIC8+PC9zdmc+'); background-size: 100% 100%; color: #fff; font-size: 24px; padding: 80px 0; text-align: center; text-shadow: 0 0 5px rgba(0, 0, 0, 0.5);">I Love SVG Gradient Maker</div>