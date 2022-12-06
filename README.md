# janet-usages-as-tests

Generate and run tests from usage examples

## Background

`janet-usages-as-tests` is an evolution of
[usages-as-tests](https://github.com/sogaiu/usages-as-tests).  The
basic idea is the same once things are setup.

## Sample Repositories

The following repositories use `janet-usages-as-tests`:

* [jandent](https://github.com/sogaiu/jandent)
* [janet-bits](https://github.com/sogaiu/janet-bits)
* [janet-editor-elf](https://github.com/sogaiu/janet-editor-elf)
* [janet-peg](https://github.com/sogaiu/janet-peg)
* [janet-xmlish](https://github.com/sogaiu/janet-xmlish)
* [janet-zipper](https://github.com/sogaiu/janet-zipper)
* [jaylib-wasm-demo](https://github.com/sogaiu/jaylib-wasm-demo)
* [margaret](https://github.com/sogaiu/margaret)

## Running Tests

### Repositories Using janet-usages-as-tests

Invoke `jpm test` as usual.

### This Repository

Invoking `jpm test` will not work for this repository as it is not set
up to be tested in that manner.

Instead, to test the code in this repository, invoke:
```
janet test.janet
```

## Setup and Configuration

### Basic

1. Clone or copy this repository as a subdirectory of a target
   project.
2. Copy or move the included `test.janet` file into the `test`
   directory of the target project.
3. Edit `test.janet` to specify files and/or directories that are the
   target of usages to be treated as tests.

Note, most sample repositories listed above (except for
`jaylib-wasm-demo`) used this method of setup.

### Git Submodule

1. In place of step 1 above, add this repository as a submodule of a
   target project.  See
   [jaylib-wasm-demo](https://github.com/sogaiu/jaylib-wasm-demo) for
   an example that does this.
2. Copy or move the included `test.janet` file into the `test`
   directory of the target project.
3. Edit `test.janet` to specify files and/or directories that are the
   target of usages to be treated as tests.

## Writing Tests

Within `comment` blocks, put expressions / forms to be tested along
with expected values (or expressions):

```janet
(comment

  (- 1 1)
  # =>
  0

  )
```

Here `(- 1 1)` is the expression to be tested and `0` is the
corresponding expected value.  The instance of `# =>` indicates
the presence of a test / usage.

See [Usage / Test Writing Tips](./doc/tips.md) for more details.

## Acknowledgments

* andrewchambers - suggestion and explanation
* bakpakin - janet, jpm, helper.janet, path.janet, peg for janet, etc.
* pepe - discussion, One-Shot Power Util Solver ™ motivation, and naming
* pyrmont - discussion and exploration
* rduplain - bringing to light customization of `jpm test`
* Saikyun - discussion and testing
* srnb@gitlab - suggestion

