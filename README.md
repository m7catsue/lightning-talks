# LightningTalks
A system for accepting votes for lightning talks.

## Bootstrapping

### Development
**First**: you must have a running mongodb instance accessible.
```sh
brew install mongodb
ln -sfv /usr/local/opt/mongodb/*.plist ~/Library/LaunchAgents
launchctl load ~/Library/LaunchAgents/homebrew.mxcl.mongodb.plist
```
**Second**: Pull down the code from git, create a virtual environment and install requirements.
```sh
git clone git@github.com:ireapps/lightning-talks.git && cd lightning-talks
mkvirtualenv lightningtalks
pip install -r requirements.txt
```

**Third**: Load some fake data.
```sh
fab fake_data
```

### Production
TKTK

## Overview
### Routes
####`/api/user/?_id=97984267-ab75-46c4-b113-016a5555e92b`
```json
{
    "sessions_pitched": [
        "60b27f91-9506-498c-8758-90edfa1ad0b1",
        "d2650553-9e4f-4dc2-adee-f831419cf3e0",
        "ef16edee-2292-49c8-b990-4d52b77529eb"
    ],
    "sessions_voted_for": [
        "ef16edee-2292-49c8-b990-4d52b77529eb",
        "d2650553-9e4f-4dc2-adee-f831419cf3e0"
    ],
    "_id": "97984267-ab75-46c4-b113-016a5555e92b",
    "email": "jeremy.bowers@fake.fake"
}
```
####`/api/session/?_id=60b27f91-9506-498c-8758-90edfa1ad0b1`
```json
{
    "votes": 1,
    "_id": "60b27f91-9506-498c-8758-90edfa1ad0b1",
    "description": "This is a test description that is rather long. This is a test description that is rather long. This is a test description that is rather long. This is a test description that is rather long. This is a test description that is rather long. This is a test description that is rather long. This is a test description that is rather long. This is a test description that is rather long. This is a test description that is rather long. This is a test description that is rather long. This is a test description that is rather long. This is a test description that is rather long.",
    "created": 1416886310,
    "title": "Having The Time Of Your Life",
    "updated": 1416886667,
    "user": "97984267-ab75-46c4-b113-016a5555e92b",
    "accepted": false
}
```

## Models
TKTK

## Tests
To run tests, do `fab tests`.