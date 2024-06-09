Overview

The proprietary language used by Yara for rules is easy to learn but challenging to master, as the effectiveness of your rule depends on your understanding of the patterns you want to search for.
Using a Yara Rule

Every Yara command requires two arguments:

    The rule file you create
    The name of the file, directory, or process ID to use the rule for.

Every rule must have a name and a condition.

Example Command:

sh

yara myrule.yar somedirectory

(Note: .yar is the standard file extension for all Yara rules.)
Creating Your First Yara Rule

    Create a file named "somefile":

    sh

touch somefile

Create a new file named "myfirstrule.yar":

sh

touch myfirstrule.yar

Open "myfirstrule.yar" with a text editor (e.g., nano) and input the following snippet:

sh

nano myfirstrule.yar

yara

    rule examplerule {
        condition: true
    }

Explanation

    Rule Name: examplerule
    Condition: condition: true

This rule checks if the specified file/directory/PID exists. If it does, Yara outputs examplerule.
Testing Your Rule

Command:

sh

yara myfirstrule.yar somefile

Output if the file exists:

sh

examplerule somefile

Output if the file does not exist:

sh

error scanning sometextfile: could not open file

Yara Conditions Continued
Overview

Checking for file existence isn't particularly useful. Yara conditions can do much more. Here are some key components:
Meta Section

Reserved for descriptive information by the rule's author. This section does not influence the rule's functionality. For example:

yara

meta:
    desc = "Checks for Hello World string"

Strings

Strings allow searching for specific text or hexadecimal patterns in files.

Example: Basic String Search

yara

rule helloworld_checker {
    strings:
        $hello_world = "Hello World!"

    condition:
        $hello_world
}

This rule matches files containing the exact string "Hello World!".

Case-Insensitive Search

yara

rule helloworld_checker {
    strings:
        $hello_world = "Hello World!"
        $hello_world_lowercase = "hello world"
        $hello_world_uppercase = "HELLO WORLD"

    condition:
        any of them
}

This rule matches files containing "Hello World!" in any case.
Conditions

Yara supports various conditions similar to regular programming:

    <= less than or equal to
    >= greater than or equal to
    != not equal to

Example: Limiting Occurrences

yara

rule helloworld_checker {
    strings:
        $hello_world = "Hello World!"

    condition:
        #hello_world <= 10
}

This rule matches files with 10 or fewer occurrences of "Hello World!".
Combining Keywords

You can combine multiple conditions using:

    and
    not
    or

Example: Combining Conditions

yara

rule helloworld_checker {
    strings:
        $hello_world = "Hello World!"

    condition:
        $hello_world and filesize < 10KB
}

This rule matches files containing "Hello World!" and with a file size less than 10KB.
Testing Rules

Command:

sh

yara myfirstrule.yar mytextfile.txt

Example Output:

sh

helloworld_textfile_checker mytextfile.txt

    The rule name is shown in red.
    The matched file is shown in green.
