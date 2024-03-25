# Endpoints called by the web layer 

Certainly! Here's the description of each endpoint in Markdown format:

1. **`/odaapi/api/load`**
   - Likely used to load or retrieve data from the server, possibly a specific file or a set of data based on parameters like `short_name` and `revision`.

2. **`/odaapi/api/displayunits/`**
   - This endpoint might be used to fetch information related to display units, which could be a part of a larger dataset or system configuration, including details like address, units, and logical parameters.

3. **`/odaapi/api/masters/:shortName/branches/`**
   - Retrieves a list of branches (possibly in a version control context or different data branches) associated with a specific master entity identified by `shortName`.

4. **`/odaapi/api/displayunits/1/vmaToLda`**
   - Converts Virtual Memory Addresses (VMA) to Logical Data Addresses (LDA), which is often relevant in contexts like debugging, memory management, or software reverse engineering.

5. **`/odaapi/api/find/`**
   - Searches for specific data within the system, possibly filtering by bytes, `short_name`, and `revision`. This could be used to find occurrences of data patterns or specific byte sequences.

6. **`/odaapi/api/binarystrings/0/`**
   - Might be used for updating or patching binary strings in the system, where binary data or configurations can be modified.

7. **`/odaapi/api/masters/:shortName/can_edit/`**
   - Checks whether the entity identified by `shortName` can be edited, possibly indicating permission levels or edit capabilities in the system.

8. **`/odaapi/api/masters/:shortName/clone/`**
   - Clones or duplicates the master entity identified by `shortName`, potentially creating a copy of a dataset, configuration, or system state.

9. **`/odaapi/api/disassembler/0/options/`**
   - Retrieves disassembler options for a given architecture, which could be related to software reverse engineering, where different architectures require different disassembly settings.

10. **`/odaapi/api/options/0/`**
    - Updates or patches options in the system, which could involve configurations related to the user interface, system operations, or other customizable aspects of the backend service.

11. **`/odaapi/_upload`**
    - Handles file uploads to the server, where users can send files along with metadata like project name and sharing mode.

12. **`/odaapi/api/graph`**
    - Fetches a graphical representation or data structure from the server, possibly used for visualizing relationships, data flows, or structures based on the provided address and revision.

13. **`/odaapi/api/parcels/`**
    - Retrieves parcels, which could be segments or blocks of data, often used in mapping or chunking large datasets into manageable units.

14. **`/odaapi/api/displayunits/1/makeCode/`**
    - Converts data at a specified address to code, possibly for purposes like disassembly or dynamic analysis in software reverse engineering.

15. **`/odaapi/api/displayunits/1/makeData/`**
    - Converts code at a specified address back to data, which might be used in contexts where binary data is being analyzed or manipulated.

16. **`/odaapi/api/definedData/`**
    - Creates or defines new data entities, possibly adding metadata or structure to raw data points in the system.

17. **`/odaapi/api/definedData/0/`**
    - Deletes or undefines data entities, potentially removing previously set definitions or metadata from the system.

18. **`/odaapi/api/comments/`**
    - Adds comments to a specific part of the data, which could be used for annotation, review, or collaborative editing purposes.

19. **`/odaapi/api/operations/`**
    - Retrieves a list of operations, possibly indicating available actions, historical transactions, or system capabilities based on the current state or configuration.

20. **`/odaapi/api/decompiler`**
    - Fetches decompiled code from a given address, which is a common task in reverse engineering, allowing the user to view higher-level code from compiled binaries.

21. **`/odaapi/api/masters/:shortName/set_default_permission_level/`**
    - Sets the default permission level for a master entity, potentially altering who can view, edit, or interact with the entity.

22. **`/odaapi/api/displayunits/1/makeFunction/`**
    - Defines a new function at a given address, possibly for adding annotations or definitions in a code analysis or reverse engineering context.

23. **`/odaapi/api/functions/0/`**
    - Updates information about a function, which could involve changing its name, return value, arguments, or other defining characteristics.

24. **`/odaapi/api/cstructs/`**
    - Creates a new structure definition, often used in programming to define complex data types that group together different pieces of data.

