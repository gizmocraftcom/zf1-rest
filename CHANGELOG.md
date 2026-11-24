# Changelog

## 2.0.0

Fork of `diablomedia/zendframework1-rest`, published as `gizmocraft/zendframework1-rest`.

### Breaking changes

- Requires PHP `>=8.5`. Tested on PHP 8.5 and 8.6.
- Package renamed from `diablomedia/zendframework1-rest` to `gizmocraft/zendframework1-rest`. It now requires `gizmocraft/zendframework1-exception`, `-server`, `-xml`, `-controller`, `-http`, `-service` and `-uri` (each `^2.0.0`) and `-config` (`^3.0.0`).

### Other changes

- `Zend_Rest_Server` no longer passes `null` to `DOMDocument::createTextNode()` when a returned struct contains a `null` value (deprecated since PHP 8.1); the element is written empty as before. No signature changes.
- Dev dependencies upgraded (PHPUnit 13, PHPStan 2.3, php-cs-fixer 3.95, GrumPHP 2.27). Dropped `composer-require-checker`, which has no release for PHP 8.6.
- Tests migrated to PHPUnit 13 attributes. `Zend_Rest_ServerTest` removes the exception handler that `Zend_Rest_Server` registers in its constructor. Added a regression test for the `null` struct value.
- CI runs PHP 8.5 and 8.6.
