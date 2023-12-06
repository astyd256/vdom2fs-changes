# VDOM Application Unpacker Script

This script is designed to work with VDOM applications, specifically for unpacking one app compiled from several others to prepare it for commit changes back into the repository. 

## Features

- Unpacks VDOM applications for easy access to the source files.
- Skips database files if the `--skip_db` flag is set to avoid unnecessary processing.
- Supports inclusion and exclusion `regex` patterns for file processing.
- Reconstructs the directories structure of the original source repositories.
- Creates a new directory for files that do not match the existing index.
- Optimized to look only fro files from which project was compiled

## Requirements

- Python 2.7
- VDOM application source files
- `vdom2fs.conf` configuration file

## Usage

To use the script just launch the command or add optional arguments specific to your use-case

```
python unpack_script.py
```
Replace the paths and flags with the appropriate values for your setup.

## Arguments

The script supports plenty of arguments for you comfort working with VDOM apps:

* `--config_path`: Path to the configuration file (default: vdom2fs.conf).
* `--indexes_path`: Path to the indexes file (default: .tmp/index.json).
* `--temp_dir`: Path to the temporary directory where changes  are made (default: .tmp/changes).
* `--unpack_dir`: Path to the directory containing the VDOM application to unpack (default: .tmp/unpack).
* `--parent_dir`: Path to the parent directory of the project (default: current working directory name).
* `--skip_db`: Flag to skip processing database files (default: True).
* `--no_index`: Flag to skip indexing repositories (default: False).

## Configuration File
The vdom2fs.conf file should contain the settings for the aliases, directories, and patterns for include/exclude criteria.

## Output
The script outputs the unpacked files into the specified temporary directory. It also creates a new directory for files that are new or do not match the existing index, which can then be reviewed for changes.
