# Changelog

## [1.4.2](https://github.com/antmelekhin/ansible-role-mysqld-exporter/compare/v1.4.1...v1.4.2) (2024-11-16)


### Continuous Integration

* use `ubuntu-22.04` instead of `ubuntu-latest` ([11522fb](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/11522fb6198d932738e8431b1d7be6e166120578))
* used `tox` instead `gofrolist/molecule-action` ([#15](https://github.com/antmelekhin/ansible-role-mysqld-exporter/issues/15)) ([10aa245](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/10aa245c23fb3be32ebe8a9bf3d5f22494d4b204))


### Fixes

* **version:** mysqld_exporter updated to `0.16.0` release ([#14](https://github.com/antmelekhin/ansible-role-mysqld-exporter/issues/14)) ([d3b1503](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/d3b150312b5f200707429c2efc00f601123f14a3))


### Styles

* updated indents in jinja templates ([b8f108d](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/b8f108de3bae53ede046fd196830e6863dbcd80a))

## [1.4.1](https://github.com/antmelekhin/ansible-role-mysqld-exporter/compare/v1.4.0...v1.4.1) (2024-10-03)


### Documentation

* fix description for `mysqld_exporter_collectors` variable ([306ccf8](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/306ccf86f82fad65c2c9f2c77e34e59b758c3e53))


### Fixes

* add `become: false` to localhost delegated tasks ([e59707f](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/e59707f5a63c74a1d867d09ef801a28489693ce9))


### Styles

* minor fixes ([9f97560](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/9f9756093e6fd84b9d78ce8fb1ee02c59b801cc7))

## [1.4.0](https://github.com/antmelekhin/ansible-role-mysqld-exporter/compare/v1.3.2...v1.4.0) (2024-08-09)


### Features

* add `meta/argument_specs.yml` file  ([#13](https://github.com/antmelekhin/ansible-role-mysqld-exporter/issues/13)) ([35d3c0a](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/35d3c0ad3cb50a3dbcabc39deee3007d48f2e575))

## [1.3.2](https://github.com/antmelekhin/ansible-role-mysqld-exporter/compare/v1.3.1...v1.3.2) (2024-07-16)


### Documentation

* **README:** update documentation ([e6e160d](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/e6e160d633721356140753f5d4a11f0c7ed55e9f))


### Fixes

* revert the value of `mysqld_exporter_archive_name` variable ([e1b68a5](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/e1b68a522e227e5ec035c01609cc7e729e3558f2))
* update `mysqld_exporter_archive_name` variable ([dd4c0ac](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/dd4c0acdb626356c19abc66897f4b1895b20a5b1))

## [1.3.1](https://github.com/antmelekhin/ansible-role-mysqld-exporter/compare/v1.3.0...v1.3.1) (2024-07-15)


### Fixes

* add `mysqld_exporter_checksum_url` variable ([10bdbdb](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/10bdbdb61305a6459f81c0caa3fcddc6bbd188d7))


### Tests

* clean version output in the `default` scenario ([3690e12](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/3690e12b24d83418564f7e73d5f2b96312b6ea31))

## [1.3.0](https://github.com/antmelekhin/ansible-role-mysqld-exporter/compare/v1.2.5...v1.3.0) (2024-06-05)


### Improvements

* update variables and common role style, add molecule `integration-test` ([#12](https://github.com/antmelekhin/ansible-role-mysqld-exporter/issues/12)) ([52646e1](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/52646e12fdc7dcc3be8f6292ea44979a00d3da49))

## [1.2.5](https://github.com/antmelekhin/ansible-role-mysqld-exporter/compare/v1.2.4...v1.2.5) (2024-05-18)


### Documentation

* **README:** update variables documentation ([69565ef](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/69565ef0493b0819c3c757e9f01c37f150dd947c))


### Styles

* task and molecule instance names ([48fda35](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/48fda357691f6660a3abd889cd4742147607f46f))

## [1.2.4](https://github.com/antmelekhin/ansible-role-mysqld-exporter/compare/v1.2.3...v1.2.4) (2024-05-07)


### Fixes

* fix selinux type for the specified port ([718b338](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/718b338793b331f0e8fb85128a1dcf61bd7763b9))

## [1.2.3](https://github.com/antmelekhin/ansible-role-mysqld-exporter/compare/v1.2.2...v1.2.3) (2024-05-05)


### Code Refactoring

* minor changes ([#11](https://github.com/antmelekhin/ansible-role-mysqld-exporter/issues/11)) ([2d1e19f](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/2d1e19f18db5c2dc2726b7f0f1d02a174e16ff13))


### Continuous Integration

* update workflows and release rules ([#10](https://github.com/antmelekhin/ansible-role-mysqld-exporter/issues/10)) ([ec576b6](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/ec576b64d3652d877c97a27c75285e7f4bc9812e))


### Styles

* add newline to end of file ([1ec64e4](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/1ec64e4071b9bbc8b1ceae68598c1c7ea5f9c690))


### Tests

* add .tox as ignore ([990f527](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/990f527908af3ef2f45498179996632ff8ac0348))
* rm lint from molecule ([e1d1060](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/e1d1060c5bd120dbbfd42c540e5fc58c22872e14))

## [1.2.2](https://github.com/antmelekhin/ansible-role-mysqld-exporter/compare/v1.2.1...v1.2.2) (2023-12-20)


### Fixes

* **version:** mysqld_exporter updated to `0.15.1` release ([#9](https://github.com/antmelekhin/ansible-role-mysqld-exporter/issues/9)) ([ea2ed29](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/ea2ed29075b2f674d20fa35c78363141f058de98))

## [1.2.1](https://github.com/antmelekhin/ansible-role-mysqld-exporter/compare/v1.2.0...v1.2.1) (2023-08-27)


### Fixes

* add fqcn for all modules ([dc72d5b](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/dc72d5b165d802f8a5c18d7af6882dc9735995bd))


### Tests

* add tox ([11df2e1](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/11df2e13c37debf6a6e5e70bd5601da5a47dba07))

## [1.2.0](https://github.com/antmelekhin/ansible-role-mysqld-exporter/compare/v1.1.4...v1.2.0) (2023-07-04)


### Features

* add selinux support ([1087296](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/10872963a4185e0175f58bf85769ac252e69ab25))

## [1.1.4](https://github.com/antmelekhin/ansible-role-mysqld-exporter/compare/v1.1.3...v1.1.4) (2023-07-04)


### Fixes

* rm become ([49bcaa4](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/49bcaa4019752b8a4bb0e997923302d3652c8ce6))


### Styles

* add quotes in notify name ([ea7b06d](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/ea7b06d4d1c075ef26c7747ed86923c57f82fed2))

## [1.1.3](https://github.com/antmelekhin/ansible-role-mysqld-exporter/compare/v1.1.2...v1.1.3) (2023-06-28)


### Continuous Integration

* add release type `improv` ([54cc7ea](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/54cc7ea153b1ffcd6a465b4f90cd338613e499df))
* fix `update-version.sh` script ([c3a9fd7](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/c3a9fd7514f5a9d1843a2507ba9c7733d0eb7be9))
* rm `tagFormat` option, update `commit-analyzer` and `release-notes-generator` blocks ([e0adefa](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/e0adefabba56535004b13350a016186127761d94))


### Documentation

* update README ([ec157ae](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/ec157ae65c6b91ae9ed69948979ba5a2aa8fd230))


### Fixes

* **version:** mysqld_exporter updated to `0.15.0` release ([#7](https://github.com/antmelekhin/ansible-role-mysqld-exporter/issues/7)) ([a7f52b7](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/a7f52b799ca7cb320e750d10cd245bf163b56890))

## [1.1.2](https://github.com/antmelekhin/ansible-role-mysqld-exporter/compare/v1.1.1...v1.1.2) (2023-06-16)

### Tests

* **fix:** rm `remote_src` ([a6d7bf4](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/a6d7bf438c253f5abd0f5cee2fa8419639109f2d))

## [1.1.1](https://github.com/antmelekhin/ansible-role-mysqld-exporter/compare/v1.1.0...v1.1.1) (2023-06-16)

### Documentation

* update README.md and add supported os ([6c33067](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/6c33067cd1c60f8b41dd0cb386da007cadb292d2))

### Fixes

* replace `with_items` on `loop` ([50df892](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/50df8925b2ebe6e9d59c38fcf1ffa42ddacf72b5))

### Tests

* update molecule scenarios ([4de5e83](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/4de5e833976602654cc666d1deb065005800da37))

## [1.1.0](https://github.com/antmelekhin/ansible-role-mysqld-exporter/compare/v1.0.2...v1.1.0) (2023-05-03)

### Features

* add new variables and minor fixes ([#6](https://github.com/antmelekhin/ansible-role-mysqld-exporter/issues/6)) ([a7c3bcf](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/a7c3bcfb40b454167ecaf966cd886e6f4de185ea))

## [1.0.2](https://github.com/antmelekhin/ansible-role-mysqld-exporter/compare/v1.0.1...v1.0.2) (2023-05-01)

### Fixes

* mv `daemon_reload` from tasks to handlers ([#5](https://github.com/antmelekhin/ansible-role-mysqld-exporter/issues/5)) ([f53104a](https://github.com/antmelekhin/ansible-role-mysqld-exporter/commit/f53104a6bad242202e1a9a684b958098f201794e))

## [1.0.1](https://github.com/antmelekhin/ansible-role-mysqld-exporter/compare/v1.0.0...v1.0.1) (2023-05-01)

### Fixes

* update linting rules, use my docker containers in molecule testing and minor fixes ([#2](https://github.com/antmelekhin/ansible-role-mysqld-exporter/pull/2))