25. **`/odaapi/api/cstructs/:index/`**
    - Deletes a structure definition at a given index, possibly removing a previously defined complex data type or template.

26. **`/odaapi/api/cstructs/:index/modify/`**
    - Modifies an existing structure definition, potentially updating its fields, types, or other attributes.

27. **`/odaapi/api/masters/`**
    - Retrieves a list of master entities, which could represent top-level data structures, configurations, or administrative records in the system.

28. **`/odaapi/api/masters/:shortName/`**
    - Deletes a master entity identified by `shortName`, possibly removing a dataset, configuration set, or other significant data grouping.

# Serializers

1. **OdaUserSerializer**: Serializes the `OdaUser` model, including fields like username, email, and a boolean indicating if the user is a "lazy" user.

2. **UserGroupSerializer**: Serializes Django's `Group` model, including a URL field for the detail view and a nested serialization of users in the group.

3. **CommentSerializer**: Serializes comments, with fields for the comment text and a Virtual Memory Address (VMA).

4. **BinaryFileSerializer**: Serializes binary file data, including filename, filesize, and a hash value.

5. **DataStringSerializer**: Serializes strings with their associated memory addresses.

6. **BinaryStringSerializer**: Serializes binary strings.

7. **SymbolSerializer**: Serializes symbols, including their name, VMA, and type.

8. **BranchSerializer**: Serializes branch data, including source and target addresses.

9. **LabelSerializer**: Serializes labels, including the label text and its VMA.

10. **OdaMasterPermissionSerializer**: Serializes `OdaMaster` permissions, including username, user group, and permission level.

11. **OdaMasterPermissionLevelSerializer**: Serializes permission level names.

12. **OdaMasterSerializer**: Serializes the `OdaMaster` model, including project name, short name, default permission level, revision, creation date, and permissions.

13. **FunctionSerializer**: Serializes function data, including return value, arguments, VMA, and name.

14. **CStructFieldTypeSerializer**: Serializes C-structure field types, including kind, name, and size.

15. **UserSerializer**: Serializes user data, including username, lazy user status, last login, email, and date joined.

16. **CStructFieldSerializer**: Serializes C-structure fields, including name, kind, type, and size.

17. **CStructSerializer**: Serializes C-structures, including name, packed status, fields, and object ID.

18. **DefinedDataSerializer**: Serializes defined data, including type kind, type name, variable name, VMA, and size.

19. **ParcelSerializer**: Serializes parcels of data, including start and end VMAs, start LDA, and a code indicator.

20. **RefSerializer**: Serializes references, including a VMA.

21. **DisplayUnitSerializer**: Serializes display units, including section name, VMA, raw bytes, instruction string, and references.

22. **SectionFlagSerializer**: Serializes section flags, including abbreviation, description, and name.

23. **OperationsSerializer**: Serializes operations, including datetime, user, operation name, and description.

24. **SectionSerializer**: Serializes sections, including name, size, VMA, and flags.

25. **StringSerializer**: Serializes strings, including their address and content.

26. **FindResultsSerializer**: Serializes find operation results, including address and section.

# Notes 

/displayunits is called when browsing the dissambled code .. 

This is what is returned 
```json
[
  {
    "section_name": ".text",
    "vma": 4225279,
    "rawBytes": "c60069",
    "instStr": "mov    BYTE PTR [rax],0x69",
    "branch": "",
    "branch_label": "",
    "opcode": "mov",
    "operands": "BYTE PTR [rax],0x69",
    "stringRef": null,
    "branchRef": null,
    "targetRef": null,
    "crossRef": [],
    "isBranch": false,
    "isFunction": false,
    "labelName": "abc",
    "isCode": true
  }
]
```

/comments creates a comment on a VMA 
/makeFunction creates or updates a function at a VMA
```json
{
  "short_name": "TDGJqvdo",
  "revision": 0,
  "vma": 4228143,
  "name": "my_call_function",
  "retval": "unknown",
  "args": "unknown"
}
```

For display there is a web renderer that shows something like this : 

![img.png](img.png)

