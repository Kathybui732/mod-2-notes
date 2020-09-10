# Intro to Co-Authored Git Commits

### Why

In student projects, I commonly look at contribution graphs to see how much code they worked on, to get an idea if one student is doing more work than others on the project. This can be used for coaching and performance grading.

### How

Start with your `~/.gitconfig` file in your home folder. Add these lines:

```text
[commit]
  template = ~/.gitmessage
```

Next, create a file called `~/.gitmessage`, also in your home folder, that looks like this, including two blank lines at the top:

```text
(blank line)
(blank line)
Co-authored-by: Megan McMahon <32604200+memcmahon@users.noreply.github.com>
```
You can add as many Co-Authors as you like, one per line, but the format must follow the above. When in a team project, please add ALL of your teammates.

GitHub has built-in co-authoring contributions, but it requires that you know the email address used by the co-author. Each co-author can find their "anonymous" GitHub email address by navigating to their email settings page under "Keep my email address private."

If you're trying to set this up yourself and can't reach your co-authors, you can build their anonymous email this way:
their github user_id, a plus sign, their github username, and finally `@users.noreply.github.com`.

To find their github user_id, visit their profile, right-click on their profile photo and "inspect" the image or view the page source. The profile picture URL will look something like this:
`https://avatars2.githubusercontent.com/u/32604200`
The number at the end is their user_id

## Set up a better commit message editor

By default, `git commit` will use an editor called `vim` to edit commit messages. Let's use Atom instead.

In your `~/.gitconfig` file, add the following lines:
```
[core]
  editor = atom --wait
```

Your `.gitconfig` file might look like the following now:
```
[user]
  email = ian.douglas@iandouglas.com
  name = ian douglas

[commit]
  template = ~/.gitmessage

[core]
  editor = atom --wait
```

## How to use it

After you've staged files to commit, simply type `git commit` and hit enter. Atom will include everything from your `.gitmessage` file. Enter new content on line 1, remove any co-authors that did NOT contribute, save and close the file, and you've just co-authored your work.

If you're used to using `git commit -m` on the command line, it will NOT use your `.gitmessage` file. This will allow you to make SOLO contributions to the project.
