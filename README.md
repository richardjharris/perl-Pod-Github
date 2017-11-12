```
Pod::Github - convert POD to Github markdown
```

## Synopsis

```perl
my $parser = Pod::Github->new(%opts);
$parser->output_fh(\*STDOUT);
$parser->parse_file(\*ARGV);
```

## Description

Subclass of `Pod::Simple` that accepts POD and outputs Github Flavored
Markdown (GFM). Optionally inlines or removes headings and/or prettifies
the markdown to look better as a GitHub readme.

## Methods

- new (%opts)

    Accepts the arguments in the same form as the binary `bin/pod2github`
    (i.e. with dashes, not underscores). `include`, `exclude` and `inline`
    should be arrayrefs of section names rather than a CSV string.

- output\_fh (fh)

    Set the filehandle for Markdown output.

- output\_string (stringref)

    Sets the string that $parser's output will be sent to, instead of a
    filehandle.

- parse\_file (fh)

    Read POD from the given filehandle and output Markdown to `output_fh`.

- parse\_string\_document (string)

    Works like `parse_file` except it reads the POD from a string already
    in memory.

- parse\_lines (list)

    Works like `parse_file` except it reads the POD from a list of strings,
    each containing exactly one line of content.
