# Posting Machine
A pretty simple script to help you avoid repeat posting images/videos, if you care about that sort of thing.

Configure in `config.sh`, which is called before the majority of `./postcheck`.

My vision for using this:
```
$ ./postcheck [postname]
```
will navigate to `$POST_HOME/postname/` (configured in `config.sh`), and check if any of the pictures (by filename) have been included in a post before.

## How it works

It does not actually scrape the posts (future possibility?) but rather, everytime `postcheck` is called with a post, it "registers" those filenames along with the post they're associated with.

## Use case

I want to post a batch of pictures to a site, so I copy them over to a folder `mypost` in `$POST_HOME`, then run `$ ./postcheck mypost`.
I am alerted that one of the pictures, I have posted before, under the post labeled "oldpost", and am prompted whether I would like to remove the offending file from `mypost`.
Afterwards, I am asked one last time to confirm what I'm registering the post as, in terms of what files are included.
Afterwards, I post the remaining pictures, and delete them from the file.  That does not affect whether they are recorded by the posting machine.

## Files at play

I plan to make `.posts` be a simple text file of key value pairs for post:associatedfilename.  Hopefully simple enough to be hand edited if needed.
