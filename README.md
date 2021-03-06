# Jekyll ical tag

Author: Ricky Chilcott https://www.rakefire.io

Description: Pull ICS feed and provide a for-like loop of calendar events

## Installation

To your Gemfile:

`gem 'jekyll-ical-tag', git: "https://github.com/Rakefire/jekyll-ical-tag.git"`

To your `_config.yml`

```yml
plugins:
  - jekyll-ical-tag
```

## Syntax

```html
  {% calendar url: https://space.floern.com/launch.ics reverse: true only_future: true %}
    {{ event.summary }}
    {{ event.description }}
    {{ event.simple_html_description }}
    {{ event.start_time }}
    {{ event.end_time }}
    {{ event.url }}
    {{ event.attendees }}
  {% endcalendar %}
```

## Options

- `reverse` - Defaults to 'false', ordering events by start_time (or reverse start_time).
- `only_past` - Defaults to 'false', limits returned events to start_times before now.
- `only_future` - Defaults to 'false', limits returned events to start_time after now.

- `before_date` - limits returned events to dates before a specific date. This gets parsed with Ruby's Time.parse (e.g. 01-01-2018)
- `after_date` - limits returned events to dates before a specific date. This gets parsed with Ruby's Time.parse (e.g. 01-01-2018).

## Event Attributes:

- `summary` - Title or name of event
- `description` - Notes/description of event
- `simple_html_description` - Notes/description of event with urls auto-linked
- `location` - Location of event
- `start_time` - start time of event
- `end_time` - end time of event
- `url` - url of event, if provided, if not, take the first url from the description.
- `attendees` - [Array] of attendees names/emails
