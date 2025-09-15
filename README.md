# **Fossil CLI by Fossil Logic**

**Fossil CLI** is a lightweight, portable command-line interface (CLI) framework written in pure C with zero external dependencies. It enables developers to quickly build structured, user-friendly CLI applications with minimal boilerplate. Fossil CLI emphasizes simplicity, predictability, and portability, making it a perfect choice for utilities, automation tools, and cross-platform command-line programs.  

### Key Features

- **Cross-Platform Support**  
  Consistent behavior across Windows, macOS, Linux, and embedded shells.  

- **Zero External Dependencies**  
  Implemented entirely in portable C for easy integration and maintenance.  

- **Command & Option Parsing**  
  Provides robust argument parsing, subcommands, and flags with minimal code.  

- **Lightweight and Efficient**  
  Small and fast, enabling quick startup and low resource usage.  

- **Self-Contained & Auditable**  
  Clean, well-documented implementation for easy review and debugging.  

- **Modular Design**  
  Flexible enough to support everything from simple utilities to full-featured CLI applications.  

## ***Prerequisites***

To get started, ensure you have the following installed:

- **Meson Build System**: If you don’t have Meson `1.8.0` or newer installed, follow the installation instructions on the official [Meson website](https://mesonbuild.com/Getting-meson.html).

### Adding Dependency

#### Adding via Meson Git Wrap

To add a git-wrap, place a `.wrap` file in `subprojects` with the Git repo URL and revision, then use `dependency('fossil-cli')` in `meson.build` so Meson can fetch and build it automatically.

#### Integrate the Dependency:

Add the `fossil-cli.wrap` file in your `subprojects` directory and include the following content:

```ini
[wrap-git]
url = https://github.com/fossillogic/fossil-cli.git
revision = v0.1.0

[provide]
dependency_names = fossil-cli
```

**Note**: For the best experience, always use the latest releases. Visit the [releases](https://github.com/fossillogic/fossil-cli/releases) page for the latest versions.

## Build Configuration Options

Customize your build with the following Meson options:
	•	Enable Tests
To run the built-in test suite, configure Meson with:

```sh
meson setup builddir -Dwith_test=enabled
```

### Tests Double as Samples

The project is designed so that **test cases serve two purposes**:

- ✅ **Unit Tests** – validate the framework’s correctness.  
- 📖 **Usage Samples** – demonstrate how to use these libraries through test cases.  

This approach keeps the codebase compact and avoids redundant “hello world” style examples.  
Instead, the same code that proves correctness also teaches usage.  

This mirrors the **Meson build system** itself, which tests its own functionality by using Meson to test Meson.  
In the same way, Fossil Logic validates itself by demonstrating real-world usage in its own tests via Fossil Test.  

```bash
meson test -C builddir -v
```

Running the test suite gives you both verification and practical examples you can learn from.

## Contributing and Support

For those interested in contributing, reporting issues, or seeking support, please open an issue on the project repository or visit the [Fossil Logic Docs](https://fossillogic.com/docs) for more information. Your feedback and contributions are always welcome.
