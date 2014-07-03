Healthy Hackathon
=======

Holds documentation, site, and any tools used to run Khan Academy's Healthy Hackathon

**Deploying**

healthyhackathon.khanacademy.org is hosted on S3 (bucket:
healthyhackathon.khanacademy.org), setup as a static website
using https://github.com/laurilehmijoki/s3_website

If you want to deploy an update:

1) Install the s3_website tool from that repo and use it to push to the above
bucket. Note that you're gonna need to create a config file in site/ that looks
something like this:

```
s3_id: {AWS Access Key Id w/ S3 access}
s3_secret: {AWS Secret}
s3_bucket: healthyhackathon.khanacademy.org

max_age:
  "css/*": 6000
  "js/*": 6000
  "img/*": 6000

gzip:
  - .html
  - .jpg
  - .png
  - .js
  - .css
  - .md
```

2) From the site/ directory, run ```s3_website push --site=.```
