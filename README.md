# icon-replacement-tabler
Replace depreceated icons (Streamline, FontAwesome) with Tabler icons

This repository contains information and AI directions for the replacement of depreceated icon libraries.  
The depreceated icon libraries are
- [Streamline Icons](https://www.streamlinehq.com/)
- [FontAwesome icons](https://fontawesome.com/v6/icons/)

The icons of those libraries should be replaced with the new Tabler icons
- [Tabler icons](https://tabler.io/icons)

## Resources
- HTML dialog example with a showcase of all icons: https://nightly.demo.ivyteam.io/demo-app/1/faces/view/html-dialog-demos/icons.xhtml-
- Jira Epic: https://axon-ivy.atlassian.net/browse/XIVY-18409
- Confluence: https://axon-ivy.atlassian.net/wiki/spaces/XIVY/pages/458752001/Migrate+to+Tabler+icons

## How to use

`plan_template.md` describes an execution plan which can be handed over to an AI agent to execute the replacment. Due to the variability in project structures, there is no hardcoded conversion file.

1. Copy `all-old-icons.txt` to your project root - Contains a static list of all potential old icon CSS classes. **No need to modify**.
2. Compile `mapping.yaml`
    This mapping must be created by you to reflect the most up to date mapping from known old -> new icons.
    - Go to https://axon-ivy.atlassian.net/wiki/spaces/XIVY/pages/458752001/Migrate+to+Tabler+icons
    - Copy all mappings from the page and put them in a YAML file. The strucutre should look like this:
        ```yaml
        si si-add: ti ti-plus
        si si-add-circle: ti ti-circle-plus
        si si-add-small: ti ti-plus
        ```
3. Copy `mapping.yaml` to your project root
4. Copy `plan_template.md` to your project root as `plan.md`
5. Adjust `plan.md` section ROOT_FOLDERS in section "Resoucres". Specify which folders in your project should be considered for replacement
6. Adjust `plan.md` section EXCLUDED_FOLDERS in section "Resoucres". Specify which folders should be excluded for replacement. Exapmle: "target/".
7. Hand over to the AI agent for execution.

## Caveats
The concrete outcome depends on the AI agents implementation. However, it is very likely that not all occurences will be found and replaced perfectly, since the compilation of the CSS icon classes can be arbitrarily nested within source files and can become complex.  
Therefore, most liekyl some manual intervention will be needed to fully replace all and every occrence in your project.
