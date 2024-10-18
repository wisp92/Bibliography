# Conventional Commits

The following guidelines advise on the format of commit messages.

## General Structure

```none
<type>[scope]: <description>

[body]

[footer(s)]
```

The header must start with a lowercase character and must not end with `.`.


### Structure of a Revert Commit

```none
revert: <header>

This reverts commit <hash>.
```


## Commit Types

1. `build`: changes that affect the build system or external dependencies
2. `ci`: changes to the configuration files and scripts
3. `docs`: changes to the documentation only
4. `fix`: a bug fix
5. `feat`: a new feature.
6. `perf`: a code change that improves performance
7. `refactor`: a code change that neither fixes a bug nor adds a feature
8. `style`: changes that do not affect the output of the code, e.g., formatting
9. `test`: adds a test or makes corrections to existing ones

A scope may be provided after a type. A scope must consist of a noun describing a section of the codebase surrounded by parenthesis, e.g., `fix(parser)`.


## Available Footers

1. `BREAKING CHANGE: <description>`: a commit that has a footer `BREAKING CHANGE`, or appends a `!` after the type, introduces a breaking API change.
2. `<token>: <value>`: any other token-value pair, e.g., `Reviewed-by: Z`, `Ref(s): #123`. A footer's token must use `-` in place of whitespace characters.


## Instructions to Enable Commit-Lint

The following commands must be executed in the Git Bash.

```bash
npm install --save-dev @commitlint/{cli,config-conventional}

echo "export default { extends: ['@commitlint/config-conventional'] };" > commitlint.config.mjs

npm install --save-dev husky
npx husky init
rm .husky/pre-commit

echo "npx --no -- commitlint --edit \$1" > .husky/commit-msg
```