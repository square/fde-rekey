# fde-rekey

fde-rekey is a simple macOS package, designed to generate a new FileVault2 personal recovery key without any user interaction. It is designed to work on macOS 10.9 - 10.12.3.

## Usage

Download the latest macOS package from the releases tab and import it into your favorite macOS package deployer. There is no need to repackage. Then deploy as you would any other package. Thats it!

##### Crypt2

If you have a `ServerURL` Key defined in the `com.grahamgilbert.crypt` Preference domain, fde-rekey will convert the new key to support [Crypt2][3]. On the next run of Crypt following the use of fde-rekey the key will be escrowed.

##### FileVault RedirectURL (Beta)

fde-rekey will check for the existence of a set FileVault `RedirectURL` configuration key. If found it will allow FileVault to perform the escrow. This feature has only been lightly tested as this is not our escrow method. Please test this feature thoroughly before deploying.

#### Other

If you do not use Crypt2 or a FileVault RedirectURL, fde-rekey will place the new key at `/var/root/fderekey.plist` as root read only.

### Building from Source

fde-rekey is built using [munkipkg][1], you'll need this tool to build from source. Once you have munkipkg installed, clone this repo then run ``munkipkg /path/to/fde-rekey-repo``. You should then find a new package in the fde-rekey build directory.

### Help

If you need help with fde-rekey please join either #filevault or #crypt in the [MacAdmins][4] Slack team.

### License

fde-rekey is under the Apache 2.0 license. See [LICENSE](LICENSE) for details.

### Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

### Credit

A special thank you to contributors of the [macdestroyer][2] project as well as [Graham Gilbert][5] and [Owen Pragel][6] for help with FileVault ReDirection. Without them fde-rekey would not be possible!

[1]: https://github.com/munki/munki-pkg
[2]: https://github.com/google/macops/tree/master/macdestroyer
[3]: https://github.com/grahamgilbert/crypt2
[4]: https://macadmins.herokuapp.com/
[5]: https://grahamgilbert.com/
[6]: https://github.com/opragel
