<h1 align="center">
	PCB GUIDELINES
	<br>
</h1>

<h4 align="center">Guidelines for the development of SpaceLab hardware projects.</h4>

<p align="center">
    <a href="https://github.com/spacelab-ufsc/altium-library">
		<img src="https://img.shields.io/badge/pcb-libraries-green?style=for-the-badge">
	</a>
    <a href="https://github.com/spacelab-ufsc/pcb-standard/tree/master/pcb_projects">
		<img src="https://img.shields.io/badge/pcb-projects-blue?style=for-the-badge">
	</a>
	<a href="https://github.com/spacelab-ufsc/pcb-standard/tree/master/pcb_references">
		<img src="https://img.shields.io/badge/pcb-references-9cf?style=for-the-badge">
	</a>
	<a href="https://github.com/spacelab-ufsc/pcb-standard/tree/master/pcb_templates">
		<img src="https://img.shields.io/badge/pcb-templates-yellow?style=for-the-badge">
	</a>
	<a href="https://github.com/spacelab-ufsc/pcb-standard/tree/master/pcb_standards">
		<img src="https://img.shields.io/badge/pcb-standards-lightgray?style=for-the-badge">
	</a>
</p>

<p align="center">
  	<a href="#overview">Overview</a> •
  	<a href="#templates">Templates</a> •
  	<a href="#design-rules">Design Rules</a> •
  	<a href="#output-files">Output files</a> •
  	<a href="#project-repositories">Project Repositories</a> •
  	<a href="#documentation">Documentation</a>
</p>


## Overview
This guideline aims only to give general and basic directions for the PCB layout for the SpaceLab and does not present complete and extensive standards. 

