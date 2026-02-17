# renice

## Purpose
Changes the priority (nice value) of a running process.

---

## Usage

`renice <nice_value> -p <pid>`

## Notes
- Lower nice value = higher priority
- Higher nice value = lower priority
- Regular users can only lower priority
- Root can raise or lower priority

