.. _eb_help:

.. _basic_usage_help:

*(see also* ``eb --help`` *)*

Usage
-----

``eb [options] easyconfig [...]``

Description
-----------

Builds software based on easyconfig (or parse a directory).
Provide one or more easyconfigs or directories, use -H or --help more information.

Help options
------------
==========================================    ======================================
Option flag                                   Option description                    
==========================================    ======================================
``--version``                                 show program's version number and exit
``-h, --shorthelp``                           show short help message and exit      
``-H OUTPUT_FORMAT, --help=OUTPUT_FORMAT``    show full help message and exit       
``--confighelp``                              show help as annotated configfile     
==========================================    ======================================


Debug and logging options (configfile section MAIN)
---------------------------------------------------
===============    =========================================
Option flag        Option description                       
===============    =========================================
``-d, --debug``    Enable debug log mode (def False)        
``--info``         Enable info log mode (def False)         
``--quiet``        Enable quiet/warning log mode (def False)
===============    =========================================


Configfile options
------------------
=========================================    ================================================================
Option flag                                  Option description                                              
=========================================    ================================================================
``--configfiles=CONFIGFILES``                Parse (additional) configfiles (type comma-separated list; def )
``--ignoreconfigfiles=IGNORECONFIGFILES``    Ignore configfiles (type comma-separated list)                  
=========================================    ================================================================


