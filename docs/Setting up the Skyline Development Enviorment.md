# Setting up the Skyline Development Enviorment

## Requirements
   - [Cargo](https://www.rust-lang.org/tools/install) (Windows/MacOS/Linux)
   - [git](https://git-scm.com/downloads) (Windows/MacOS/Linux)
   - cargo-skyline

## Installation
1. Install [git](https://git-scm.com/downloads) (Follow the on-screen installer)
2. Install [Cargo](https://www.rust-lang.org/tools/install) (Follow the instructions on the page)
3. After the installation is complete, run `cargo install cargo-skyline`
4. Once that's done, run `cargo skyline update-std`
5. Finally, run `cargo skyline set-ip <Switch IP>`
5. When it's finally over, you have your development enviorment set up!

## Creating and building a new skyline project
1. Run `cargo skyline new <project_name>`
2. Run `cd <project_name>`
3. Run `cargo skyline build --release`
4. Your built plugin file will be in `./<project_name>/target/aarch64-skyline-switch/release/lib<project_name>.nro`

## Installing your skyline plugin automatically
1. Run `cargo skyline run`

## Installing your skyline plugin manually
1. Copy `./<project_name>/target/aarch64-skyline-switch/release/lib<project_name>.nro` to `sd:/atmosphere/contents/01006A800016E000/romfs/skyline/plugins` (Make sure you have the skyline exefs set up!)