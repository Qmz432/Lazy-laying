# S-EXPRESSION GRAMMAR LEARNING
In this document, I will record the main point of the S-EXPRESSION GRAMMAR. And the primary material is the technical documentation provided by [Kicad](https://dev-docs.kicad.org/en/file-formats/). So words below will be highly probably similar to their documentation. 
 
## INTRODUCTION
### SYNTAX
**1. TOKEN**
Token is the basic unit in the s-expression and its definitions are delimited by opening `(` and closing `)` parenthesis. And all tokens are lowercase. White space characters or special characters other than the underscore '_' character are not allowed. Tokens can have zero or more attributes which means that tokens in an s-expression can be nested within other tokens to form a tree-like structure. And in the token is the token attributes.

Token attributes are upper-case descriptive names. For example `(at X Y)`, X is the horizontal coordinate, Y is the vertical coordinate and at is the token. Some tokens have a limited number of possible attribute values which are separated by a logical or character '|'.  For example `(visible yes|no)` the only valid attributes for the `visible` token are `yes` or `no`. Some tokens have optional attributes which are enclosed in square braces. For example `(paper A0 [portrait])` the page portrait setting is optional.

**2. STRING**
All strings are quoted using the double quote character (") and are UTF-8 encoded. 

**3. COORDINATES AND SIZES**
All values are given in millimeters. Exponential floating point values are not used for readability purposes. All coordinates are relative to the origin of their containing object which could form a line.

## COMMON SYNTAX
In this section, all syntax crossing the symbol library, footprint library, schematic, board, and worksheet file formats are shared. Though we just use the Footprint file, it's better to read it all.

### LIBRARY IDENTIFIER
This section is prepared for the schematic symbol library and printed circuit board footprint library. Both libraries use library identifiers which are defined as a quoted string using the "LIBRARY_NICKNAME: ENTRY_NAME" format where "LIBRARY_NICKNAME" is the nickname of the library in the symbol or footprint library table and "ENTRY_NAME" is the name of the symbol or footprint in the library separated by a colon. However, The "LIBRARY_NICKNAME" is not stored in the library files because a library cannot know what the assigned library table nickname is in advance. Only the "ENTRY_NAME" is saved in the library files.

### POSITION IDENTIFIER
The `at` token defines the positional coordinates in the X-Y axis and rotation of an object. The X attribute defines the horizontal position of the object while the Y attribute defines the vertical position of the object. The rotation angle is optional. Symbol `text` ANGLEs are stored in a tenth of a degree. All other ANGLEs are stored in degrees. Below is an example.

```
  (at
    X                                                           
    Y                                                           
    [ANGLE]                                                     
  )
```

### COORDINATE POINT LIST
### STROKE DEFINITION





