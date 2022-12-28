# CDX Package SPEC

A CDX Package is used to finish certain function in the Chip-Design-Execution process.

## Folder Structure

All the files (at least main files) must be in one folder as a package which will be used by the application.

package.toml or package.json is the file to tell the meta information of the cdx package.

## Package Meta File

Plural keys are arrays, simple array or associated array.

Singular keys are string.

### name

### description

### version

### entry

### keywords

keyword could have "type", the format is "&lt;type&gt;:&lt;keyword&gt;". And keyword could be used along with the tagging system. Each tag is an object and could have its own functions and properties.

### engines

### maintainers

### scripts

### dependencies


## Use the Package

The application should based on the `engines` to pick the actions from `scripts`.

Or there is a key called entry, you can follow the package rule to load the file accordingly.


