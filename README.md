# Update sfdx-project.json dependencies from installed packages

Oppdaterer pakkeversjoner i sfdx-project.json basert på hva som er installert i `target-org`.  
MERK: Denne Git Hub actionen hverken legger til eller fjerner pakker, den bare oppdaterer versjonen på pakker i lista.

## Usage

<!-- Start usage -->
```yaml
- name: Update sfdx-project.json dependencies
    id: update-dependencies
    uses: navikt/sf-gha-update-sfdx-project-dependencies@main
    with:
        # Alias or username of the target org to fetch installed packages from
        # Required: true
        # Default: ''
        target-org: ''
        
        # Path to sfdx-project.json
        # Required: false
        # Default: 'sfdx-project.json'
        sfdx-project-path: ''

- name: Next action
    run: |
        echo "sfdx-project.json updated: $SFDX_PROJECT_UPDATED"
    env:
        SFDX_PROJECT_UPDATED: ${{ steps.update-dependencies.outputs.updated == 'true' }}
```
<!-- end usage -->

## Henvendelser

Spørsmål knyttet til koden eller prosjektet kan stilles som issues her på GitHub.

## For NAV-ansatte

Interne henvendelser kan sendes via Slack i kanalen #platforce.
