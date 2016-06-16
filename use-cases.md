# crates.io mirror thoughts

## End-user use cases

I want to have options to continue working even if crates.io is down.

- crates.io is down and i want to be able to change a "source" url in my Cargo.toml to manually temporarily fetch metadata and crates from a mirror.
- i want to specify multiple source urls and automatically fall back to a secondary mirror if the primary does not respond to my requests within a timeout, meaning it's down, so that i don't even have to notice that the primary source is down.
- i want to be able to install new crates, update crates, and fetch crate metadata from said mirror.
- i don't want to have to change a bunch of urls in, say, cargo.lock
- i want to be able to find out about community-run mirrors
- i want to be able to verify that code on a mirror is the same as code on crates.io

## Community mirror operator use cases

I want to help the community by running a mirror.

- i want to be able to set it then forget about it most of the time
- i don't want to administrate anything, so my mirror should be read-only
- i want to be a good citizen and don't want to overload crates.io's servers
- i want it to be as cheap as possible, but it can cost some money
- i want to get alerts if my mirror is down so that i can fix it
- i want to know how much traffic my mirror is getting to know if it's worthwhile to keep running it

## Corporate use cases

I'm a company and I want to have my employees use Rust.

- i want to be able to build our projects even when crates.io is down, for example on my CI server or build/deploy server, but i don't need every version of every crate, just ones any developer has installed before (passthrough cache, no administration)
- i want to host private internal-only crates but be able to distribute them within the company as easily as it is to distribute on crates.io.
- i want to whitelist certain authors or packages and only allow installation of those (after manual approval? for each new version?)

## Hosting crates for paid distribution (a la sidekiq)

I'm an author of a crate who wants to charge for access.

- i want to be able to create a basic auth username/PW for each client to use when accessing my server.
