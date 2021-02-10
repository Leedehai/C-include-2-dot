# C-include-2-dot

It is continue of the [version](https://github.com/frabcus/cinclude2dot). The code itself is licensed under the GNU GPL v2 license. Feel free to use
the code as is, or modify it according to your needs. It requires a Perl 5 interpreter, which is installed on macOS and many Linux distributions by default.

## Usage:
- for help message:
	```
	./cinclude2dot -h
	```

- example usage: `--include` and `--src` are followed by comma-saparated header and source file paths. `--quotetype=quote` means only user headers (`#include "..."`) are counted.
	```
	./cinclude2dot.pl --include=MyProject/include,OtherInclude --src=MyProject/include,MyProject/src,OtherSrc --quotetype=quote > dependency.dot
	```
	>  In the example above, `MyProject/include` is also in the list of `--src` because a user header may include other user headers.

- You can feed the generated `.dot` file to GraphViz to create a dependency graph. There is also an online version of GraphViz [here](http://webgraphviz.com).

- In fact, your GCC compiler can output a dependency list, too - but it is not a `.dot` file that can be feed to GraphViz. The options are `-H`, `-M` (a tree), and `-MM` (same as `-M`, but only user headers are counted).

###### EOF
