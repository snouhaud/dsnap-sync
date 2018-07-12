# dsnap-sync TODO #

## open tasks ##

- dsnap-sync: supply saving streams to tape or other filesystemd
  e.g like documented in btrfs wiki
  # btrfs subvolume snapshot -r / /my/snapshot-YYYY-MM-DD && sync
  # btrfs send /my/snapshot-YYYY-MM-DD | ssh user@host 'cat >/backup/home/snapshot-YYYY-MM-DD.btrfs'
  # btrfs subvolume snapshot -r / /my/incremental-snapshot-YYYY-MM-DD && sync
  # btrfs send -p /my/snapshot-YYYY-MM-DD /my/incremental-snapshot-YYYY-MM-DD | ssh user@host 'cat >/backup/home/incremental-snapshot-YYYY-MM-DD.btrfs'
- dsnap-sync: introduce snapper config handling for parent/child types
  disk2disk      -> parent to child on btrfs (default: snapshot)
  disk2disk2disk -> child to child on btrfs(clone snapshot)
  disk2disk2tape -> child to tape on non-btrfs (send btrfs-stream of snapshot if incremental, copy snapshot if first/full) 
- dsnap-sync: parallel tasks per config
- dsnap-sync: introduce snapper function: important snapshots
  Important snapshots have important=yes in the userdata
  let snapper cleanup/timeline mechanisms respect this

## finished tasks ##

- dsnap-sync: refine backupdir with --interactive
- dsnap-sync: visualize backup progress (using pv)
- dsnap-sync: use snapper to administer target synced snapshots
- dsnap-sync: introduce selectable subvolid option
- dsnap-sync: refine paramteter parsing
- dsnap-sync: refine functions structure
- dsnap-sync: port as posix compatible
- dsnap-sync: introduce selectable subvolid option
- dsnap-sync: use snapper to administer target synced snapshots
