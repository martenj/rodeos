.. _impl_sequencers:

=====================
Connecting Sequencers
=====================

Currently RODEOS has support for Illumina sequencing machines only.
These sequencers are connected to Windows-based driver computers that write to network shares.

RODEOS uses Windows network shares to expose the landing zones to the sequencing machines.
It is best practice to:

- have one account setup for each sequencing machine as these machines are usually directly accessible to any user who walks up to them,
- have one network file share for each sequencing machine that is mounted on the machines automatically.

In the case of not being able to configure file mounts through the Windows ActiveDirectory / network file share infrastructure of the organisation, a Windows BAT file such as the following one can be used to mount the network share at a given drive (here ``U:``).

.. code-block:: winbatch
    :caption: File ``Connect RODEOS.bat``

    net use /delete u: >nul
    net use u: \\<server>\<share> /user:<user>@<domain> <password>

Such files can be placed directly on the Windows Desktop and the instrument operator can connect the network shares before starting the sequencing.
RODEOS will move the sequencing data directly after detecting that the sequencing is complete such that persons accessing the instrument can only see the currently run being written (if any).
