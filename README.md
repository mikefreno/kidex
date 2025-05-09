# Kidex

A fork from [Kirottu](https://github.com/Kirottu/kidex) with the pr(#4 - Deserialize path strings from config directly into PathBuf
) by [Lxtharia](https://github.com/Lxtharia) and to serve as a base for any personal changes

A simple file indexing service

### Manual installation
From project root

```sh
cargo install --path ./kidex
cargo install --path ./kidex-client
```

## Configuration

Kidex only has a single config file to be placed in `~/.config/kidex.ron`, which uses the following structure:
```ron
Config(
  ignored: [], // A list of patterns to be ignored in all directories
  directories: [
    WatchDir(
      path: "~/Documents", // The root folder to be indexed
      recurse: true, // Recursively index and watch all subfolders
      ignored: [], // Ignore patterns specifically for this directory
    ),
  ],
)
```

## Usage

To start the service, simply run `kidex` and make sure it runs in the background. To get data from the service,
the provided `kidex-client` binary can be used to get JSON output of the index. Alternatively a tool like [Anyrun](https://github.com/Kirottu/anyrun)
(with the kidex plugin) can be used to search for files using kidex.
