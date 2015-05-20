# Package End of Life Policy

Creation Date: 3 March, 2015.<br />
Last Edit Date: 14 May, 2015.

The Bioconductor project strives to provide a software repository that is stable
and relevant to users across the community. Each year 100-150 new software
packages are added to the repository; as of Spring 2015 over 1000 packages are
hosted. The Bioconductor build system builds and checks each software package
every 24 hours. Regular execution of example, vignette and unit test code
ensures the package is operating as expected and all required dependencies are
available. The
[build system](http://www.bioconductor.org/checkResults/devel/bioc-LATEST/)
provides a detailed report for each package across three platforms: Linux, 
Windows and Mac.

In an effort to maintain a high quality repository we have adopted a
one-year end of life (EOL) process for packages that no longer pass
build or check and do not have an active maintainer. Packages are
assessed for EOL deprecation prior to each Bioconductor release; the
EOL policies apply to software, annotation, and experiment data
packages.

## Required criteria to avoid package removal

1. Error-free R CMD build and check on all platforms

   The package must build and check without error on all platforms
   (exceptions to cross-platform builds are available under limited
   circumstances) at each Bioconductor release. All efforts will be
   made to keep a package in the repository if the maintainer is
   actively attempting a fix.

2. Active maintainer 

   The maintainer listed in the DESCRIPTION file must be responsive to
   questions on the support site, package-related email from users and
   Bioconductor team members, package-related errors in the build
   system, and requests for bug fixes.

## End of Life process

**Step I**: Deprecation (1 release cycle)

Packages that fail to meet requirements outlined in the previous
section will be marked with a deprecation warning. The message is
emitted when the package is loaded, and is reported on the package
'landing page'. The message alerts users that the package currently
fails the minimal build and check criteria, and that the package will
likely be removed from Bioconductor in the next release.

If at any time in this 6 month period the required criteria are met
(e.g., the package returns to active maintenance, perhaps by a third
party) the warning is removed.

**Step II**: Defunct (subsequent release cycles)

When a package has gone through one development cycle as 'deprecated'
without remedial action, the package is marked as 'Defunct'. The
package is removed from the nightly build system, is no longer
available through 'biocLite()', and does not have a current 'landing
page'. 

The package remains available in the subversion archive, and in
previous versions of Bioconductor.

Defunct packages cannot re-enter the Bioconductor repository except
through review as a 'new package'.

**Example**:

      devel  --|------|---
             ^      ^ 
             Depr   Defunct
    
    release  --|------|---
                ^      ^
                Depr   Defunct

- Immediately prior to Bioconductor release 3.2 -- 'devel' package
  fails to meet required criteria. Marked as 'Deprecated' in the
  devel branch prior to the release, and consequently are marked as
  'Deprecated' in the release (3.3) and subsequent devel branches.

- Immediately before Bioconductor release 3.3 -- 'devel' packages are
  marked as 'Defunct', and removed from the 3.3 release manifest.