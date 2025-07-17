Title: Fun with pelican
Date: 2020-12-03 10:20
Category: Blog

# My Journey with Pelican: A Static Blog on Raspberry Pi

So I decided to try out Pelican for my blog instead of going with the usual WordPress route. Honestly, it's been quite an experience - some good parts, some frustrating bits, but overall pretty satisfying.

## Why Pelican?

I wanted something simple, fast, and didn't want to deal with database headaches. Plus, writing in Markdown felt natural since I was already doing that for my notes anyway. Pelican seemed like a solid choice - Python-based, good documentation, and active community.

## Setting Up on Raspberry Pi

This was actually the fun part! I had an old Raspberry Pi 4 lying around, so thought why not host my blog there itself? The setup was straightforward - installed Pelican, configured it, and got the basic site running locally first. The Pi handles it pretty well, though initial build times can be a bit slow when you have many posts.

One thing I learned the hard way - make sure you have enough storage space. The themes and generated files can add up quickly, and SD card space on Pi is always at a premium.

## CI/CD Pipeline

Now this is where things got interesting. I set up a simple CI/CD pipeline using GitHub Actions that automatically deploys to my Raspberry Pi whenever I push changes to the main branch. The workflow goes something like:

1. Push markdown files to GitHub
2. GitHub Action triggers
3. Pelican generates the static site
4. Files get deployed to the Pi via SSH

Took me a few attempts to get the SSH keys and permissions right, but once it was working, it felt like magic. Just write, commit, push - and boom, blog is updated. No more manual FTP uploads or anything.

## Theme Exploration

This was probably the most time-consuming part. Pelican has tons of themes available, and I went through quite a few before settling on one. Some looked great but were missing features I wanted, others had too much going on.

I tried the default theme first (boring), then moved to some minimalist ones, experimented with a few colorful options, and finally went with something that balanced simplicity with functionality. Pro tip - test themes thoroughly with your actual content, not just the demo posts. What looks good with lorem ipsum might not work with your writing style.

## The Good Stuff

- Fast loading times - static sites are just snappy
- Version control for everything - blog posts, themes, configuration
- No security worries about WordPress vulnerabilities
- Minimal server requirements - perfect for Pi hosting
- Writing in Markdown is a breeze

## The Not-So-Good

- Theme customization can be tricky if you're not comfortable with Jinja2 templates
- Some plugins aren't as polished as WordPress equivalents
- Limited dynamic features (obviously, since it's static)
- Initial learning curve for configuration

## Final Thoughts

Would I recommend Pelican? Yes, especially if you're comfortable with command line and don't mind getting your hands dirty with configuration. It's perfect for tech blogs, personal sites, or anyone who values simplicity and speed.

The Raspberry Pi hosting adds a nice DIY touch, though you'll want to ensure you have reliable internet and maybe set up some monitoring. My little Pi has been chugging along nicely, serving pages faster than some expensive hosting solutions I've used before.

Overall, it's been a solid choice for my blogging setup. Not perfect, but definitely fits my workflow and requirements well enough.