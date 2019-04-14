# Release Notes for 5.8.x

## [Unreleased](https://github.com/laravel/framework/compare/v5.8.11...5.8)


## [v5.8.11 (2019-04-10)](https://github.com/laravel/framework/compare/v5.8.10...v5.8.11)

### Added
- Allowed to call `macros` directly on `Illuminate\Support\Facades\Date` ([#28129](https://github.com/laravel/framework/pull/28129))
- Allowed `lock` to be configured in `local filesystems` ([#28124](https://github.com/laravel/framework/pull/28124))
- Added tracking of the exit code in scheduled event commands ([#28140](https://github.com/laravel/framework/pull/28140))

### Fixed
- Fixed of escaping single quotes in json paths in `Illuminate\Database\Query\Grammars\Grammar` ([#28160](https://github.com/laravel/framework/pull/28160))
- Fixed event discovery with different Application Namespace ([#28145](https://github.com/laravel/framework/pull/28145))

### Changed
- Added view path to end of compiled blade view (in case if path is not empty) ([#28117](https://github.com/laravel/framework/pull/28117), [#28141](https://github.com/laravel/framework/pull/28141))
- Added `realpath` to `app_path` during string replacement in `Illuminate\Foundation\Console\Kernel::load()` ([82ded9a](https://github.com/laravel/framework/commit/82ded9a28621b552589aba66e4e05f9a46f46db6))

### Refactoring
- Refactoring of `Illuminate\Foundation\Events\DiscoverEvents::within()` ([#28122](https://github.com/laravel/framework/pull/28122), [006f999](https://github.com/laravel/framework/commit/006f999d8c629bf87ea0252447866a879d7d4a6e))


## [v5.8.10 (2019-04-04)](https://github.com/laravel/framework/compare/v5.8.9...v5.8.10)

### Added
- Added `replicating` model event ([#28077](https://github.com/laravel/framework/pull/28077))
- Make `NotificationFake` macroable ([#28091](https://github.com/laravel/framework/pull/28091))

### Fixed
- Exclude non-existing directories from event discovery ([#28098](https://github.com/laravel/framework/pull/28098))

### Changed
- Sorting of events in `event:list` command ([3437751](https://github.com/laravel/framework/commit/343775115722ed0e6c3455b72ee7204aefdf37d3))
- Removed path hint in compiled view ([33ce7bb](https://github.com/laravel/framework/commit/33ce7bbb6a7f536036b58b66cc760fbb9eda80de))


## [v5.8.9 (2019-04-02)](https://github.com/laravel/framework/compare/v5.8.8...v5.8.9)

### Added
- Added Event Discovery ([#28064](https://github.com/laravel/framework/pull/28064), [#28085](https://github.com/laravel/framework/pull/28085))

### Fixed
- Fixed serializing a collection from a `Resource` with `preserveKeys` property ([#27985](https://github.com/laravel/framework/pull/27985))
- Fixed: `SoftDelete::runSoftDelete` and `SoftDelete::performDeleteOnModel` with overwritten `Model::setKeysForSaveQuery` ([#28081](https://github.com/laravel/framework/pull/28081))

### Changed
- Update forever cache duration for database driver from minutes to seconds ([#28048](https://github.com/laravel/framework/pull/28048))

### Refactoring:
- Refactoring of `Illuminate\Auth\Access\Gate::callBeforeCallbacks()` ([#28079](https://github.com/laravel/framework/pull/28079))


## [v5.8.8 (2019-03-26)](https://github.com/laravel/framework/compare/v5.8.7...v5.8.8)

### Added
- Added `Illuminate\Database\Query\Builder::forPageBeforeId()` method ([#28011](https://github.com/laravel/framework/pull/28011))

### Fixed
- Fixed `BelongsToMany::detach()` with custom pivot class ([#27997](https://github.com/laravel/framework/pull/27997))
- Fixed incorrect event namespace in generated listener by `event:generate` command ([#28007](https://github.com/laravel/framework/pull/28007))
- Fixed unique validation without ignored column ([#27987](https://github.com/laravel/framework/pull/27987))

### Changed
- Added `parameters` argument to `resolve` helper ([#28020](https://github.com/laravel/framework/pull/28020))
- Don't add the path only if path is `empty` in compiled view ([#27976](https://github.com/laravel/framework/pull/27976))

### Refactoring
- Refactoring of `env()` helper ([#27965](https://github.com/laravel/framework/pull/27965))


## [v5.8.6-v5.8.7 (2019-03-21)](https://github.com/laravel/framework/compare/v5.8.5...v5.8.7)

### Fixed
- Fix: Locks acquired with block() are not immediately released if the callback fails ([#27957](https://github.com/laravel/framework/pull/27957))

### Changed
- Allowed retrieving `env` variables with `getenv()` ([#27958](https://github.com/laravel/framework/pull/27958), [c37702c](https://github.com/laravel/framework/commit/c37702cbdedd4e06eba2162d7a1be7d74362e0cf))
- Used `stripslashes` for `Validation\Rules\Unique.php` ([#27940](https://github.com/laravel/framework/pull/27940), [34759cc](https://github.com/laravel/framework/commit/34759cc0e0e63c952d7f8b7580f48144a063c684))

### Refactoring
- Refactoring of `Illuminate\Http\Concerns::allFiles()` ([#27955](https://github.com/laravel/framework/pull/27955))


## [v5.8.5 (2019-03-19)](https://github.com/laravel/framework/compare/v5.8.4...v5.8.5)

### Added
- Added `Illuminate\Database\DatabaseManager::setReconnector()` ([#27845](https://github.com/laravel/framework/pull/27845))
- Added `Illuminate\Auth\Access\Gate::none()` ([#27859](https://github.com/laravel/framework/pull/27859))
- Added `OtherDeviceLogout` event ([#27865](https://github.com/laravel/framework/pull/27865), [5e87f2d](https://github.com/laravel/framework/commit/5e87f2df072ec4a243b6a3a983a753e8ffa5e6bf))
- Added `even` and `odd` flags to the `Loop` variable in the `blade` ([#27883](https://github.com/laravel/framework/pull/27883))

### Changed 
- Add replacement for lower danish `�` ([#27886](https://github.com/laravel/framework/pull/27886))
- Show error message from exception, if message exist for `403.blade.php` and `503.blade.php` error ([#27893](https://github.com/laravel/framework/pull/27893), [#27902](https://github.com/laravel/framework/pull/27902))

### Fixed
- Fixed seeding logic in `Arr::shuffle()` ([#27861](https://github.com/laravel/framework/pull/27861)) 
- Fixed `Illuminate\Database\Query\Builder::updateOrInsert()` with empty `$values` ([#27906](https://github.com/laravel/framework/pull/27906))
- Fixed `Application::getNamespace()` method ([#27915](https://github.com/laravel/framework/pull/27915))
- Fixed of store previous url ([#27935](https://github.com/laravel/framework/pull/27935), [791992e](https://github.com/laravel/framework/commit/791992e20efdf043ac3c2d989025d48d648821de))

### Security
- Changed `Validation\Rules\Unique.php` ([da4d4a4](https://github.com/laravel/framework/commit/da4d4a468eee174bd619b4a04aab57e419d10ff4)). You can read more [here](https://blog.laravel.com/unique-rule-sql-injection-warning)


## [v5.8.4 (2019-03-12)](https://github.com/laravel/framework/compare/v5.8.3...v5.8.4)

### Added
- Added `Illuminate\Support\Collection::join()` method ([#27723](https://github.com/laravel/framework/pull/27723))
- Added `Illuminate\Foundation\Http\Kernel::getRouteMiddleware()` method ([#27852](https://github.com/laravel/framework/pull/27852))
- Added danish specific transliteration to `Str` class ([#27857](https://github.com/laravel/framework/pull/27857))

### Fixed
- Fixed JSON boolean queries ([#27847](https://github.com/laravel/framework/pull/27847))


## [v5.8.3 (2019-03-05)](https://github.com/laravel/framework/compare/v5.8.2...v5.8.3)

### Added
- Added `Collection::countBy` ([#27770](https://github.com/laravel/framework/pull/27770))
- Added protected `EloquentUserProvider::newModelQuery()` ([#27734](https://github.com/laravel/framework/pull/27734), [9bb7685](https://github.com/laravel/framework/commit/9bb76853403fcb071b9454f1dc0369a8b42c3257))
- Added protected `StartSession::saveSession()` method ([#27771](https://github.com/laravel/framework/pull/27771), [76c7126](https://github.com/laravel/framework/commit/76c7126641e781fa30d819834f07149dda4e01e6))
- Allow `belongsToMany` to take `Model/Pivot` class name as a second parameter ([#27774](https://github.com/laravel/framework/pull/27774))

### Fixed
- Fixed environment variable parsing ([#27706](https://github.com/laravel/framework/pull/27706))
- Fixed guessed policy names when using `Gate::forUser` ([#27708](https://github.com/laravel/framework/pull/27708))
- Fixed `via` as `string` in the `Notification` ([#27710](https://github.com/laravel/framework/pull/27710))
- Fixed `StartSession` middleware ([499e4fe](https://github.com/laravel/framework/commit/499e4fefefc4f8c0fe6377297b575054ec1d476f))
- Fixed `stack` channel's bug related to the `level` ([#27726](https://github.com/laravel/framework/pull/27726), [bc884bb](https://github.com/laravel/framework/commit/bc884bb30e3dc12545ab63cea1f5a74b33dab59c))
- Fixed `email` validation for not string values ([#27735](https://github.com/laravel/framework/pull/27735))

### Changed
- Check if `MessageBag` is empty before checking keys exist in the `MessageBag` ([#27719](https://github.com/laravel/framework/pull/27719))


## [v5.8.2 (2019-02-27)](https://github.com/laravel/framework/compare/v5.8.1...v5.8.2)

### Fixed
- Fixed quoted environment variable parsing ([#27691](https://github.com/laravel/framework/pull/27691))


## [v5.8.1 (2019-02-27)](https://github.com/laravel/framework/compare/v5.8.0...v5.8.1)

### Added
- Added `Illuminate\View\FileViewFinder::setPaths()` ([#27678](https://github.com/laravel/framework/pull/27678))

### Changed
- Return fake objects from facades ([#27680](https://github.com/laravel/framework/pull/27680))

### Reverted
- reverted changes related to the `Facade` ([63d87d7](https://github.com/laravel/framework/commit/63d87d78e08cc502947f07ebbfa4993955339c5a))


## [v5.8.0 (2019-02-26)](https://github.com/laravel/framework/compare/5.7...v5.8.0)

Check the upgrade guide in the [Official Laravel Documentation](https://laravel.com/docs/5.8/upgrade).
