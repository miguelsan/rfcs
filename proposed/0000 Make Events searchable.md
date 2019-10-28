# 0000 - Make Events searchable

## Status
[status]: #status

Proposed

## Summary
[summary]: #summary

Events are not included in search and filter so far. If Events are activated, all of them are allways visible, which is not usable for our clients. We need to make them searchable.

## Context
[context]: #context

Since the the beginning of the year, https://pioneersofchange.org/landkarte/ is using the event fuction at kvm. In Minsk Hackers developed the entry form for new events. As soon as this is online and in use by many, the map will be useless if you can not filter these events.


## Decision
[decision]: #decision

We will improve the backend-API so that events are searchable till the end of the year.
At least for hashtags it has to work!

## Consequences
[consequences]: #consequences

Events are searchable
Is the frontend more complex? Does it need to send two search request for every search?
> This section describes the resulting context, after applying the decision. All consequences should be listed here, not just the "positive" ones. A particular decision may have positive, negative, and neutral consequences, but all of them affect the team and project in the future.

## References
[references]: #references

- Can we avoid having an own API for events but somhow to use the same so that the complexity in the frontend does not increase? Should the frontend "feel" as if there where only one databsis? https://github.com/kartevonmorgen/kartevonmorgen/issues/575
