# bash best practices
a few hints on bash best practice 
=================================

    * use #!/usr/bin/env bash .. this is more portable but you cant rely on a specific version with this
    * use set, dont use options to bash - if someone runs your script with bash scriptname then it will ignore the options to bash
    * use {} to enclose variables - can cause mistakes if you donr - e.g. variable name becomes VAR_ext rather than what you wanted
    * to ensure you always have a value, set defaults - e.g. "${MYNAME}" = "Stuart" - MYNAME defaults to Stuart if not already set
    * use spaces for tabs, not tabs - tab not portable
    * max line length of 80 characters for readability - use \ to split of lines if needed
    * dont have whitespace at end of lines as may confuse source code control like git
    * use $(command) instead of backticks
    * variables and function names lowercase and underscores - use meaninful names
    * constants should be in caps, declare them first in file
    * use readonly to set a variable readonly
    * can use local to make a variable specific to a function
    * put functions together below the constants, I order the functions alphabetically as easier to find
    * use a main function if using multiple functions
    * check return values from functions
    * avoid eval - munges input
    * [[ .. ]] is better than test or /usr/bin/[ - stops pathname expansion and word splitting
    * comment difficult bits of code
    * insecure to have suid/sgid
    * i prefer to have .sh extension so easy to recognise file
    * good set options:
        * -e exit script immediately if command fails
        * -o pipefail fails if any part of a pipe fails
        * -u treat unset variables as an error and exit immediately
        * suggest second line of bash script is: set -eou pipefail
        * -x prints each command before executing it - expands arguments also
        * use -E if script contains traps
    * to start with using a program like shellcheck can be useful - gives your scripts a quick checkover
    * a useful tool if you use vim is the bash support plugin - see https://www.thegeekstuff.com/2009/02/make-vim-as-your-bash-ide-using-bash-support-plugin/
