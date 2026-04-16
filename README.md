# icon-replacement-tabler
Replace depreceated icons (Streamline, FontAwesome) with Tabler icons

This repository contains information and AI directions for the replacement of depreceated icon libraries.  
The depreceated icon libraries are
- [Streamline Icons](https://www.streamlinehq.com/)
- [FontAwesome icons](https://fontawesome.com/v6/icons/)

The icons of those libraries should be replaced with the new Tabler icons
- [Tabler icons](https://tabler.io/icons)

## Resources
- AxonIvy Market HTML dialog example with a showcase of all icons. See project `html-dialog`: https://github.com/axonivy/demo-projects
- Depreceation page: https://dev.axonivy.com/features/deprecation
- Community post: TODO

## How to use

`plan_template.md` describes an execution plan which can be handed over to an AI agent to execute the replacment. Due to the variability in project structures, there is no hardcoded conversion file.

1. Copy `all-old-icons.csv` to your project root - Contains a static list of all potential old icon CSS classes. **No need to modify**.
2. Copy `mapping_si.csv` and `mapping_fa.csv` to your project root - Contains a compiled list of known mappings to matching Tabler icons. **If any mapping is missing, add it after copy**.
    - There is also a mapping file for PrimeIcons `mapping-pi.csv`, you do not have to use this file.
3. Copy `plan_template.md` to your project root as `plan.md`
4. Adjust `plan.md` section ROOT_FOLDERS in section "Resoucres". Specify which folders in your project should be considered for replacement.
5. Adjust `plan.md` section EXCLUDED_FOLDERS in section "Resoucres". Specify which folders should be excluded for replacement. Exapmle: "target/".
6. Hand over to the AI agent for execution.

## Caveats
The concrete outcome depends on the AI agents implementation. However, it is very likely that not all occurences will be found and replaced perfectly, since the compilation of the CSS icon classes can be arbitrarily nested within source files and can become complex.  
Therefore, most liekyl some manual intervention will be needed to fully replace all and every occrence in your project.
