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

### `Problems`
Issues that make the product feel broken. High Priority, especially if its present in production.

### `Mindless`
Converting measurements, reorganizing folder structure, and other necessary (but less impactful) tasks.

### `Experience`
Affect user’s comprehension, or overall enjoyment of the product. These can be both opportunities and “UX bugs”.

### `Environment`
Server environment. With good QA, you'll identify issues on test and staging deployments.

### `Feedback`
Requires further conversation to figure out the action steps. Most feature ideas start here.

### `Improvements`
Iterations on existing features or infrastructure. Generally these update speed, or improve the quality
of results. Adding a new "Owner" field to an "Calendar" model in the API, for example.

### `Additions`
Brand new functionality. New pages, workflows, endpoints, etc.

### `Pending`
Taking action, but need a few thing happen first. A feature that needs dependencies merged, or a bug that needs further data.

### `Inactive`
No action needed or possible. The issue is either fixed, addressed better by other issues, or just out of product scope.

