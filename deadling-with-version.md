for new projects we will start with v0
and upon release we will increment to v1

the issue is we tie our release numbers to our releases
and going forward we are starting to use a semi ci process
in that process the versions will increment freely and quickly
we have already seen this. Recurly has dozens on minor versions and an untold amount of patches

maybe it's time to seperate our spring numbers from the app versions
would them being out of sync be a big deal?
we can tag versions and also tag good releases
use release tags to manage the jira spring version and let the project version run freely 

vtags for dev releases
releasetags for jira sprints

with tickets that don't ship there are times when a bug fix is included that legitimatly should go wether or not the project is shipped. 

branching from main always would allow devs the freedom to implement bug fixes without having to go through the ticketing system for a simple fix.

in the changelogs we can include ticket numbers if exists and not if they don't and they will tell QA all they need on the status of the change

if QA is not able to get the change from the description fully they will be able to ask the devs by tracking the versions they approve

this will free up dev to have serveral versions, and one get's releases to qa
then qa can have serveral versions, some that they approve
and sent to stage
and even fewer get released
each stage should add a git tage for the state-version

**commits with tags**
v{#.#.#}-dev
v{#.#.#}-qa
v{#.#.#}-stage
v{#.#.#}-prod + sprint-v{#}

