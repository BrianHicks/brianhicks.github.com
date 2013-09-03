---
title: Post Script
date: 2013-09-03
layout: default
---
After reading [this Scott Hanselman post on
keystrokes](http://www.hanselman.com/blog/DoTheyDeserveTheGiftOfYourKeystrokes.aspx)
I've realized that while I've tweeted quite a bit in the past couple of years
I've hardly ever blogged, when that would be much more useful (not to mention
sustainable.)

So, here's a little script wrapper for posting *quickly* to a Jekyll blog
hosted on your filesystem.

Aliases are helpful to use this - I have this particular blog aliased as:

    alias blog="post ~/code/sideprojects/brianhicks.github.com/_posts -c -p 'git push'"

Then I can just `blog "Post Script"` to generate some boilerplate for this
post, for instance. When I save and quit vim, it'll get pushed to GitHub pages
automatically.

Hopefully I can remember to "post more in the future" although that's an empty
promise of many a personal tech blog.

Without further ado, the wrapper (the irony of this being written in Python is
not lost on me, for the record):

    #!/usr/bin/env python
    "Wrapper for posting to a Jekyll blog from the command line"
    import argparse
    from datetime import datetime, timedelta
    import operator
    import os
    import re
    from subprocess import call

    parser = argparse.ArgumentParser(__doc__)

    parser.add_argument(
        'where',
        help='Which directory to post to'
    )
    parser.add_argument('title', help='Title of the post')
    parser.add_argument(
        '-d', '--date',
        default=datetime.now().strftime('%Y-%m-%d'),
        help='Date the post should be published (ex: 2013-06-19)',
    )
    parser.add_argument(
        '-o', '--offset',
        help='Days to offset post by, based on latest post (ex: +2 or -5)',
    )
    parser.add_argument(
        '-n', '--offset-now',
        action='store_true',
        help='If present, offset from current date instead of last post'
    )
    parser.add_argument(
        '-c', '--commit-after',
        action='store_true',
        help='If present, add and commit to git afterward'
    )
    parser.add_argument(
        '-p', '--post',
        help='Extra command to run after hook, if committed'
    )

    if __name__ == '__main__':
        args = parser.parse_args()

        # transform the parsed arguments
        slug = re.sub('[^\w-]', '', re.sub('\s+', '-', args.title).lower())

        date = args.date

        # do relative posting dates, from the latest post. Override date if provided.
        if args.offset:
            if args.offset_now:
                base = datetime.now()
            else:
                latest = sorted([x.split('-') for x in os.listdir(args.where)], reverse=True)[0]
                base = datetime(int(latest[0]), int(latest[1]), int(latest[2]))

            op = operator.sub if args.offset.startswith('-') else operator.add

            date = datetime.strftime(op(base, timedelta(int(args.offset[1:]))), '%Y-%m-%d')

        title = '%s-%s.md' % (date, slug)
        filename = os.path.expanduser(os.path.join(args.where, title))

        text = "---\ntitle: %s\ndate: %s\nlayout: default\n---" % (args.title, date)

        if not os.path.exists(filename):
            with open(filename, 'w') as post:
                post.write(text)

        call([os.environ.get('EDITOR', '/usr/local/bin/vim'), filename])
        if args.commit_after:
            os.chdir(args.where)
            call(['git', 'add', title])
            call(['git', 'commit', '-m', 'Add %s' % title])

            if args.post:
                os.chdir(os.path.abspath(
                    os.path.join(args.where, '..') if '_posts' in args.where else args.where
                ))
                call(args.post.split())