## Templates
- Use the schematics and layout template provided in: Altium and KiCad [templates](https://github.com/spacelab-ufsc/pcb-standard/tree/master/pcb_projects).
- The first schematic sheet must contain: simplified hardware architecture (block diagram), power architecture, version control indication, project name, contributors, and licensing.
- The other schematic sheets must contain: a header containing essential info, the circuits separated by category/functionality, simple description or relevant commentaries in non-obvious design decisions/signals/architecture/integration.
- All the elements must be embedded into the project or available in the folder (i.e., they do not need external linking to work properly).

## Design Rules

#### Libraries
- Create a dedicated file for schematic and layout libraries in each project using the Altium and KiCad [libraries](https://github.com/spacelab-ufsc/pcb-standard/tree/master/pcb_libraries) as source or import from a reliable website (manufacturer provider, distributor, [Kleber’s repository](blank), [3D Content Central](https://www.3dcontentcentral.com/), [Ultra Librarian](https://www.ultralibrarian.com/), [SnapEDA](https://www.snapeda.com/) or [GrabCAD](https://grabcad.com/)).
- Create a dedicated library for the critical 3D rendering of the components used for further measurements if necessary.
- Remember to review the footprints after importing (electrical and mechanical layers, 3D bodies, essential parameters, adequate schematic symbols, footprints, linking of the components, and overall compliance with the laboratory’s standard).
- Do not use obsolete components for new designs and update them in older projects if possible (use the “search component” feature in Altium if available).
For space segment projects, try to use automotive grade components (if not possible, at least industrial grade).

#### Schematics
- In the schematic circuits are mandatory: values, designators, partnumber in case of ICs, subsystem names, readable connections, and meanifull signal names.
- Remember to add mechanical entities (screws, fiducials, holes, attachments, others) to enhance the linking between schematics and layout.
- Remember to  be compliant with the checklist provided in: [Kleber’s checklist](https://github.com/spacelab-ufsc/pcb-standard/blob/master/pcb_resources/pcb_design_checklist.xlsx)
- Remember to perform a tedious and comprehensive review after doing all the previous items and finishing the circuits.
- If it is beneficial, make variants for fitted and not fitted components (test models, flight models or any other variant).
- If it is beneficial, use harness signals to create block diagrams and multi signal interfaces within altium features (it helps to perform design checks).

#### Layout
- Remember to check the linking with the schematics and keep the design rules updated.
- (Altium feature): If beneficial, import the PCB design rules already made for some manufactures (JLCPCB 2 layer design rules file link here), these rules need to be double checked always before finishing the DRC.
- In the layout are mandatory: drills counter, stack-up description, header including essential information (version, contributors, others), manufacturing details and observations (pads finishing, PCB class, impedance control, materials, dimensions, vias finishing), and overall board dimensions.
- Remember to check if the design requires special measures before starting for impedance control, length matching, noise reduction (crosstalk and interference), power and ground planes, return paths, finishing, materials, and other relevant parameters.
- Create signal groups for specific rules instead of generalizing rules (expanding intervals) to fit all the specifications.
- Add SpaceLab and open hardware logos (if applicable), the board/module name, and version to the silkscreen.
- Add good ground connections across the board and create several inter-ground connections in different layers through vias.
- Remember that placement is very important for easing the routing and connection process, besides the overall board organization (components location based on purpose, noise generation and susceptibility, layers requirements, others) and manufacturability.
- It is highly recommended to do routing in preferential directions to mitigate crosstalk, improve organization and ease the routing itself.
- Avoid ground loops in the design generated when multiple ground access points in different locations are provided for the same component, circuit, or the entire board (it is recommended uninterrupted ground polygons/planes).
- Remember to give proper and secure space for mechanical attachments and elements within the PCB and with other modules in the system.
- Remember to use the [design resources](https://github.com/spacelab-ufsc/pcb-standard/tree/master/pcb_resources) for accessing the theoretical references, tips, and rules of thumb.
- Remember to check the Cezar’s thesis and book for space application PCBs, avaliable in: [10.1109/TLA.2020.9085278](https://ieeexplore.ieee.org/document/9085278), Printed Circuit Board Design Methodology for Embedded Systems Targeting Space Applications.

#### Rules of thumb
- Under definition! (Things that we adopted with no proper justification, but must be done)

## Output files
- The output files must contain: Gerbers (all relevant layers), NC Drills, Pick and Place, complete schematic sheets (including the electrical layout layers), draftmans (top, bottom, and sides), parasolid/step, bill of materials, and 3D render images without background.
- Altium: Use the [Kleber’s output job file](https://github.com/spacelab-ufsc/pcb-standard/tree/master/pcb_templates/output_job_file.outjob) to export all the fabrication and assembly files.

## Project Repositories

#### Organization
- The project repository in GitHub is going to be provided with 3 main folders: hardware, firmware, and doc. (It could be expanded depending on the project, mechanical, fpga, scripts, libs, and others).
- Inside the hardware folder, the hardware project is going to be added following this directory structure: (use lowercase words separated by underscores)

```
	hardware/images/   (include editables and .png)
		../hardware_architecture
		../power_architecture
		../interfaces_pinout
		../[logos_files]
		../[others_files]
	hardware/libraries/
		../schematics_library
		../footprints_library
		../3d_bodies_library (mandatory only for critical or bigger components)
	hardware/outputs/
		../assembly_step/
		../assembly_odb/  (optional)
		../assembly_pick_place/
		../board_drc/
		../board_gerbers/
		../board_ncdrills/
		../board_prints/   (optional)
		../board_test_points/  (optional)
		../bom/
		../pdf/
		../[camtastic]
		../[output_job_file]  (mandatory only for altium)
	hardware/fabrication/
		../[gerbers+ncdrills].zip
		../[pick_place].txt   (file format generally accepted)
		../[readme].txt    (include observations for every fabrication aspect)
	hardware/sources/
		../[all_sources]  (all schematic sheets, pcb layout and auxiliary files)
	hardware/[project_files]   (all strictly necessary project files)
	hardware/[git_related_files]  (readme.md and .gitignore)
```

#### Control
- The repository in GitHub has 2 main branches: master and dev. For hardware only projects keep this structure and use the dev branch, always doing a pull before and push after committing (for this, remember to never leave uncommitted changes to avoid conflicts with the others contributions/commits). In case of more complex projects create branches, such as: dev_hardware, dev_firmware, dev_documentation, others. For merging the repository into the master, never do it directly, you will not have permission. The correct workflow is periodically or after a meanifull series of commits in the dev_hardware branch, do a pull request for merging your branch into dev, then someone will approve it and later merge dev into master.
- Do clean commits (never add unnecessary, temporary, log files, others).There is a .gitignore in the template folder to ignore them during the commits, use it!! Altium tips: do not commit History and __previews folders.
- Since there is no direct tracking of changes of the hardware files, try to commit relevant changes(not too frequently exposing each little detail, but exposing major changes), such as: adding the subsystem Y placement, updating component X routing, removing unnecessary labels.
- The commit names must be compliant with the following standard: “key_folder: secundary_folder: scope: subsystem (if applicable): Adding/Removing/Updating… content… #issue_number (if applicable). close #issue_number (if applicable)“. Example: “hardware: sources: schematics: buffers: Adding the preliminary IC and capacitors placement #45 #57. close #56”.
- It is recommended to keep track of major changes and objectives through the use of issues.

## Documentation
- Documentation is mandatory and important to be written during the development process, when the implementation details and decisions are still remembered. Use the [documentation spacelab template](https://github.com/spacelab-ufsc/doc-template) that should be used within the documentation folder.
- The documentation topics and required depth change dramatically over different projects, then for properly documenting the new project, use the previous examples to guide the process. The [obdh2 doc](https://github.com/spacelab-ufsc/obdh2/tree/master/doc/build) is a good first example for module/payload projects.