# Pipeline uploaded

This is a tool for managing remote configs, possible from a ci or other file backed source. 
See `/examples` in repo root for expected file formats.

This tool will:

- Load all pipeline files from the directory specified by `-d` (any `.river` or `.alloy` files)
- Discover matchers from comments in those files (from comments, see below)
- Upload pipelines to a remote configuration server
- Delete any remote pipelines not found locally (if `-purge` is set).

## Discovering matchers from pipeline `.alloy` files:

This tool will look for a comment in each file of the form:

```// matchers: key=val key2=val```

It expects to find at most one such comment. The matchers will be associated with the uploaded pipeline.