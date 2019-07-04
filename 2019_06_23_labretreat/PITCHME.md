---?color=black
@title[Title]

@snap[west headline text-white span-100]
3D Slicer: DBS Guide
<br>


@size[40%](<p>Lab Retreat 2019<br>June 22, 2019</p>)
@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](greydon.gilmore@gmail.com)
@snapend


---
@title[Contents]

@snap[north-west span-120]
## Contents
@snapend
<br><br>
@ol[list-bullets-concise](false)
- Current DBS surgical workflow
- What is DBS Guide?
- Why 3D Slicer?
- Methods
- Case example
@olend


---
@title[Current DBS surgical workflow]

@snap[north-west span-120]
## Current DBS surgical workflow
@snapend
<br><br>
@ul[list-bullets-squares](false)
- Preoperative electrode trajectories planning
- MRI sequences merged with stereotactic frame CT
- Stereotactic procedure carried out
- Trajectory refined by intraoperative electrophysiology 
- Postoperative images determine actual electrode position
@ulend


---
@title[Drawbacks to current workflow]

@snap[north-west span-120]
## Drawbacks to current workflow
@snapend
<br><br>
@ul[list-bullets-squares](false)
- Commercial software is required for surgery
  - Often lacks state-of-the-art algorithms
  - Restricts the usage of the data for research
- No integration of DBS systems
  - i.e. Medtronic, Boston Scientific
@ulend


---
@title[What is DBS Guide?]
@snap[north-west span-120]
## What is DBS Guide?
@snapend
<br><br>
@ul[list-bullets-squares](false)
- Surgical planning and postoperative assessment
- Open-source automated workflow
- All data can be de-identified by the user
- Data is stored in easy to read file formats
@ulend


---
@title[Data storage]
@snap[north-west span-120]
## Data storage
@snapend
<br><br>

```
└── settings
└── summaries
└── data
```


---
@title[Settings]
@snap[north-west span-120]
## Settings directory
@snapend
<br><br>

```markdown
└── settings
    └── model_color.json
    └── model_visibility.json
└── summaries
└── data
```


---
@title[Summaries]
@snap[north-west span-120]
## Summaries directory
@snapend
<br><br>

```markdown
└── settings
└── summaries
    └── contact_summary.csv
    └── patient_summary.json
    └── *_surgical_data.json
└── data
```
@[3](Planned/actual contact position summary)
@[3,4](Summary of patient<br>&nbsp;&nbsp;&nbsp;&nbsp;- surgery date<br>&nbsp;&nbsp;&nbsp;&nbsp;- target)
@[3,4,5](All surgical data<br>&nbsp;&nbsp;&nbsp;&nbsp;- coordinates <br>&nbsp;&nbsp;&nbsp;&nbsp;- angles <br>&nbsp;&nbsp;&nbsp;&nbsp;- MER tracks)

---
@title[Data]
@snap[north-west span-120]
## Data directory
@snapend
<br><br>

```markdown
└── settings
└── summaries
└── data
    └── actual
    └── anat
    └── markups
    └── planned
    └── transforms
```
@[4](&nbsp;&nbsp;&nbsp;&nbsp;- contacts <br>&nbsp;&nbsp;&nbsp;&nbsp;- leads <br>&nbsp;&nbsp;&nbsp;&nbsp;- MER activity<br>&nbsp;&nbsp;&nbsp;&nbsp;- MER tracks)
@[4,5](Imaging data stored as .nii files)
@[4,5,6](.csv files for fiducial points)
@[4,5,6,7](Same subdirectories as actual)
@[4,5,6,7,8](Any transforms performed [i.e. ACPC transform])


---
@title[Data]
@snap[north-west span-120]
## Data directory
@snapend
<br><br>

```markdown
└── data
    └── actual
        └── contacts
        └── leads
        └── mer_activity
        └── mer_trajectories
```
@[3,4,5,6](stored as .vtk files)

---
@title[Contents]
### Contents

@ol[](false)
- What is React.js?
- Why React.js?
- **Setup**
- Your First Component
@olend

