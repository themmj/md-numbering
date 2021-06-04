# md-numbering

A small bash script to prefix level >= n headings with appropriate numbering.  
The following readme was numbered with this tool.

# Table of contents

- [1 Setup](#1-setup)
- [2 Usage](#2-usage)
- [3 Example](#3-example)
  * [3.1 This readme](#31-this-readme)
  * [3.2 With other starting levels](#32-with-other-starting-levels)
    + [3.2.1 Level 1](#321-level-1)
    + [3.2.2 Level 3](#322-level-3)

## Setup

The only requirement is a fairly modern installation of bash running and a markdown file.

## Usage

To run the script on a markdown file:

```bash
./numbering <srcFile> <destFile> <startingLevel>
```

parameter      |required|default|meaning
---------------|--------|-------|-------
`srcFile`      |required|-      |markdown file without numbered headings to use
`destFile`     |required|-      |file the new content should be written to (will overwrite)
`startingLevel`|optional|2      |level on which numbering will start, default excludes # header

## Example

### This readme

The command used to generate this readme assuming the raw file [README-base.md](./README-base.md) is used:

```bash
./numbering README-base.md README.md 2
```

### With other starting levels

The following shows the resulting headers for different starting levels.

#### Level 1

```markdown
    # 1 md-numbering
    # 2 Table of contents
    ## 2.1 Setup
    ## 2.2 Usage
    ## 2.3 Example
    ### 2.3.1 This readme
    ### 2.3.2 With other starting levels
    #### 2.3.2.1 Level 1
    #### 2.3.2.2 Level 3

```

#### Level 3

```markdown
    # md-numbering
    # Table of contents
    ## Setup
    ## Usage
    ## Example
    ### 1 This readme
    ### 2 With other starting levels
    #### 2.1 Level 1
    #### 2.2 Level 3
```

