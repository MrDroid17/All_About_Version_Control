What is .gitignore file and why do we needit?

    If you want to keep a file in your project's directory structure but make sure it isn't accidentally committed to the
    project, you can use the specially named file, .gitignore. Add this file to your project in the same directory that 
    the hidden .git directory is located. 

    once you have created .gitignore file ,list the names of files that you want Git to ignore (not track) and it will
    ignore them.

what is Globbing?

    Globbing is the process of expanding a non-specific file name containing a wildcard character into a set of specific 
    file names that exist in storage on a computer, server, or network. A wildcard is a symbol that can stand for one or
    more characters. The most common wildcard symbols are the question mark (?) for a single character and the asterisk(*)
    for a contiguous string of characters. 

    Globbing lets you use special characters to match patterns/characters. In the .gitignore file, you can use the
    following:

    *   blank lines can be used for spacing
    *   # - marks line as a comment
    *   * - matches 0 or more characters
    *   ? - matches 1 character
    *   [abc] - matches a, b, or c
    *   ** - matches nested directories - a/**/z matches
        


        To see .gitignore and globbing in action checkout this link: 

Example:

Let's try it with the "IgnoreMe.docx" file. Add the following line inside the .gitignore file:

project.docx


Let's say that you add 50 images to your project, but want Git to ignore all of them. Does this mean
 you have to list each and every filename in the .gitignore file? Oh gosh no, that would be crazy! 
 Instead, you can use a concept called globbing.

So if all of the 50 images are JPEG images in the "samples" folder, we could add the following line 
to .gitignore to have Git ignore all 50 images.

samples/*.jpg