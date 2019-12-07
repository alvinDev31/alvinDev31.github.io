# NPM

Node package management. There are several tools, e.g. npm, yarn, cnpm and pnpm.

---

## Package

A package is:

a) a folder containing a program described by a package.json file

b) a gzipped tarball containing (a)

c) a url that resolves to (b)

d) a <name>@<version> that is published on the registry (see npm-registry) with (c)

e) a <name>@<tag> (see npm-dist-tag) that points to (d)

f) a <name> that has a “latest” tag satisfying (e)

g) a <git remote url> that resolves to (a)

Reference: https://docs.npmjs.com/cli/install


## Q&A

### How multi-projects use same dependencies?

When using npm or Yarn for example, if you have 100 projects using the same version of lodash, you will have 100 copies of lodash on disk. With pnpm, lodash will be saved in a single place on the disk and a hard link will put it into the node_modules where it should be installed.

Reference: https://pnpm.js.org/en/motivation


### What kind of package should be install globally?

* Install it locally if you’re going to require() it.

* Install it globally if you’re going to run it on the command line.

Reference: https://docs.npmjs.com/files/folders

### I there any way to avoid duplicated packages cross projects?

So far found solution is pnpm.

## Issues

### when runing the project created with "vue create my_proj -m pnpm", "Error: getaddrinfo ENOTFOUND" is thrown.

SOLUTION: use bash instead of csh, the error gose away.
