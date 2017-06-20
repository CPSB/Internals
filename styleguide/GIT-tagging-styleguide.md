# Tagging styleguide

**Read also:** [Standard issue labels](../documentatie/github-default-labels.md)

For people who make software, the internet has no shortage of best practice for workflow organization
like [Git flow](https://www.atlassian.com/git/tutorials/comparing-workflows), [relaease versioning](http://semver.org/)
, GitHub, etc. When you get to the topic of issue management, the reading material plumments.

At Activisme-BE, [Github Issues](https://guides.github.com/features/issues/) are the core of just about every action the team takes.
Over the past period of time, we've worked out an internal tagging system that keeps engineering and product efforts organized
across repositories on GitHub. We're sharing the current iteration (and it will keep changing) in case your team is looking for some
workflow inspiration.

## Styleguide for issue tagging.

**How to organize product issues in GitHub** <br>
A sane approach to managing consistency across multiple repositories.

| Category:         | Example labels:                      | Label color:   |
| :---------------- | :----------------------------------- | :------------- |
| Platform          | angular, node                        | `#bfd4f2`      |    
| Problems          | bug, security, production            | `#ee3f46`      |
| Mindless          | chore, legal                         | `#fef2c0`      |
| Experience        | copy, design, ux                     | `#ffc274`      |   
| Environment       | staging, test                        | `#fad8c7`      |
| Feedback          | discussion, rfc, question            | `#cc317c`      |
| Improvements      | enchancement, optimization           | `5ebeff`       |
| Additions         | feature                              | `91ca55`       |
| Pending           | In progress, watchlist               | `#fbca04`      |
| Inactive          | invalid, wontfix, duplicate, on hold | `#d2dae1`      |

## Label groups

We group labels by color, according to broad themes. Labels are consistent across repositories,
except for a few language specific topics. This makes switching between projects easy, since you
don't need domain expertise in order to write an issue.
**New team members can learn the system once, and use it everywhere.**

### `Platform`
If the repository covers multiple parts, this is how we designate where the issue lives
(i.e iOS and ANdroid for cross-platform tablet app).
