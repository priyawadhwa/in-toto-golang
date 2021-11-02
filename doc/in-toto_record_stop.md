## in-toto record stop

Records and adds the paths and hashes of the passed products to the link metadata file and updates the signature.

### Synopsis

Expects preliminary link file ‘.<name>.<keyid prefix>.link-unfinished’ in the CWD,
signed by the passed functionary’s key. If found, it records
and adds the paths and hashes of the passed products to the
link metadata file, updates the signature and renames the
file to ‘<name>.<keyid prefix>.link’.

```
in-toto record stop [flags]
```

### Options

```
  -h, --help                   help for stop
  -p, --products stringArray   Paths to files or directories, whose paths and hashes
                               are stored in the resulting link metadata after the
                               command is executed. Symlinks are followed.
```

### Options inherited from parent commands

```
  -c, --cert string                 Path to a PEM formatted certificate that corresponds
                                    with the provided key.
  -e, --exclude stringArray         Path patterns to match paths that should not be recorded as 
                                    ‘materials’ or ‘products’. Passed patterns override patterns defined
                                    in environment variables or config files. See Config docs for details.
  -k, --key string                  Path to a private key file to sign the resulting link metadata.
                                    The keyid prefix is used as an infix for the link metadata filename,
                                    i.e. ‘<name>.<keyid prefix>.link’. See ‘–key-type’ for available
                                    formats. Passing one of ‘–key’ or ‘–gpg’ is required.
  -l, --lstrip-paths stringArray    Path prefixes used to left-strip artifact paths before storing
                                    them to the resulting link metadata. If multiple prefixes
                                    are specified, only a single prefix can match the path of
                                    any artifact and that is then left-stripped. All prefixes
                                    are checked to ensure none of them are a left substring
                                    of another.
  -d, --metadata-directory string   Directory to store link metadata (default "./")
  -n, --name string                 Name for the resulting link metadata file.
                                    It is also used to associate the link with a step defined
                                    in an in-toto layout.
```

### SEE ALSO

* [in-toto record](in-toto_record.md)	 - Creates a signed link metadata file in two steps, in order to provide
              evidence for supply chain steps that cannot be carried out by a single command
