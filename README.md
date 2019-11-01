# Data_Vanquisher code for removing sub-directories and files

## Versioning:
Current Version - 1.2
This version is not stopping filemover service or any other service that can prevent files from deleting. 
So, this version 1.2 just deletes the files and sub-directories in directories
that are specified in the config json file.

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

## Copyright (c) 2017-2019, Mayo Foundation for Medical Education and Research (MFMER) 
All rights reserved. GNU General Public License v3.0. Academic, non-commercial use of this software is allowed with expressed permission of the developers. 

### Contributors: Vaclav Kremen.

## ORCA Vanquisher 1.2 done by Vaclav Kremen: kremen.vaclav@mayo.edu
