# Changelog

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
