# multi-repo-git-bisect
Ideas for doing a git bisect across multiple repos:

- As in https://stackoverflow.com/questions/9711592/repo-bisect-for-debugging-android, I think the default behaviour would be to bisect over dates (assumes you are always developing with the up-to-date repos).
- Alternatively, you could make this behaviour "fuzzy," in that the search is allowed to "walk" a few days or weeks outside of this behaviour, in case one of the repos fell behind (wasn't pulled) while you were developing.
- Optimally, you could specify the order of dependencies, and this would allow you to move quickly over some (i.e., fix dependency A at v1.1, while going through dependency B from v0.9-v0.10-v0.11, etc.). This is an efficiency thing so you can build B (which depends on A), without having to build the whole stack again.
