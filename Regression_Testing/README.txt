In this directory you can run a "regression", i.e.,

    Run the Forvis executable as a RISC-V simulator
    on each of the ELF files in the Test_Programs/ directory and sub-directories,
    placing a log for each in the Logs/ directory
    and printing out a final summary of number of tests run and number of tests that "passed".

To run, first ensure that you have created the Forvis executable
forvis_exe in the top-level directory, then:

    $ cd  Regression_Testing
    $ make

For reference:
    The Logs_sample/ directory is a copy of Logs/ from a previous run.
    make_transcript.txt is a transcript of a previous 'make'

Note: the regression is run by the Python program 'Run_all_tests.py'

    Running it by itself with --help will list its command-line arguments:
        $ Run_all_tests.py  --help

    You can modify the program to change its functionality.

    In particular:

    - It has an 'ignore_list' to filter out certain files in the
        Test_Programs directory, such as tests for features that Forvis
        does not yet implement

    - It has some other ad hoc and fragile ways to ignore .dump files
        (ignores all files with any extension including .dump), and
        looks for the string "32" or "64" in the ELF filename to
        decide whether it should be run in RV32 or RV64 mode.