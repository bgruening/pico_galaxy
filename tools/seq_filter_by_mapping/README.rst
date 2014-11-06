Galaxy tool to filter FASTA, FASTQ or SFF sequences by SAM/BAM mapping
======================================================================

This tool is copyright 2014 by Peter Cock, The James Hutton Institute
(formerly SCRI, Scottish Crop Research Institute), UK. All rights reserved.
See the licence text below.

This tool is a short Python script (using Biopython library functions) which
divides a FASTA, FASTQ, or SFF file in two, those sequences which do or do
not map according to given SAM/BAM file(s).

Example uses include mapping of FASTQ reads against a known contaminant
in order to remove reads prior to a de novo assembly.

This tool is available from the Galaxy Tool Shed at:

* http://toolshed.g2.bx.psu.edu/view/peterjc/seq_filter_by_mapping

See also related tools:

* http://toolshed.g2.bx.psu.edu/view/peterjc/seq_filter_by_id
* http://toolshed.g2.bx.psu.edu/view/peterjc/seq_select_by_id
* http://toolshed.g2.bx.psu.edu/view/peterjc/seq_rename


Automated Installation
======================

This should be straightforward using the Galaxy Tool Shed, which should be
able to automatically install the dependency on Biopython and samtools
and then install this tool and run its unit tests.


Manual Installation
===================

There are just two files to install to use this tool from within Galaxy:

* ``seq_filter_by_mapping.py`` (the Python script)
* ``seq_filter_by_mapping.xml`` (the Galaxy tool definition)

The suggested location is a dedicated ``tools/seq_filter_by_mapping/`` folder.

You will also need to modify the ``tools_conf.xml`` file to tell Galaxy to offer the
tool. One suggested location is in the filters section. Simply add the line::

    <tool file="seq_filter_by_mapping/seq_filter_by_mapping.xml" />

If you wish to run the unit tests, also move/copy the ``test-data/`` files
under Galaxy's ``test-data/`` folder. Then::

    $ ./run_tests.sh -id seq_filter_by_mapping

You will also need to install Biopython 1.54 or later. That's it.


History
=======

======= ======================================================================
Version Changes
------- ----------------------------------------------------------------------
v0.0.1  - Initial version.
======= ======================================================================


Developers
==========

Development is on this GitHub repository:
https://github.com/peterjc/pico_galaxy/tree/master/tools/seq_filter_by_mapping

Much of the code was copied from my older tool:
https://github.com/peterjc/pico_galaxy/tree/master/tools/seq_filter_by_id

For making the "Galaxy Tool Shed" http://toolshed.g2.bx.psu.edu/ tarball use
the following command from the Galaxy root folder::

    $ tar -czf seq_filter_by_mapping.tar.gz tools/seq_filter_by_mapping/README.rst tools/seq_filter_by_mapping/seq_filter_by_mapping.* tools/seq_filter_by_mapping/tool_dependencies.xml

Check this worked::

    $ tar -tzf seq_filter_by_mapping.tar.gz
    tools/seq_filter_by_mapping/README.rst
    tools/seq_filter_by_mapping/seq_filter_by_mapping.py
    tools/seq_filter_by_mapping/seq_filter_by_mapping.xml
    tools/seq_filter_by_mapping/tool_dependencies.xml


Licence (MIT)
=============

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.