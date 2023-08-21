# heroku-buildpack-ffmpeg-latest

Push: [![Test](https://github.com/jonathanong/heroku-buildpack-ffmpeg-latest/workflows/Test/badge.svg?branch=master&event=push)](https://github.com/jonathanong/heroku-buildpack-ffmpeg-latest/actions?query=workflow%3ATest+event%3Apush+branch%3Amaster)  
Scheduled: [![Test](https://github.com/jonathanong/heroku-buildpack-ffmpeg-latest/workflows/Test/badge.svg?branch=master&event=schedule)](https://github.com/jonathanong/heroku-buildpack-ffmpeg-latest/actions?query=workflow%3ATest+event%3Aschedule+branch%3Amaster)

> If you'd like to maintain this repository, let me know!

A Heroku buildpack for ffmpeg that always downloads the latest [static build](http://johnvansickle.com/ffmpeg/).
Unlike other build packs, I never compile anything.

## Why this fork?

Since deployments from heroku failed due to a SSL TSL error, I forked the original repo and changed the url to a working url as a temporary workaround to keep deployments coming.
See: https://github.com/jonathanong/heroku-buildpack-ffmpeg-latest/issues/71

## Usage

Run the following from the heroku command line:

```
heroku buildpacks:add --index 1 https://github.com/agieche/heroku-buildpack-ffmpeg-latest.git
```

You can set a custom download URL by setting the variable `FFMPEG_DOWNLOAD_URL`.

Note: This buildpack should be added before the main language buildpack (by using `--index 1`),
since the application process types are calculated from the last buildpack in the list if no
`Procfile` is specified.
