# Mini ARC

A `gh` extension to start up a Actions Runner Controller deployment in Minikube via Codespaces.

Built for those that need or want to deploy Actions Runner Controller as fast as possible for testing or experimental purposes.

This extension will:
- Create you a new repository.
- Create a new Codespace.
- Install Actions Runner Controller in Minikube on said Codespace.
- Create a flexible number of runner scale set deployments based on input options.
  - Each runner scale set is installed to the new repository. 

## Prerequisites

- Ensure you have the [GitHub CLI](https://github.com/cli/cli) installed. 
- Ensure your GitHub CLI token has the `repo`, `workflow`, and `codespace` scopes (run `gh auth status` to check).
- If not, add the scopes: 
    ```bash
    gh auth refresh --scopes repo,workflow,codespace
    ```
- Install the extension:
    ```bash
    gh extension install bagtoad/gh-mini-arc
    ```

## Usage

Create a new repository with an Actions Runner Controller deployment in a Codespace.
```bash
gh mini-arc
```
Create a new repository with an Actions Runner Controller deployment in a Codespace with 5 runner scale sets of different names.
```bash
gh mini-arc -s "scale-set-1" -s "scale-set-2" -s "scale-set-3" -s "scale-set-4" -s "scale-set-5"
```

