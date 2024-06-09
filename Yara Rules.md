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
