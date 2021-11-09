# taggedpymolpysnips: Tagged templates for running PyMOL from JupyterLab

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
![Version](https://img.shields.io/static/v1?label=taggedpymolpysnips&message=0.1&color=brightcolor)

For details on installing the taggedpymolpysnips library for **JupyterLab**, go to the [GitHub Page](https://mooerslab.github.io/taggedpymolpysnips/) associated with this project.
For a list of the snippets and their descriptions, also go to the [GitHub Page](https://MooersLab.github.io/taggedpymolpysnips/) associated with this project.

<a id="table-of-contents"><h2>Table of Contents</h2></a>

* [Motivation](#motivation)
* [New to scripting in PyMOL](#new)
* [Tech Stack](#technology-stack)
* [Installation](#installation)
* [Configuration Setup](#configuration-setup)
* [Usage](#usage)
* [Testing](#testing)
* [Requests for new snippets and text editors](#requests)
* [Bug reports](#bugreports)
* [Roadmaps](#roadmap)
* [License](#license)
* [Contact Information](#contact-information)
* [How to cite](#citation)


<a id="motivation"><h2>Motivations for this project</h2></a>

### Use taggedpymolpysnips to be more productive while running PyMOL in Jupyterlab with the elyra-code-snippets-extension


<p>The animation below demonstrates the use of the <b>ao</b> snippet in <em>taggedpymolpysnips</em> to insert 17 lines of code for generating the ambient occlusion effect. 
The snippet will appear in a list of autosuggestions after entering the first several letters of its tab trigger. 
Note that entering <b>ao</b> was not sufficient to bring up the ao snippet. 
I had to enter <b>aod</b> to bring up the ao snippet in the list.</p>

<p align="center"><img src="gifs/accessingsnippets.gif"></p>



The result of applying a variant of the above code to a 27-nucleotide RNA hairpin is shown below.

<p align="center"><img src="./images/ao5d99.png" alt="HTML5 Icon" style="width:640px;height:480px;"></p>

There is no option in a pulldown menu in **PyMOL** to apply the ambient occlusion effect. 
A script file with 17 commands is required.
This code can be applied to any molecular object that has been loaded into **PyMOL**.

[Return to Table of Contents](#table-of-contents)


### Why run PyMOL in JupyterLab?

#### 1. JupyterLab is very easy to use.

The code cells are easy to execute and edit with help from the menu pull-downs.
The keyboard shortcuts for Jupyter are modest in number and fast to master.


#### 2. Illustrate JupyterLab with molecular images

You can illustrate your **JupyterLab** documents with images created in **PyMOL**.
You can also adjust molecular images from within **JupyterLab** without having to open **PyMOL**, thereby saving time.


#### 3. Jupyter notebooks are easy to edit in JupyterLab <!--  -->

The Jupyter notebooks have a gentle learning curve because they are easy to edit.
The code blocks can be run individually during the development of the code or all of the code block can be run at once.


#### 4. Combine PyMOL output with statistical packages

The output from structure analysis can be directly imported into statistical for further analysis.
The presence of output from **PyMOL** and statistical packages in the same document eases the tracking of the results and supports reproducible research.


#### 5. Streamlines the management of images for a project
The images generated by **PyMOL** can be stored in one Jupyter notebook file as opposed to having dozens of script and images files sequestered in numerous subfolders.
The use of one file greatly eases finding the code to make a particular figure because the code and image can be next to each other. <!--  -->
This ability to easily find the required code at a later time reduces the resistance to remaking a figure for manuscript resubmission, journal cover artwork, posters, platform presentations, lectures, book chapters, review articles, websites, and wall hangings.

The use of one file also eases the sharing of images with collaborators because only one file needs to be shared.
If the collaborators are not **PyMOL** or **JupyterLab** users, the notebook file can be reformatted as a PDF or HTML file.


#### 6. Facilitates combining PyMOL with other software in molecular structure analysis

Other software can be run from the same notebook during a molecular structure analysis project provided that this software has Python APIs.
This can improve the reproducibility of the computational aspects of your research.

[Return to Table of Contents](#table-of-contents)


### But I will miss the interactive viewport in PyMOL!

1. You can run the PyMOL GUI next to your **JupyterLab** session. You can adjust the molecule's orientation manually, run the **get_view** command, and copy the output in the command history window from **PyMOL** and paste it into a cell in the **Jupyter notebook**.
The one line of settings returned by the **rv** shortcut is much easier to work with (see [PyMOL shortcuts](https://github.com/MooersLab/pymolshortcuts)). 

2. You do not need the viewport. With 10-15 minutes of practice, you can master the rapid iterating of **rotate** and **translate** commands to adjust the molecule's orientation with greater precision than via manipulation of the mouse.

[Return to Table of Contents](#table-of-contents)


<a id="new"><h2>New to PyMOL scripting?</h2></a>

If you are not ready to write **PyMOL** scripts, please consider using [PyMOL shortcuts](https://github.com/MooersLab/pymolshortcuts) to enhance your productivity in **PyMOL** interactive sessions.
For example, the above ambient occlusion effect can be invoked at any time by entering **AO** at the **PyMOL** prompt, if the *pymolshortcuts.py* file has been loaded.
These shortcuts can also be invoked in **JupyterLab** by submitting them as arguments to the cmd.do() method, (e.g., cmd.do("AO") to generate the ambient occlusion effect.)

## Application Description

The **taggedpymolpysnips** library contains 260 code fragments (i.e, templates or snippets) written in Python to run **PyMOL** in **JupyterLab** via **PyMOL**'s **Python** API through the **reticulate** package.
This API is only available for recent versions of **PyMOL** that depend on Python3 from Anaconda.
This API is available for both the incentive and open-source versions of **PyMOL**.
A conda env with Python 3.8 or later as the default Python interpreter is required.
**PyMOL** must be installed in this env.

[Return to Table of Contents](#table-of-contents)


<a id="technology-stack"><h2>Technology Stack</h2></a>

| Technology                                                                                 | Version  | Description                                                                                        |
|--------------------------------------------------------------------------------------------|----------|----------------------------------------------------------------------------------------------------|
| [PyMOL](https://pymol.org/2/)                                                              | 2.5.1    | Molecular graphics program                                                                         |
| Python from Anaconda                                                                       | 3.6-3.9  | Programming language                                                                               |
| conda from Anaconda                                                                        | 4.10.1   | Program used to create Python environments.                                                        |
| git                                                                                        | 2.25.1   | Eases the downloading and updating of the libraries.                                               |


Some of the snippets are limited to Python3 code.
If you are using an ancient version of **PyMOL** that relies on Python2, you can buy a license to the current version of **PyMOL**, install a free open-source version of **PyMOL** that depends on Python3 (See the [PyMOL Wiki](https://pymolwiki.org/index.php/Main_Page)), or you can rewrite the snippet's code to be Python2 compliant. 
This often merely involves replacing print functions in Python3 with print statements in Python2.
Note that multiple versions of **PyMOL** can operate side-by-side on a computer, so you do not have to delete the old version of **PyMOL**.


<a id="installation"><h2>Installation of the snippet library</h2></a>

```bash
# If the following directory is missing: ~/.config/rstudio/snippets
mkdir ~/Library/Jupyter/metadata
cd ~/Library/Jupyter/metadata
git clone https://github.com/MooersLab/elyrapymolpysnips.git snippets
```

When you open **JupyterLab**, you will find that the new file python.snippets from rstudiopymolpysnips has replaced the default Python snippets.
These are found under *Preferences/Code/Edit Snippets/Python* (see animation below).
You can edit the snippets and add new ones.
The format is self-explanatory.


<p align="center"><img src="gifs/accessingSnippets.gif"></p>


[Return to Table of Contents](#table-of-contents)

<a id="configuration-setup"><h2>Configuration Setup</h2></a>

The snippet library is independent of **PyMOL**. 
No modification of **PyMOL** is required. 

[Return to Table of Contents](#table-of-contents)


<a id="usage"><h2>Usage</h2></a>

The animation at the top of the page conveys the essential knowledge for usage. 

[Return to Table of Contents](#table-of-contents)


<a id="testing"><h2>Testing</h2></a>

Try the **ao** snippet in Python code cell.
Run the code cell by clicking on the green button.
You should get a result similar to the one shown in the animation above.

[Return to Table of Contents](#table-of-contents)


<a id="requests"><h2>Requests for new snippets</h2></a>

Please use the **Issues tab** above to request support for additional snippets or to ask questions.
Alternatively, you can send [e-mail](#contact-information) to me.

Questions about **PyMOL** should be directed to the [PyMOL Mailing List](https://pymolwiki.org/index.php/PyMOL_mailing_list).

[Return to Table of Contents](#table-of-contents)


<a id="requests"><h2>Contributing</h2></a>

Snippets of new code are most welcome. Send to [e-mail](#contact-information).

- Submit the Python code in a plain text file.
- Write the filenames and function names in camelCase.
- Describe what the code does in one to several sentences, an example of usage, and any citations or links to further information.

[Return to Table of Contents](#table-of-contents)


<a id="bugreports"><h2>Bug reports</h2></a>

Use the **Issues** tab above to report bugs or send [e-mail](#contact-information) to me.

[Return to Table of Contents](#table-of-contents)


<a id="roadmap"><h2>Roadmap</h2></a>

I plan to expand the library to cover with examples the 500 commands and 600 settings in **PyMOL**.

[Return to Table of Contents](#table-of-contents)


<a id="license"><h2>License</h2></a>

We use the permissive MIT license.
The license information for this project is found in the *License.txt* file above. 

[Return to Table of Contents](#table-of-contents)


<a id="contact-information"><h2>Contact Information</h2></a>

Reach me via the Issue tab above or via e-mail: `blaine-mooers at ouhsc.edu`.

[Return to Table of Contents](#table-of-contents)


<a id="citation"><h2>Citation</h2></a>

If you use this library to make figures for publication, please see the *Citation.md* file above.


[Return to Table of Contents](#table-of-contents)

