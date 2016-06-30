# Bosh Add-On for SaltMinion

If you need the Salt Minion installed in every VM of your infrastructure then deploy this BOSH release.

## Usage

### Create & Upload the BOSH release

To use this BOSH release, first create the dev release, then the final release, then upload it to your BOSH director:

```
bosh target BOSH_HOST
git clone https://github.com/kartiklunkad26/salt-minion-bosh-release.git
cd salt-minion-bosh-release
bosh create release --force
bosh create release --force --final
bosh upload release
```

### Create a BOSH deployment manifest

Please refer to the file salt-addon.yml for an example of the deployment manifest.

### Update the runtime-config

Using the previous created deployment manifest, now we can deploy it:

```
bosh update runtime-config salt-addon.yml
bosh -n deploy
```


