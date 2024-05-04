* Eclipse RCP-2023-12: https://www.eclipse.org/downloads/packages/release/2023-12/r/eclipse-ide-rcp-and-rap-developers
* JDK9 (Open JDK9 for Mac OSX with Apple silicon, https://jdk.java.net/archive/)

* [Training demo (including Eclipse configuration)](https://unomail-my.sharepoint.com/:v:/g/personal/myoungkyu_unomaha_edu/EaJxymO8QzlCvDhDwIBnLz4BKeoejzT1Cs1YEGGXLU-6dA?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=Z59owy){:target="_blank"}
* [Testing demo](https://unomail-my.sharepoint.com/:v:/g/personal/myoungkyu_unomaha_edu/Eez5XCw3TWVKhQPw73MpC4cB0Rhh51EJeO1pyr5hrgjv5Q?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=NIPKtm){:target="_blank"}
* [How to Add New Implementations](https://unomail-my.sharepoint.com/:v:/g/personal/myoungkyu_unomaha_edu/ET5lof3qjuBCrYStIfkiXA4BifFV5fKj6M1vLXVtnDTxwA?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=6NzXcf){:target="_blank"}
* [How to Import Eclipse Project and Add New Implementations with 2 Outputs Counters and Vocabulary](https://unomail-my.sharepoint.com/:v:/g/personal/myoungkyu_unomaha_edu/EZuQXRL13sdAiznZEM6drDgBhK334rwJXoYQCO3BMmPQ8w?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=XBcXua){:target="_blank"}
---

    Right-click on the file src/slp/core/CLI.java that contains the main method.
    Run.
    Confirm HELP info.

    Setting up Run Configurations in Eclipse
    Open Run Configurations:
        Right-click on the file CLI.java
        Navigate to Run As > Run Configurations.... This opens the Run Configurations dialog.

    Set the Program Arguments:
        With your configuration selected, go to the Arguments tab.
        In the Program arguments field, you can enter the arguments.

    Apply and Run:
        Click Apply to save your configuration.
        Click Run to run your application with these arguments.
---

Training Parameters: 

    train --train train --counter train.counts --vocabulary train.vocab --order 6 -l java --delims --giga

Training result:

    Using lexer JavaLexer
    Counting at file 1000, tokens processed: 4645672 in 4s
    Counting complete, files: 1520, tokens: 9854086, time: 7s
    Resolving to VirtualCounter
    12%...12%...18%...25%...31%...37%...50%...43%...56%...62%...68%...75%...81%...87%...93%...100%...
    Resolved in 3s
    Writing counter to file
    WARNING: An illegal reflective access operation has occurred
    WARNING: Illegal reflective access by org.jboss.marshalling.Marshalling$OptionalDataExceptionCreateAction$1 (file:/Users/myoungkyu/Desktop/R/workspaces/workspace-slpcore-c-v02/slp-core-v02/lib/SLP-Core_v0.2.jar) to constructor java.io.OptionalDataException(boolean)
    WARNING: Please consider reporting this to the maintainers of org.jboss.marshalling.Marshalling$OptionalDataExceptionCreateAction$1
    WARNING: Use --illegal-access=warn to enable warnings of further illegal reflective access operations
    WARNING: All illegal access operations will be denied in a future release
    Counter written in 1s
    Writing vocabulary to file
    Vocabulary written
---

Testing Parameters: 

    test --test test --counter train.counts --vocabulary train.vocab -o 6 --model jm --cache --nested -l java --delims

Testing Result:

    Using lexer JavaLexer
    Retrieving vocabulary from file
    Retrieving counter from file
    WARNING: An illegal reflective access operation has occurred
    WARNING: Illegal reflective access by org.jboss.marshalling.Marshalling$OptionalDataExceptionCreateAction$1 (file:/Users/myoungkyu/Desktop/R/workspaces/workspace-slpcore-c-v02/slp-core-v02/lib/SLP-Core_v0.2.jar) to constructor java.io.OptionalDataException(boolean)
    WARNING: Please consider reporting this to the maintainers of org.jboss.marshalling.Marshalling$OptionalDataExceptionCreateAction$1
    WARNING: Use --illegal-access=warn to enable warnings of further illegal reflective access operations
    WARNING: All illegal access operations will be denied in a future release
    Counter retrieved in 0s
    Modeling @ file 100 (44005 tokens, 7s), entropy: 2.5272
    Modeling @ file 200 (60885 tokens, 9s), entropy: 3.5339
    Modeling @ file 300 (72408 tokens, 10s), entropy: 3.8238
    Modeling @ file 400 (173907 tokens, 16s), entropy: 4.2560
    Testing complete, modeled 450 files with 225314 tokens yielding average entropy:    4.0277
---
