# Damien's Work/Dev Mac Setup Playbook

Ever since I first used Ansible back when Red Hat acquired Ansible back in 2016, I've had some version of a "Workstation Setup Playbook".  My [initial version](https://github.com/deversmann/laptop-setup), worked on my work RHEL CSB (corporate standard build) Lenovo laptop.  It just handled some initial installs and connecting to the internal network before the VPN was configured.  There have been several versions over the years, usually inspired by [Jeff Geerling's](https://github.com/geerlingguy/mac-dev-playbook), most lost to history.  Every 3 years, as Red Hat issued me a new laptop, I'd dust an old one off, decide it was severely outdated and decide to rewrite it. This is one of those times.

This playbook works in tandem with my [dotfiles](https://github.com/deversmann/dotfiles) project.  The dotfiles project kicks off this one as part of its run.  That's a temporary copy though.  My intention is for this to be used a little more frequently to keep things organized.

## Steps Taken By the Playbook
1. Configure passwordless `sudo` if it's not already set up
2. Install a list of Managed Software Center (MSC aka Munki) packages.
    - MSC is like the app store but enterprise in nature.
    - It has required and optional packages.  The playbook only deals with the optional ones.
    - It leverages my old [Ansible role](https://galaxy.ansible.com/ui/standalone/roles/deversmann/msc/)([github project](https://github.com/deversmann/ansible-role-msc)) from years ago.  It worked exactly as it did back then.
3. Installs [Homebrew](https://brew.sh) and optionally kicks off `brew bundle` to install things from a `Brewfile`
4. Installs [Oh-My-ZSH](https://ohmyz.sh) and optionally customizes it.

## TODOs
- [ ] Add in the ability to choose between a "Work Install" and a "Personal Install" where MSC isn't used and different software lists/configs are used
- [ ] Add in more OS personalization like Terminal profiles, etc
- [ ] Adding in other setup like creating directories and checking out projects.

## Inspiration
- https://github.com/rickmanley-nc/laptop-configure
- https://github.com/geerlingguy/mac-dev-playbook
- https://github.com/mrlesmithjr/developers-workstation-setup

