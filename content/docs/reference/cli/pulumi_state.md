---
title: "pulumi state"
aliases: ["pulumi_state.html"]
expanded_url: /reference/commands/
---



Edit the current stack's state

### Synopsis

Edit the current stack's state

Subcommands of this command can be used to surgically edit parts of a stack's state. These can be useful when
troubleshooting a stack or when performing specific edits that otherwise would require editing the state file by hand.

### Options

```
  -h, --help   help for state
```

### Options inherited from parent commands

```
      --color string                 Colorize output. Choices are: always, never, raw, auto (default "auto")
  -C, --cwd string                   Run pulumi as if it had been started in another directory
      --disable-integrity-checking   Disable integrity checking of checkpoint files
  -e, --emoji                        Enable emojis in the output (default true)
      --logflow                      Flow log settings to child processes (like plugins)
      --logtostderr                  Log to stderr instead of to files
      --non-interactive              Disable interactive mode for all commands
      --profiling string             Emit CPU and memory profiles and an execution trace to '[filename].[pid].{cpu,mem,trace}', respectively
      --tracing string               Emit tracing to a Zipkin-compatible tracing endpoint
  -v, --verbose int                  Enable verbose logging (e.g., v=3); anything >3 is very verbose
```

### SEE ALSO

* [pulumi](/reference/cli/pulumi/)	 - Pulumi command line
* [pulumi state delete](/reference/cli/pulumi_state_delete/)	 - Deletes a resource from a stack's state
* [pulumi state unprotect](/reference/cli/pulumi_state_unprotect/)	 - Unprotect resources in a stack's state

###### Auto generated by spf13/cobra on 7-Jun-2019