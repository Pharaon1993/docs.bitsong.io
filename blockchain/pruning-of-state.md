# Pruning of State

There are four strategies for pruning state. These strategies apply only to state and do not apply to block storage. To set pruning, adjust the `pruning` parameter in the `~/.bitsongd/config/app.toml` file. The following pruning state settings are available:

1. `everything`: Prune all saved states other than the current state.
2. `nothing`: Save all states and delete nothing.
3. `default`: Save the last 100 states and the state of every 10,000th block.
4. `custom`: Specify pruning settings with the `pruning-keep-recent`, `pruning-keep-every`, and `pruning-interval` parameters.

By default, every node is in `default` mode which is the recommended setting for most environments. If you would like to change your nodes pruning strategy then you must do so when the node is initialized. Passing a flag when starting `bitsongd` will always override settings in the `app.toml` file, if you would like to change your node to the `everything` mode then you can pass the `---pruning everything` flag when you call `gaiad start`.

> Note: When you are pruning state you will not be able to query the heights that are not in your store.