Basic options
-------------
=======================================    ==================================================================================================================================================================================================================================================
Option flag                                Option description                                                                                                                                                                                                                                
=======================================    ==================================================================================================================================================================================================================================================
``--dry-run``                              Print build overview incl. dependencies (full paths) (def False)                                                                                                                                                                                  
``-D, --dry-run-short``                    Print build overview incl. dependencies (short paths) (def False)                                                                                                                                                                                 
``-x, --extended-dry-run``                 Print build environment and (expected) build procedure that will be performed (def False)                                                                                                                                                         
``--extended-dry-run-ignore-errors``       Ignore errors that occur during dry run (def True)                                                                                                                                                                                                
``-f, --force``                            Force to rebuild software even if it's already installed (i.e. if it can be found as module), and skipping check for OS dependencies (def False)                                                                                                  
``--job``                                  Submit the build as a job (def False)                                                                                                                                                                                                             
``-l, --logtostdout``                      Redirect main log to stdout (def False)                                                                                                                                                                                                           
``-M, --missing-modules``                  Print list of missing modules for dependencies of specified easyconfigs (def False)                                                                                                                                                               
``-b BLOCKS, --only-blocks=BLOCKS``        Only build listed blocks (type comma-separated list)                                                                                                                                                                                              
``--rebuild``                              Rebuild software, even if module already exists (don't skip OS dependencies checks) (def False)                                                                                                                                                   
``-r PATH[:PATH], --robot=PATH[:PATH]``    Enable dependency resolution, using easyconfigs in specified paths (type pathsep-separated list; def )                                                                                                                                            
``--robot-paths=PATH[:PATH]``              Additional paths to consider by robot for easyconfigs (--robot paths get priority) (type pathsep-separated list; def /home/example/develop/easybuild-easyconfigs/easybuild/easyconfigs)                                                        
``--search-paths=PATH[:PATH]``             Additional locations to consider in --search (next to --robot and --robot-paths paths) (type pathsep-separated list; def )                                                                                                                        
``-k, --skip``                             Skip existing software (useful for installing additional packages) (def False)                                                                                                                                                                    
``-s STOP, --stop=STOP``                   Stop the installation after certain step (type choice; def source) (choices: fetch, ready, source, patch, prepare, configure, build, test, install, extensions, postiter, postproc, sanitycheck, cleanup, module, permissions, package, testcases)
``--strict=STRICT``                        Set strictness level (type choice; def warn) (choices: ignore, warn, error)                                                                                                                                                                       
=======================================    ==================================================================================================================================================================================================================================================


Configuration options
---------------------
=================================================================    ============================================================================================================================================================================================================================================================================
Option flag                                                          Option description                                                                                                                                                                                                                                                          
=================================================================    ============================================================================================================================================================================================================================================================================
``--avail-module-naming-schemes``                                    Show all supported module naming schemes (def False)                                                                                                                                                                                                                        
``--avail-modules-tools``                                            Show all supported module tools (def False)                                                                                                                                                                                                                                 
``--avail-repositories``                                             Show all repository types (incl. non-usable) (def False)                                                                                                                                                                                                                    
``--buildpath=BUILDPATH``                                            Temporary build path (def /home/example/.local/easybuild/build)                                                                                                                                                                                                             
``--containerpath=CONTAINERPATH``                                    Location where container recipe & image will be stored (def /home/example/.local/easybuild/containers)                                                                                                                                                                      
``--external-modules-metadata=EXTERNAL-MODULES-METADATA``            List of (glob patterns for) paths to files specifying metadata for external modules (INI format) (type comma-separated list)                                                                                                                                                
``--hooks=HOOKS``                                                    Location of Python module with hook implementations (type str)                                                                                                                                                                                                              
``--ignore-dirs=IGNORE-DIRS``                                        Directory names to ignore when searching for files/dirs (type comma-separated list; def .git,.svn)                                                                                                                                                                          
``--include-easyblocks=INCLUDE-EASYBLOCKS``                          Location(s) of extra or customized easyblocks (type comma-separated list; def )                                                                                                                                                                                             
``--include-module-naming-schemes=INCLUDE-MODULE-NAMING-SCHEMES``    Location(s) of extra or customized module naming schemes (type comma-separated list; def )                                                                                                                                                                                  
``--include-toolchains=INCLUDE-TOOLCHAINS``                          Location(s) of extra or customized toolchains or toolchain components (type comma-separated list; def )                                                                                                                                                                     
``--installpath=INSTALLPATH``                                        Install path for software and modules (def /home/example/.local/easybuild)                                                                                                                                                                                                  
``--installpath-modules=INSTALLPATH-MODULES``                        Install path for modules (if None, combine --installpath and --subdir-modules)                                                                                                                                                                                              
``--installpath-software=INSTALLPATH-SOFTWARE``                      Install path for software (if None, combine --installpath and --subdir-software)                                                                                                                                                                                            
``--job-backend=JOB-BACKEND``                                        Backend to use for submitting jobs (type choice; def GC3Pie) (choices: GC3Pie, PbsPython, Slurm)                                                                                                                                                                            
``--logfile-format=DIR,FORMAT``                                      Directory name and format of the log file (type comma-separated tuple; def easybuild,easybuild-%(name)s-%(version)s-%(date)s.%(time)s.log)                                                                                                                                  
``--module-depends-on``                                              Use depends_on (Lmod 7.6.1+) for dependencies in all generated modules (implies recursive unloading of modules). (def False)                                                                                                                                                
``--module-extensions``                                              Include 'extensions' statement in generated module file (Lua syntax only) (def False)                                                                                                                                                                                       
``--module-naming-scheme=MODULE-NAMING-SCHEME``                      Module naming scheme to use (def EasyBuildMNS)                                                                                                                                                                                                                              
``--module-syntax=MODULE-SYNTAX``                                    Syntax to be used for module files (type choice; def Lua) (choices: Lua, Tcl)                                                                                                                                                                                               
``--moduleclasses=MODULECLASSES``                                    Extend supported module classes (For more info on the default classes, use --show-default-moduleclasses) (type comma-separated list; def base,astro,bio,cae,chem,compiler,data,debugger,devel,geo,ide,lang,lib,math,mpi,numlib,perf,quantum,phys,system,toolchain,tools,vis)
``--modules-footer=PATH``                                            Path to file containing footer to be added to all generated module files                                                                                                                                                                                                    
``--modules-header=PATH``                                            Path to file containing header to be added to all generated module files                                                                                                                                                                                                    
``--modules-tool=MODULES-TOOL``                                      Modules tool to use (type choice; def Lmod) (choices: EnvironmentModules, EnvironmentModulesC, EnvironmentModulesTcl, Lmod)                                                                                                                                                 
``--package-naming-scheme=PACKAGE-NAMING-SCHEME``                    Packaging naming scheme choice (type choice; def EasyBuildPNS) (choices: EasyBuildPNS)                                                                                                                                                                                      
``--packagepath=PACKAGEPATH``                                        The destination path for the packages built by package-tool (def /home/example/.local/easybuild/packages)                                                                                                                                                                   
``--prefix=PREFIX``                                                  Change prefix for buildpath, installpath, sourcepath and repositorypath (used prefix for defaults /home/example/.local/easybuild)                                                                                                                                           
``--recursive-module-unload``                                        Enable generating of modules that unload recursively. (def False)                                                                                                                                                                                                           
``--repository=REPOSITORY``                                          Repository type, using repositorypath (type choice; def FileRepository) (choices: FileRepository)                                                                                                                                                                           
``--repositorypath=REPOSITORYPATH``                                  Repository path, used by repository (is passed as list of arguments to create the repository instance). For more info, use --avail-repositories. (type comma-separated list; def /home/example/.local/easybuild/ebfiles_repo)                                               
``--sourcepath=SOURCEPATH``                                          Path(s) to where sources should be downloaded (string, colon-separated) (def /home/example/.local/easybuild/sources)                                                                                                                                                        
``--subdir-modules=SUBDIR-MODULES``                                  Installpath subdir for modules (def modules)                                                                                                                                                                                                                                
``--subdir-software=SUBDIR-SOFTWARE``                                Installpath subdir for software (def software)                                                                                                                                                                                                                              
``--subdir-user-modules=SUBDIR-USER-MODULES``                        Base path of user-specific modules relative to their $HOME                                                                                                                                                                                                                  
``--suffix-modules-path=SUFFIX-MODULES-PATH``                        Suffix for module files install path (def all)                                                                                                                                                                                                                              
``--testoutput=TESTOUTPUT``                                          Path to where a job should place the output (to be set within jobscript)                                                                                                                                                                                                    
``--tmp-logdir=TMP-LOGDIR``                                          Log directory where temporary log files are stored                                                                                                                                                                                                                          
``--tmpdir=TMPDIR``                                                  Directory to use for temporary storage                                                                                                                                                                                                                                      
=================================================================    ============================================================================================================================================================================================================================================================================


Container options
-----------------
===============================================    ======================================================================================================
Option flag                                        Option description                                                                                    
===============================================    ======================================================================================================
``--container-build-image``                        Build container image (requires sudo privileges!) (def False)                                         
``--container-config=CONFIG``                      Configuration for container image (type <type 'str'>)                                                 
``--container-image-format=IMAGE-FORMAT``          Container image format (type choice) (choices: ext3, sandbox, sif, squashfs)                          
``--container-image-name=IMAGE-NAME``              Custom name for container image (defaults to name of easyconfig)                                      
``--container-template-recipe=TEMPLATE-RECIPE``    Template recipe for container image (type <type 'str'>)                                               
``--container-tmpdir=TMPDIR``                      Temporary directory where container image is built                                                    
``--container-type=TYPE``                          Type of container recipe/image to create (type choice; def singularity) (choices: docker, singularity)
===============================================    ======================================================================================================


Options for Easyconfigs
-----------------------
===================================================    ================================================================================================================================================================================================================================================
Option flag                                            Option description                                                                                                                                                                                                                              
===================================================    ================================================================================================================================================================================================================================================
``--fix-deprecated-easyconfigs``                       Fix use of deprecated functionality in specified easyconfig files. (def False)                                                                                                                                                                  
``--inject-checksums=INJECT-CHECKSUMS``                Inject checksums of specified type for sources/patches into easyconfig file(s) (type choice; def sha256) (choices: adler32, crc32, md5, sha1, sha256, sha512, size)                                                                             
``--local-var-naming-check=LOCAL-VAR-NAMING-CHECK``    Mode to use when checking whether local variables follow the recommended naming scheme ('log': only log warnings (no printed messages); 'warn': print warnings; 'error': fail with an error) (type choice; def warn) (choices: error, log, warn)
===================================================    ================================================================================================================================================================================================================================================


GitHub integration options
--------------------------
=======================================================    ================================================================================================================================
Option flag                                                Option description                                                                                                              
=======================================================    ================================================================================================================================
``--check-contrib``                                        Runs checks to see whether the given easyconfigs are ready to be contributed back (def False)                                   
``--check-github``                                         Check status of GitHub integration, and report back (def False)                                                                 
``--check-style``                                          Run a style check on the given easyconfigs (def False)                                                                          
``--cleanup-easyconfigs``                                  Clean up easyconfig files for pull request (def True)                                                                           
``--close-pr=PR#``                                         Close pull request (type <type 'int'>)                                                                                          
``--close-pr-msg=CLOSE-PR-MSG``                            Custom close message for pull request closed with --close-pr;  (type <type 'str'>)                                              
``--close-pr-reasons=CLOSE-PR-REASONS``                    Close reason for pull request closed with --close-pr; supported values: archived, inactive, obsolete, retest (type <type 'str'>)
``--dump-test-report=DUMP-TEST-REPORT``                    Dump test report to specified path (def test_report.md)                                                                         
``--from-pr=PR#``                                          Obtain easyconfigs from specified PR (type <type 'int'>)                                                                        
``--git-working-dirs-path=GIT-WORKING-DIRS-PATH``          Path to Git working directories for EasyBuild repositories (type <type 'str'>)                                                  
``--github-org=GITHUB-ORG``                                GitHub organization (type <type 'str'>)                                                                                         
``--github-user=GITHUB-USER``                              GitHub username (type <type 'str'>)                                                                                             
``--install-github-token``                                 Install GitHub token (requires --github-user) (def False)                                                                       
``--list-prs=STATE,ORDER,DIRECTION``                       List pull requests (type <type 'str'>; def open,created,desc)                                                                   
``--merge-pr=PR#``                                         Merge pull request (type <type 'int'>)                                                                                          
``--new-branch-github``                                    Create new branch in GitHub in preparation for a PR (def False)                                                                 
``--new-pr``                                               Open a new pull request (def False)                                                                                             
``--new-pr-from-branch=NEW-PR-FROM-BRANCH``                Open a new pull request from branch in GitHub (type <type 'str'>)                                                               
``--pr-branch-name=PR-BRANCH-NAME``                        Branch name to use for new PRs; '<timestamp>_new_pr_<name><version>' if unspecified (type <type 'str'>)                         
``--pr-commit-msg=PR-COMMIT-MSG``                          Commit message for new/updated pull request created with --new-pr (type <type 'str'>)                                           
``--pr-descr=PR-DESCR``                                    Description for new pull request created with --new-pr (type <type 'str'>)                                                      
``--pr-target-account=PR-TARGET-ACCOUNT``                  Target account for new PRs (type <type 'str'>; def easybuilders)                                                                
``--pr-target-branch=PR-TARGET-BRANCH``                    Target branch for new PRs (type <type 'str'>; def develop)                                                                      
``--pr-target-repo=PR-TARGET-REPO``                        Target repository for new/updating PRs (type <type 'str'>; def easybuild-easyconfigs)                                           
``--pr-title=PR-TITLE``                                    Title for new pull request created with --new-pr (type <type 'str'>)                                                            
``--preview-pr``                                           Preview a new pull request (def False)                                                                                          
``--review-pr=PR#``                                        Review specified pull request (type <type 'int'>)                                                                               
``--sync-branch-with-develop=SYNC-BRANCH-WITH-DEVELOP``    Sync branch with current 'develop' branch (type <type 'str'>)                                                                   
``--sync-pr-with-develop=PR#``                             Sync pull request with current 'develop' branch (type <type 'int'>)                                                             
``--test-report-env-filter=TEST-REPORT-ENV-FILTER``        Regex used to filter out variables in environment dump of test report                                                           
``--update-branch-github=UPDATE-BRANCH-GITHUB``            Update specified branch in GitHub (type <type 'str'>)                                                                           
``--update-pr=PR#``                                        Update an existing pull request (type <type 'int'>)                                                                             
``-u, --upload-test-report``                               Upload full test report as a gist on GitHub (def False)                                                                         
=======================================================    ================================================================================================================================


Informative options
-------------------
=====================================================    ===========================================================================================
Option flag                                              Option description                                                                         
=====================================================    ===========================================================================================
``--avail-cfgfile-constants``                            Show all constants that can be used in configuration files (def False)                     
``--avail-easyconfig-constants``                         Show all constants that can be used in easyconfigs (def False)                             
``--avail-easyconfig-licenses``                          Show all license constants that can be used in easyconfigs (def False)                     
``-a, --avail-easyconfig-params``                        Show all easyconfig parameters (include easyblock-specific ones by using -e) (def False)   
``--avail-easyconfig-templates``                         Show all template names and template constants that can be used in easyconfigs. (def False)
``--avail-hooks``                                        Show list of known hooks (def False)                                                       
``--avail-toolchain-opts=AVAIL-TOOLCHAIN-OPTS``          Show options for toolchain (type str)                                                      
``--check-conflicts``                                    Check for version conflicts in dependency graphs (def False)                               
``--dep-graph=depgraph.<ext>``                           Create dependency graph                                                                    
``--dump-env-script``                                    Dump source script to set up build environment based on toolchain/dependencies (def False) 
``--last-log``                                           Print location to EasyBuild log file of last (failed) session (def False)                  
``--list-easyblocks=LIST-EASYBLOCKS``                    Show list of available easyblocks (type choice; def simple) (choices: simple, detailed)    
``--list-installed-software=LIST-INSTALLED-SOFTWARE``    Show list of installed software (type choice; def simple) (choices: simple, detailed)      
``--list-software=LIST-SOFTWARE``                        Show list of supported software (type choice; def simple) (choices: simple, detailed)      
``--list-toolchains``                                    Show list of known toolchains (def False)                                                  
``--search=REGEX``                                       Search for easyconfig files in the robot search path, print full paths                     
``--search-filename=REGEX``                              Search for easyconfig files in the robot search path, print only filenames                 
``-S REGEX, --search-short=REGEX``                       Search for easyconfig files in the robot search path, print short paths                    
``--show-config``                                        Show current EasyBuild configuration (only non-default + selected settings) (def False)    
``--show-default-configfiles``                           Show list of default config files (def False)                                              
``--show-default-moduleclasses``                         Show default module classes with description (def False)                                   
``--show-full-config``                                   Show current EasyBuild configuration (all settings) (def False)                            
``--show-system-info``                                   Show system information relevant to EasyBuild (def False)                                  
``--terse``                                              Terse output (machine-readable) (def False)                                                
=====================================================    ===========================================================================================


Options for job backend
-----------------------
===========================================    ===========================================================================================================================
Option flag                                    Option description                                                                                                         
===========================================    ===========================================================================================================================
``--job-backend-config=BACKEND-CONFIG``        Configuration file for job backend                                                                                         
``--job-cores=CORES``                          Number of cores to request per job (type int)                                                                              
``--job-deps-type=DEPS-TYPE``                  Type of dependency to set between jobs (default depends on job backend) (type choice) (choices: abort_on_error, always_run)
``--job-max-jobs=MAX-JOBS``                    Maximum number of concurrent jobs (queued and running, 0 = unlimited) (type int; def 0)                                    
``--job-max-walltime=MAX-WALLTIME``            Maximum walltime for jobs (in hours) (type int; def 24)                                                                    
``--job-output-dir=OUTPUT-DIR``                Output directory for jobs (default: current directory) (def /home/example/develop/easybuild/docs)                       
``--job-polling-interval=POLLING-INTERVAL``    Interval between polls for status of jobs (in seconds) (type <type 'float'>; def 30.0)                                     
``--job-target-resource=TARGET-RESOURCE``      Target resource for jobs                                                                                                   
===========================================    ===========================================================================================================================


Override options
----------------
=========================================================================    ==================================================================================================================================================================================
Option flag                                                                  Option description                                                                                                                                                                
=========================================================================    ==================================================================================================================================================================================
``--add-dummy-to-minimal-toolchains``                                        Include dummy toolchain in minimal toolchain searches [DEPRECATED, use --add-system-to-minimal-toolchains instead!) (def False)                                                   
``--add-system-to-minimal-toolchains``                                       Include system toolchain in minimal toolchain searches (def False)                                                                                                                
``--allow-loaded-modules=ALLOW-LOADED-MODULES``                              List of software names for which to allow loaded modules in initial environment (type comma-separated list; def EasyBuild)                                                        
``--allow-modules-tool-mismatch``                                            Allow mismatch of modules tool and definition of 'module' function (def False)                                                                                                    
``--allow-use-as-root-and-accept-consequences``                              Allow using of EasyBuild as root (NOT RECOMMENDED!) (def False)                                                                                                                   
``--backup-modules``                                                         Back up an existing module file, if any. Only works when using --module-only                                                                                                      
``--check-ebroot-env-vars=CHECK-EBROOT-ENV-VARS``                            Action to take when defined $EBROOT* environment variables are found for which there is no matching loaded module; supported values: error, ignore, unset, warn (def warn)        
``--cleanup-builddir``                                                       Cleanup build dir after successful installation. (def True)                                                                                                                       
``--cleanup-tmpdir``                                                         Cleanup tmp dir after successful run. (def True)                                                                                                                                  
``--color=WHEN``                                                             Colorize output (type choice; def auto) (choices: auto, always, never)                                                                                                            
``--consider-archived-easyconfigs``                                          Also consider archived easyconfigs (def False)                                                                                                                                    
``-C, --containerize``                                                       Generate container recipe/image (def False)                                                                                                                                       
``--debug-lmod``                                                             Run Lmod modules tool commands in debug module (def False)                                                                                                                        
``--default-opt-level=DEFAULT-OPT-LEVEL``                                    Specify default optimisation level (type choice; def defaultopt) (choices: noopt, lowopt, defaultopt, opt)                                                                        
``--deprecated=DEPRECATED``                                                  Run pretending to be (future) version, to test removal of deprecated code.                                                                                                        
``--detect-loaded-modules=DETECT-LOADED-MODULES``                            Detect loaded EasyBuild-generated modules, act accordingly; supported values: error, ignore, purge, unload, warn (def warn)                                                       
``--devel``                                                                  Enable including of development log messages (def False)                                                                                                                          
``--download-timeout=DOWNLOAD-TIMEOUT``                                      Timeout for initiating downloads (in seconds) (type <type 'float'>)                                                                                                               
``--dump-autopep8``                                                          Reformat easyconfigs using autopep8 when dumping them (def False)                                                                                                                 
``-e CLASS, --easyblock=CLASS``                                              easyblock to use for processing the spec file or dumping the options                                                                                                              
``--enforce-checksums``                                                      Enforce availability of checksums for all sources/patches, so they can be verified (def False)                                                                                    
``--experimental``                                                           Allow experimental code (with behaviour that can be changed/removed at any given time). (def False)                                                                               
``--extra-modules=EXTRA-MODULES``                                            List of extra modules to load after setting up the build environment (type comma-separated list)                                                                                  
``--fetch``                                                                  Allow downloading sources ignoring OS and modules tool dependencies, implies --stop=fetch, --ignore-osdeps and ignore modules tool (def False)                                    
``--filter-deps=FILTER-DEPS``                                                List of dependencies that you do *not* want to install with EasyBuild, because equivalent OS packages are installed. (e.g. --filter-deps=zlib,ncurses) (type comma-separated list)
``--filter-env-vars=FILTER-ENV-VARS``                                        List of names of environment variables that should *not* be defined/updated by module files generated by EasyBuild (type comma-separated list)                                    
``--fixed-installdir-naming-scheme``                                         Use fixed naming scheme for installation directories (def True)                                                                                                                   
``--force-download=FORCE-DOWNLOAD``                                          Force re-downloading of sources and/or patches, even if they are available already in source path (type choice; def sources) (choices: all, patches, sources)                     
``--group=GROUP``                                                            Group to be used for software installations (only verified, not set)                                                                                                              
``--group-writable-installdir``                                              Enable group write permissions on installation directory after installation (def False)                                                                                           
``--hidden``                                                                 Install 'hidden' module file(s) by prefixing their version with '.' (def False)                                                                                                   
``--hide-deps=HIDE-DEPS``                                                    Comma separated list of dependencies that you want automatically hidden, (e.g. --hide-deps=zlib,ncurses) (type comma-separated list)                                              
``--hide-toolchains=HIDE-TOOLCHAINS``                                        Comma separated list of toolchains that you want automatically hidden, (e.g. --hide-toolchains=GCCcore) (type comma-separated list)                                               
``--ignore-checksums``                                                       Ignore failing checksum verification (def False)                                                                                                                                  
``--ignore-osdeps``                                                          Ignore any listed OS dependencies (def False)                                                                                                                                     
``--install-latest-eb-release``                                              Install latest known version of easybuild (def False)                                                                                                                             
``--lib64-fallback-sanity-check``                                            Fallback in sanity check to lib64/ equivalent for missing libraries (def True)                                                                                                    
``--max-fail-ratio-adjust-permissions=MAX-FAIL-RATIO-ADJUST-PERMISSIONS``    Maximum ratio for failures to allow when adjusting permissions (type float; def 0.5)                                                                                              
``--minimal-toolchains``                                                     Use minimal toolchain when resolving dependencies (def False)                                                                                                                     
``--module-only``                                                            Only generate module file(s); skip all steps except for module, prepare, ready, postiter, sanitycheck (def False)                                                                 
``--modules-tool-version-check``                                             Check version of modules tool being used (def True)                                                                                                                               
``--mpi-cmd-template=MPI-CMD-TEMPLATE``                                      Template for MPI commands (template keys: %(nr_ranks)s, %(cmd)s)                                                                                                                  
``--mpi-tests``                                                              Run MPI tests (when relevant) (def True)                                                                                                                                          
``--optarch=OPTARCH``                                                        Set architecture optimization, overriding native architecture optimizations                                                                                                       
``--output-format=OUTPUT-FORMAT``                                            Set output format (type choice; def txt) (choices: txt, rst)                                                                                                                      
``--parallel=PARALLEL``                                                      Specify (maximum) level of parallellism used during build procedure (type int)                                                                                                    
``--pre-create-installdir``                                                  Create installation directory before submitting build jobs (def True)                                                                                                             
``-p, --pretend``                                                            Does the build/installation in a test directory located in $HOME/easybuildinstall (def False)                                                                                     
``--read-only-installdir``                                                   Set read-only permissions on installation directory after installation (def False)                                                                                                
``--remove-ghost-install-dirs``                                              Remove ghost installation directories when --force or --rebuild is used, rather than just warning about them (def False)                                                          
``--rpath``                                                                  Enable use of RPATH for linking with libraries (def False)                                                                                                                        
``--rpath-filter=RPATH-FILTER``                                              List of regex patterns to use for filtering out RPATH paths (type comma-separated list)                                                                                           
``--set-default-module``                                                     Set the generated module as default (def False)                                                                                                                                   
``--set-gid-bit``                                                            Set group ID bit on newly created directories (def False)                                                                                                                         
``--silence-deprecation-warnings=SILENCE-DEPRECATION-WARNINGS``              Silence specified deprecation warnings (type comma-separated list)                                                                                                                
``-t, --skip-test-cases``                                                    Skip running test cases (def False)                                                                                                                                               
``--sticky-bit``                                                             Set sticky bit on newly created directories (def False)                                                                                                                           
``-T, --trace``                                                              Provide more information in output to stdout on progress (def False)                                                                                                              
``--umask=UMASK``                                                            umask to use (e.g. '022'); non-user write permissions on install directories are removed                                                                                          
``--update-modules-tool-cache``                                              Update modules tool cache file(s) after generating module file (def False)                                                                                                        
``--use-ccache=PATH``                                                        Enable use of ccache to speed up compilation, with specified cache dir (type <type 'str'>; def False)                                                                             
``--use-existing-modules``                                                   Use existing modules when resolving dependencies with minimal toolchains (def False)                                                                                              
``--use-f90cache=PATH``                                                      Enable use of f90cache to speed up compilation, with specified cache dir (type <type 'str'>; def False)                                                                           
``--verify-easyconfig-filenames``                                            Verify whether filename of specified easyconfigs matches with contents (def False)                                                                                                
``--zip-logs=ZIP-LOGS``                                                      Zip logs that are copied to install directory, using specified command (def gzip)                                                                                                 
=========================================================================    ==================================================================================================================================================================================


Package options
---------------
===============================================    =========================================
Option flag                                        Option description                       
===============================================    =========================================
``--package``                                      Enabling packaging (def False)           
``--package-release=PACKAGE-RELEASE``              Package release iteration number (def 1) 
``--package-tool=PACKAGE-TOOL``                    Packaging tool to use (def fpm)          
``--package-tool-options=PACKAGE-TOOL-OPTIONS``    Extra options for packaging tool (def '')
``--package-type=PACKAGE-TYPE``                    Type of package to generate (def rpm)    
===============================================    =========================================


Regression test options
-----------------------
============================    ==========================================================================
Option flag                     Option description                                                        
============================    ==========================================================================
``--aggregate-regtest=DIR``     Collect all the xmls inside the given directory and generate a single file
``--regtest``                   Enable regression test mode (def False)                                   
``--regtest-output-dir=DIR``    Set output directory for test-run                                         
``--sequential``                Specify this option if you want to prevent parallel build (def False)     
============================    ==========================================================================


Software search and build options
---------------------------------
===================================    ===================================================================================================================================================================
Option flag                            Option description                                                                                                                                                 
===================================    ===================================================================================================================================================================
``--amend=VAR=VALUE[,VALUE]``          Specify additional search and build parameters (can be used multiple times); for example: versionprefix=foo or patches=one.patch,two.patch)                        
``--map-toolchains``                   Enable mapping of (sub)toolchains when --try-toolchain(-version) is used (def True)                                                                                
``--software=NAME,VERSION``            Search and build software with given name and version (type comma-separated list)                                                                                  
``--software-name=NAME``               Search and build software with given name                                                                                                                          
``--software-version=VERSION``         Search and build software with given version                                                                                                                       
``--toolchain=NAME,VERSION``           Search and build with given toolchain (name and version) (type comma-separated list)                                                                               
``--toolchain-name=NAME``              Search and build with given toolchain name                                                                                                                         
``--toolchain-version=VERSION``        Search and build with given toolchain version                                                                                                                      
``--try-amend=VAR=VALUE[,VALUE]``      Try to specify additional search and build parameters (can be used multiple times); for example: versionprefix=foo or patches=one.patch,two.patch) (USE WITH CARE!)
``--try-software=NAME,VERSION``        Try to search and build software with given name and version (USE WITH CARE!) (type comma-separated list)                                                          
``--try-software-name=NAME``           Try to search and build software with given name (USE WITH CARE!)                                                                                                  
``--try-software-version=VERSION``     Try to search and build software with given version (USE WITH CARE!)                                                                                               
``--try-toolchain=NAME,VERSION``       Try to search and build with given toolchain (name and version) (USE WITH CARE!) (type comma-separated list)                                                       
``--try-toolchain-name=NAME``          Try to search and build with given toolchain name (USE WITH CARE!)                                                                                                 
``--try-toolchain-version=VERSION``    Try to search and build with given toolchain version (USE WITH CARE!)                                                                                              
===================================    ===================================================================================================================================================================


Unittest options
----------------
========================    =================================
Option flag                 Option description               
========================    =================================
``--unittest-file=FILE``    Log to this file in unittest mode
========================    =================================

