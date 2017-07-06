---
title: Prevent tags from being overwritten
description: Learn how to make your tags immutable and don't allow users to
  overwrite a tag if it already exists
keywords: docker, registry, immutable
---

By default, users with access to push to a repository, can push the same tag
multiple times to the same repository.
As an example, a user pushes an image to `site/wordpress:4.7`, and later another
user can push the image with exactly the same name but different functionality.
This might make it difficult to trace back the image to the build that generated
it.

To prevent this from happening you can configure a repository to be immutable.
Once you push a tag, DTR won't anyone else to push another tag with the same
name.

## Make tags immutable

To make tags immutable, in the **DTR web UI**, navigate to the
**repository settings** page, and change **immutability** to **on**.

![](../../images/immutable-repo-1.png)

From now on, users will get an error message when trying to push a tag
that already exists:

```none
docker push dtr.example.org/site/wordpress:4.7
unknown: tag=4.7 cannot be overwritten because dtr.example.org/site/wordpress is an immutable repository
```

## Where to go next

* [Sign images](sign-images/index.md)