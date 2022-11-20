# Setting up the Skyline Development Environment

## Requirements
   - [rustup](https://www.rust-lang.org/tools/install) (Windows/MacOS/Linux)
   - [git](https://git-scm.com/downloads) (Windows/MacOS/Linux)
   - cargo-skyline

## Installation
1. Install [git](https://git-scm.com/downloads) (Follow the on-screen installer)
2. Install [rustup](https://www.rust-lang.org/tools/install) (Follow the instructions on the page)
3. After the installation is complete, open up the command prompt
4. Run the following command: `cargo install cargo-skyline` and wait for it to install
5. Next up, run `cargo skyline set-ip <Switch IP>`
6. Once that's done, run this command: `cargo skyline update-std` and click `Y` (this installation process will take a while)
7. When it's finally over, you have your development environment set up!

## Creating and building a new skyline project
1. Run `cargo skyline new <project_name>`
2. Run `cd <project_name>`
3. Run `cargo skyline build --release`
4. Your built plugin file will be in `./<project_name>/target/aarch64-skyline-switch/release/lib<project_name>.nro`
6. Now that the main part is done, open up command prompt in a directory of your choice (I recommend making a new one for your projects)
    ![Opening up cmd in a folder (Thanks to TNN for the example)](../img/General/cmd_in_folder.gif)

## Installing your skyline plugin automatically
1. Make sure you have sys-ftpd-light set up (`Prerequisites -> Modding Setup`)
2. Run `cargo skyline run`

## Installing your skyline plugin manually
1. Copy `./<project_name>/target/aarch64-skyline-switch/release/lib<project_name>.nro` to `sd:/atmosphere/contents/01006A800016E000/romfs/skyline/plugins` (Make sure you have the skyline exefs set up!)