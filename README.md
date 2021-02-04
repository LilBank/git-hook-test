# Feature Files

This is a repository for keeping all the feature files.

## Validate Commit Message Installation

1. With any text editor or IDE, find `.git` folder. The folder
will be hidden so make sure to make change on your settings.

2. Go to `.git/hooks`

```
  $ cd hooks
```

3. Find `commit-msg.sample` and replace the code with this snippet.

```
#!/usr/bin/env ruby
message_file = ARGV[0]
message = File.read(message_file)

$regex = /\[DEPTH: (\d+)\]/

if !$regex.match(message)
  puts "[WARNING] Your message must be and contain this [JIRA: XXX]"
  exit 1
end
```

4. Rename file `commit-msg.sample` to `commit-msg` and you're all set.

## Some Changes
