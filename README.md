# ORCA_or_RC+S_Data_Vanquisher code for removing sub-directories created by Medtronic ORCA or Summit RC+S RDK
----------------------------------------------------------------------

## Versioning:
----------------------------
Original Version - 1.1
Removed unnecesary code and renamed to ORCA_Vanquisher when filemover was running. 
It stopped the service and deleted folders.

Current Version - 1.2
This version is not stopping filemover service. It assumes that ORCA and filemover service
is disabled. So this version 1.2 just deletes the files and sub-directories in directories
that are specified in the config json file.
It suppose the filemover service to be stopped or ORCA uninstalled.
-----------------------------------------------------------------------

## Inputs:
directories2delete.json file with content of directory paths their sub-directories and files need to be deleted.
This file has to be placed in same directory as executable binary.
The content of the file should something look like:
{
  "Folder to Delete #1": "C:\\Medtronic",
  "Folder to Delete #2": "C:\\Medtronic"
}

## Outputs:
The program deletes all sub-directories and files in directories that are spedified in directories2delete.json.
If any of the directories doesnt' exist or is locked by another processes (e.g. filemover service),
it will skip them.
It produces a directoriesdeleted.json file, that contains log of last run of the code, e.g.:
[{"Name":"C:\\Medtronic","Date":"10/30/2019 16:27","Success":"NOT successful"},{"Name":"C:\\Medtronic","Date":"10/30/2019 16:27","Success":"NOT successful"}]
-------------------------------------------------------------------------

## Copyright (c) 2017-2019, Mayo Foundation for Medical Education and Research (MFMER), All rights reserved. Academic, non-commercial use of this software is allowed with expressed permission of the developers. MFMER and the developers disclaim all implied warranties of merchantability and fitness for a particular purpose with respect to this software, its application, and any verbal or written statements regarding its use. The software may not be distributed to third parties without consent of MFMER. Use of this software constitutes acceptance of these terms and acceptance of all risk and liability arising from the software’s use.

### Contributors: Vaclav Kremen, Gregory Worrell.

## ORCA Vanquisher 1.2 done by Vaclav Kremen: kremen.vaclav@mayo.edu
--------------------------------------------------------------------------
