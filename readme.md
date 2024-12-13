# Mnemos

Mnemos is simplest version control system (yes, really - the question is, why hasn’t this existed already) - designed for developers who value sanity over ceremony. Track changes, commit versions, revert to previous states, and send changes to remotes.

## Why Mnemos?

- Track files, commit changes, and restore versions without sacrificing goats under a dark blood moon.
- Send changes to remotes and fetch them back without labyrinthine workflows.

We're writing code or poetry here, then tracking, not launching a spaceship — if you want that, write some useful C code instead.

## Features

- Local version vontrol: track files, commit changes, and revert. Done.
- Remote support: add remotes, send commits, fetch changes, or even create a remote repository.
- Human-friendly: simple commands, meaningful messages, no detached HEAD states.

## Compile and Install

### Compile Directly

To compile Mnemos manually, use:

		cc mnemos.c -o mnemos

### Install via Makefile

For an easier installation process, use the provided Makefile:

Build the binary:

		make

Install the binary to /usr/local/bin for global access:

		sudo make install

If you want to uninstall:

		sudo make uninstall

## Usage

### Commands

#### Initialization

Initialize a new Mnemos repository in the current directory:

	    mnemos init

This creates the .mnemos directory to store commits, objects, and the index.

#### Tracking Files

Track specific file:

	    mnemos track <file>

Track all files in the current directory:

	    mnemos track -a

#### Committing Changes

Commit tracked changes with a message:

		mnemos commit <message>

#### Reverting Changes

To find available commit hashes, simply list them with:

	    ls .mnemos/commits

**Why this approach? Because we want to treat everything like a file, when UNIX allows. Your commits are not buried in some crappy database, they are real directories stored in .mnemos/commits, directly accessible with standard tools like ls.**

**This means you don't need special commands or bloat just to see what's saved. *ls* gives you all the context you need. Each commit hash is its own entity, to revert, inspect, or send to remotes without blood moon ceremonies.**

Revert the repository to a specific commit using its hash:

	    mnemos revert <commit_hash>

#### Remote Support

Set a remote repository path:

		mnemos remote <path>

Mnemos remotes work with rsync over ssh. No HTTP, we're not building a web service. When improved it will use 9P(as the gods intended), but for now, rsync over ssh gets the job done.

Send commits to configured remote:

		mnemos send

Fetch commits from configured remote:

		mnemos fetch

Create remote repository from your local Mnemos repository:

		mnemos create-remote <remote_path>

## License

This project is open source. Use it, modify it, share it - just don't sacrifice goats under a blood-red moon.
