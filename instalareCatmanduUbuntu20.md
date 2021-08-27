XML::ParserXML::Parser## Instalare locală Ubuntu

Mai întâi de toate, asigură-te că ai instalat `carton`.

```bash
sudo apt install carton
```

Horror

```text
Installing modules using /home/nicolaie/Documents/SCOALA.DE.VARA.ASTRA/SET.DATE.CATALOG.ASTRA/LibreCat/cpanfile
! Installing Gearman::XS failed. See /home/nicolaie/.cpanm/work/1629223070.105268/build.log for details. Retry with --force to force install it.
! Configure failed for XML-LibXSLT-1.99. See /home/nicolaie/.cpanm/work/1629223070.105268/build.log for details.
! Installing the dependencies failed: Module 'XML::LibXSLT' is not installed
! Bailing out the installation for Catmandu-XML-0.16.
! Installing the dependencies failed: Module 'Catmandu::XML' is not installed
! Bailing out the installation for Catmandu-OAI-0.19.
! Installing the dependencies failed: Module 'Catmandu::XML' is not installed, Module 'XML::LibXSLT' is not installed
! Bailing out the installation for Catmandu-ArXiv-0.212.
! Configure failed for DBD-mysql-4.050. See /home/nicolaie/.cpanm/work/1629223070.105268/build.log for details.
! Installing the dependencies failed: Module 'Catmandu::OAI' is not installed, Module 'Catmandu::XML' is not installed, Module 'Catmandu::ArXiv' is not installed, Module 'DBD::mysql' is not installed, Module 'Gearman::XS' is not installed
! Bailing out the installation for /home/nicolaie/Documents/SCOALA.DE.VARA.ASTRA/SET.DATE.CATALOG.ASTRA/LibreCat/.
Installing modules failed
```

Am executat: `cpan Test::More`.

Rezultat:

```text
Warning: You do not have write permission for Perl library directories.

To install modules, you need to configure a local Perl library directory or
escalate your privileges.  CPAN can help you by bootstrapping the local::lib
module or by configuring itself to use 'sudo' (if available).  You may also
resolve this problem manually if you need to customize your setup.

What approach do you want?  (Choose 'local::lib', 'sudo' or 'manual')
 [local::lib]
Attempting to create directory /home/nicolaie/perl5
Checking if your kit is complete...
Looks good
```

Am executat: `sudo cpan YAML`. Apoi am rulat: `sudo cpan App::cpanminus`. Apoi am executat: `cpanm Catmandu Catmandu::MARC`. Ca efect se vor instala pachetele necesare printre care și cele nucleu:

```text
Building and testing Catmandu-1.2015 ... OK
Successfully installed Catmandu-1.2015
--> Working on Catmandu::MARC
Fetching http://www.cpan.org/authors/id/H/HO/HOCHSTEN/Catmandu-MARC-1.254.tar.gz ... OK
Configuring Catmandu-MARC-1.254 ... OK
==> Found dependencies: MARC::File::MiJ, MARC::Parser::RAW, MARC::Spec, MARC::File::XML, MARC::Lint, MARC::Record, XML::LibXML, XML::XPath, MARC::File::MARCMaker, MARC::Schema, MooX::Singleton`

...


Building and testing MARC-File-XML-v1.0.5 ... FAIL
! Installing MARC::File::XML failed. See /home/nicolaie/.cpanm/work/1629226383.143397/build.log for details. Retry with --force to force install it.

...

Building and testing MARC-File-XML-v1.0.5 ... FAIL
! Installing MARC::File::XML failed. See /home/nicolaie/.cpanm/work/1629226940.165839/build.log for details. Retry with --force to force install it.
! Installing the dependencies failed: Module 'MARC::File::XML' is not installed
! Bailing out the installation for Catmandu-MARC-1.254.
```

La apariția erorii, am urmat recomandarea de a instala cu `--force`.

```bash
cpanm Catmandu Catmandu::MARC --force
```

Cu următorul rezultat:

```text
!
! Can't write to /usr/local/share/perl/5.30.0 and /usr/local/bin: Installing modules to /home/nicolaie/perl5
! To turn off this warning, you have to do one of the following:
!   - run me as a root or with --sudo option (to install to /usr/local/share/perl/5.30.0 and /usr/local/bin)
!   - Configure local::lib in your existing shell to set PERL_MM_OPT etc.
!   - Install local::lib by running the following commands
!
!         cpanm --local-lib=~/perl5 local::lib && eval $(perl -I ~/perl5/lib/perl5/ -Mlocal::lib)
!
--> Working on Catmandu
Fetching http://www.cpan.org/authors/id/N/NI/NICS/Catmandu-1.2015.tar.gz ... OK
Configuring Catmandu-1.2015 ... OK
Building and testing Catmandu-1.2015 ... OK
Successfully reinstalled Catmandu-1.2015
--> Working on Catmandu::MARC
Fetching http://www.cpan.org/authors/id/H/HO/HOCHSTEN/Catmandu-MARC-1.254.tar.gz ... OK
Configuring Catmandu-MARC-1.254 ... OK
==> Found dependencies: MARC::File::XML
--> Working on MARC::File::XML
Fetching http://www.cpan.org/authors/id/G/GM/GMCHARLT/MARC-File-XML-1.0.5.tar.gz ... OK
Configuring MARC-File-XML-v1.0.5 ... OK
Building and testing MARC-File-XML-v1.0.5 ... FAIL
! Testing MARC-File-XML-v1.0.5 failed but installing it anyway.
Successfully installed MARC-File-XML-v1.0.5
Building and testing Catmandu-MARC-1.254 ... OK
Successfully installed Catmandu-MARC-1.254
3 distributions installed
```

Am instalat cu sudo.

```bash
sudo cpanm Catmandu Catmandu::MARC
--> Working on Catmandu
Fetching http://www.cpan.org/authors/id/N/NI/NICS/Catmandu-1.2015.tar.gz ... OK
Configuring Catmandu-1.2015 ... OK
==> Found dependencies: UUID::Tiny, App::Cmd, Try::Tiny::ByClass, Module::Info, Log::Log4perl, String::CamelCase, Hash::Merge::Simple, Cpanel::JSON::XS, Test::Pod, Log::Any::Test, Clone, YAML::XS, Test::LWP::UserAgent, Data::Compare, Log::Any, Log::Any::Adapter::Log4perl, MIME::Types, Text::Hogan::Compiler, Log::Any::Adapter, Throwable, URI::Template, Parser::MGC, Data::Util, asa, Text::CSV, Test::Exception, MooX::Aliases, CGI::Expand, Path::Iterator::Rule, Config::Onion, IO::Handle::Util
--> Working on UUID::Tiny
Fetching http://www.cpan.org/authors/id/C/CA/CAUGUSTIN/UUID-Tiny-1.04.tar.gz ... OK
Configuring UUID-Tiny-1.04 ... OK
Building and testing UUID-Tiny-1.04 ... OK
Successfully installed UUID-Tiny-1.04
--> Working on App::Cmd
Fetching http://www.cpan.org/authors/id/R/RJ/RJBS/App-Cmd-0.334.tar.gz ... OK
Configuring App-Cmd-0.334 ... OK
==> Found dependencies: Test::Fatal, String::RewritePrefix, Module::Pluggable::Object, Class::Load, IO::TieCombine
--> Working on Test::Fatal
Fetching http://www.cpan.org/authors/id/R/RJ/RJBS/Test-Fatal-0.016.tar.gz ... OK
Configuring Test-Fatal-0.016 ... OK
Building and testing Test-Fatal-0.016 ... OK
Successfully installed Test-Fatal-0.016
--> Working on String::RewritePrefix
Fetching http://www.cpan.org/authors/id/R/RJ/RJBS/String-RewritePrefix-0.008.tar.gz ... OK
Configuring String-RewritePrefix-0.008 ... OK
Building and testing String-RewritePrefix-0.008 ... OK
Successfully installed String-RewritePrefix-0.008
--> Working on Module::Pluggable::Object
Fetching http://www.cpan.org/authors/id/S/SI/SIMONW/Module-Pluggable-5.2.tar.gz ... OK
Configuring Module-Pluggable-5.2 ... OK
Building and testing Module-Pluggable-5.2 ... OK
Successfully installed Module-Pluggable-5.2
--> Working on Class::Load
Fetching http://www.cpan.org/authors/id/E/ET/ETHER/Class-Load-0.25.tar.gz ... OK
Configuring Class-Load-0.25 ... OK
==> Found dependencies: Test::Needs
--> Working on Test::Needs
Fetching http://www.cpan.org/authors/id/H/HA/HAARG/Test-Needs-0.002009.tar.gz ... OK
Configuring Test-Needs-0.002009 ... OK
Building and testing Test-Needs-0.002009 ... OK
Successfully installed Test-Needs-0.002009
Building and testing Class-Load-0.25 ... OK
Successfully installed Class-Load-0.25
--> Working on IO::TieCombine
Fetching http://www.cpan.org/authors/id/R/RJ/RJBS/IO-TieCombine-1.005.tar.gz ... OK
Configuring IO-TieCombine-1.005 ... OK
Building and testing IO-TieCombine-1.005 ... OK
Successfully installed IO-TieCombine-1.005
Building and testing App-Cmd-0.334 ... OK
Successfully installed App-Cmd-0.334
--> Working on Try::Tiny::ByClass
Fetching http://www.cpan.org/authors/id/M/MA/MAUKE/Try-Tiny-ByClass-0.01.tar.gz ... OK
Configuring Try-Tiny-ByClass-0.01 ... OK
==> Found dependencies: Dispatch::Class
--> Working on Dispatch::Class
Fetching http://www.cpan.org/authors/id/M/MA/MAUKE/Dispatch-Class-0.02.tar.gz ... OK
Configuring Dispatch-Class-0.02 ... OK
Building and testing Dispatch-Class-0.02 ... OK
Successfully installed Dispatch-Class-0.02
Building and testing Try-Tiny-ByClass-0.01 ... OK
Successfully installed Try-Tiny-ByClass-0.01
--> Working on Module::Info
Fetching http://www.cpan.org/authors/id/N/NE/NEILB/Module-Info-0.37.tar.gz ... OK
Configuring Module-Info-0.37 ... OK
==> Found dependencies: B::Utils
--> Working on B::Utils
Fetching http://www.cpan.org/authors/id/E/ET/ETHER/B-Utils-0.27.tar.gz ... OK
Configuring B-Utils-0.27 ... OK
==> Found dependencies: Task::Weaken
--> Working on Task::Weaken
Fetching http://www.cpan.org/authors/id/E/ET/ETHER/Task-Weaken-1.06.tar.gz ... OK
Configuring Task-Weaken-1.06 ... OK
Building and testing Task-Weaken-1.06 ... OK
Successfully installed Task-Weaken-1.06
Building and testing B-Utils-0.27 ... OK
Successfully installed B-Utils-0.27
Building and testing Module-Info-0.37 ... OK
Successfully installed Module-Info-0.37
--> Working on Log::Log4perl
Fetching http://www.cpan.org/authors/id/E/ET/ETJ/Log-Log4perl-1.54.tar.gz ... OK
Configuring Log-Log4perl-1.54 ... OK
Building and testing Log-Log4perl-1.54 ... OK
Successfully installed Log-Log4perl-1.54
--> Working on String::CamelCase
Fetching http://www.cpan.org/authors/id/H/HI/HIO/String-CamelCase-0.04.tar.gz ... OK
Configuring String-CamelCase-0.04 ... OK
Building and testing String-CamelCase-0.04 ... OK
Successfully installed String-CamelCase-0.04
--> Working on Hash::Merge::Simple
Fetching http://www.cpan.org/authors/id/R/RO/ROKR/Hash-Merge-Simple-0.051.tar.gz ... OK
Configuring Hash-Merge-Simple-0.051 ... OK
==> Found dependencies: Clone, Test::Most
--> Working on Clone
Fetching http://www.cpan.org/authors/id/A/AT/ATOOMIC/Clone-0.45.tar.gz ... OK
Configuring Clone-0.45 ... OK
==> Found dependencies: B::COW
--> Working on B::COW
Fetching http://www.cpan.org/authors/id/A/AT/ATOOMIC/B-COW-0.004.tar.gz ... OK
Configuring B-COW-0.004 ... OK
Building and testing B-COW-0.004 ... OK
Successfully installed B-COW-0.004
Building and testing Clone-0.45 ... OK
Successfully installed Clone-0.45
--> Working on Test::Most
Fetching http://www.cpan.org/authors/id/O/OV/OVID/Test-Most-0.37.tar.gz ... OK
Configuring Test-Most-0.37 ... OK
==> Found dependencies: Test::Warn, Test::Exception, Exception::Class, Test::Differences
--> Working on Test::Warn
Fetching http://www.cpan.org/authors/id/B/BI/BIGJ/Test-Warn-0.36.tar.gz ... OK
Configuring Test-Warn-0.36 ... OK
==> Found dependencies: Sub::Uplevel
--> Working on Sub::Uplevel
Fetching http://www.cpan.org/authors/id/D/DA/DAGOLDEN/Sub-Uplevel-0.2800.tar.gz ... OK
Configuring Sub-Uplevel-0.2800 ... OK
Building and testing Sub-Uplevel-0.2800 ... OK
Successfully installed Sub-Uplevel-0.2800
Building and testing Test-Warn-0.36 ... OK
Successfully installed Test-Warn-0.36
--> Working on Test::Exception
Fetching http://www.cpan.org/authors/id/E/EX/EXODIST/Test-Exception-0.43.tar.gz ... OK
Configuring Test-Exception-0.43 ... OK
Building and testing Test-Exception-0.43 ... OK
Successfully installed Test-Exception-0.43
--> Working on Exception::Class
Fetching http://www.cpan.org/authors/id/D/DR/DROLSKY/Exception-Class-1.45.tar.gz ... OK
Configuring Exception-Class-1.45 ... OK
==> Found dependencies: Class::Data::Inheritable, Devel::StackTrace
--> Working on Class::Data::Inheritable
Fetching http://www.cpan.org/authors/id/R/RS/RSHERER/Class-Data-Inheritable-0.09.tar.gz ... OK
Configuring Class-Data-Inheritable-0.09 ... OK
Building and testing Class-Data-Inheritable-0.09 ... OK
Successfully installed Class-Data-Inheritable-0.09
--> Working on Devel::StackTrace
Fetching http://www.cpan.org/authors/id/D/DR/DROLSKY/Devel-StackTrace-2.04.tar.gz ... OK
Configuring Devel-StackTrace-2.04 ... OK
Building and testing Devel-StackTrace-2.04 ... OK
Successfully installed Devel-StackTrace-2.04
Building and testing Exception-Class-1.45 ... OK
Successfully installed Exception-Class-1.45
--> Working on Test::Differences
Fetching http://www.cpan.org/authors/id/D/DC/DCANTRELL/Test-Differences-0.68.tar.gz ... OK
Configuring Test-Differences-0.68 ... OK
Building and testing Test-Differences-0.68 ... OK
Successfully installed Test-Differences-0.68
Building and testing Test-Most-0.37 ... OK
Successfully installed Test-Most-0.37
Building and testing Hash-Merge-Simple-0.051 ... OK
Successfully installed Hash-Merge-Simple-0.051
--> Working on Cpanel::JSON::XS
Fetching http://www.cpan.org/authors/id/R/RU/RURBAN/Cpanel-JSON-XS-4.26.tar.gz ... OK
Configuring Cpanel-JSON-XS-4.26 ... OK
Building and testing Cpanel-JSON-XS-4.26 ... OK
Successfully installed Cpanel-JSON-XS-4.26
--> Working on Test::Pod
Fetching http://www.cpan.org/authors/id/E/ET/ETHER/Test-Pod-1.52.tar.gz ... OK
Configuring Test-Pod-1.52 ... OK
Building and testing Test-Pod-1.52 ... OK
Successfully installed Test-Pod-1.52
--> Working on Log::Any::Test
Fetching http://www.cpan.org/authors/id/P/PR/PREACTION/Log-Any-1.710.tar.gz ... OK
Configuring Log-Any-1.710 ... OK
Building and testing Log-Any-1.710 ... OK
Successfully installed Log-Any-1.710
--> Working on YAML::XS
Fetching http://www.cpan.org/authors/id/T/TI/TINITA/YAML-LibYAML-0.83.tar.gz ... OK
Configuring YAML-LibYAML-0.83 ... OK
Building and testing YAML-LibYAML-0.83 ... OK
Successfully installed YAML-LibYAML-0.83
--> Working on Test::LWP::UserAgent
Fetching http://www.cpan.org/authors/id/E/ET/ETHER/Test-LWP-UserAgent-0.034.tar.gz ... OK
Configuring Test-LWP-UserAgent-0.034 ... OK
==> Found dependencies: Safe::Isa, Test::Warnings, Test::RequiresInternet
--> Working on Safe::Isa
Fetching http://www.cpan.org/authors/id/E/ET/ETHER/Safe-Isa-1.000010.tar.gz ... OK
Configuring Safe-Isa-1.000010 ... OK
Building and testing Safe-Isa-1.000010 ... OK
Successfully installed Safe-Isa-1.000010
--> Working on Test::Warnings
Fetching http://www.cpan.org/authors/id/E/ET/ETHER/Test-Warnings-0.031.tar.gz ... OK
Configuring Test-Warnings-0.031 ... OK
Building and testing Test-Warnings-0.031 ... OK
Successfully installed Test-Warnings-0.031
--> Working on Test::RequiresInternet
Fetching http://www.cpan.org/authors/id/M/MA/MALLEN/Test-RequiresInternet-0.05.tar.gz ... OK
Configuring Test-RequiresInternet-0.05 ... OK
Building and testing Test-RequiresInternet-0.05 ... OK
Successfully installed Test-RequiresInternet-0.05
Building and testing Test-LWP-UserAgent-0.034 ... OK
Successfully installed Test-LWP-UserAgent-0.034
--> Working on Data::Compare
Fetching http://www.cpan.org/authors/id/D/DC/DCANTRELL/Data-Compare-1.27.tar.gz ... OK
Configuring Data-Compare-1.27 ... OK
==> Found dependencies: File::Find::Rule
--> Working on File::Find::Rule
Fetching http://www.cpan.org/authors/id/R/RC/RCLAMP/File-Find-Rule-0.34.tar.gz ... OK
Configuring File-Find-Rule-0.34 ... OK
==> Found dependencies: Number::Compare, Text::Glob
--> Working on Number::Compare
Fetching http://www.cpan.org/authors/id/R/RC/RCLAMP/Number-Compare-0.03.tar.gz ... OK
Configuring Number-Compare-0.03 ... OK
Building and testing Number-Compare-0.03 ... OK
Successfully installed Number-Compare-0.03
--> Working on Text::Glob
Fetching http://www.cpan.org/authors/id/R/RC/RCLAMP/Text-Glob-0.11.tar.gz ... OK
Configuring Text-Glob-0.11 ... OK
Building and testing Text-Glob-0.11 ... OK
Successfully installed Text-Glob-0.11
Building and testing File-Find-Rule-0.34 ... OK
Successfully installed File-Find-Rule-0.34
Building and testing Data-Compare-1.27 ... OK
Successfully installed Data-Compare-1.27
--> Working on Log::Any::Adapter::Log4perl
Fetching http://www.cpan.org/authors/id/P/PR/PREACTION/Log-Any-Adapter-Log4perl-0.09.tar.gz ... OK
Configuring Log-Any-Adapter-Log4perl-0.09 ... OK
Building and testing Log-Any-Adapter-Log4perl-0.09 ... OK
Successfully installed Log-Any-Adapter-Log4perl-0.09
--> Working on MIME::Types
Fetching http://www.cpan.org/authors/id/M/MA/MARKOV/MIME-Types-2.21.tar.gz ... OK
Configuring MIME-Types-2.21 ... OK
Building and testing MIME-Types-2.21 ... OK
Successfully installed MIME-Types-2.21
--> Working on Text::Hogan::Compiler
Fetching http://www.cpan.org/authors/id/K/KA/KAORU/Text-Hogan-2.03.tar.gz ... OK
Configuring Text-Hogan-2.03 ... OK
==> Found dependencies: Data::Visitor::Callback, Text::Trim
--> Working on Data::Visitor::Callback
Fetching http://www.cpan.org/authors/id/E/ET/ETHER/Data-Visitor-0.31.tar.gz ... OK
Configuring Data-Visitor-0.31 ... OK
==> Found dependencies: Tie::ToObject, Moose
--> Working on Tie::ToObject
Fetching http://www.cpan.org/authors/id/N/NU/NUFFIN/Tie-ToObject-0.03.tar.gz ... OK
Configuring Tie-ToObject-0.03 ... OK
Building and testing Tie-ToObject-0.03 ... OK
Successfully installed Tie-ToObject-0.03
--> Working on Moose
Fetching http://www.cpan.org/authors/id/E/ET/ETHER/Moose-2.2015.tar.gz ... OK
==> Found dependencies: Dist::CheckConflicts
--> Working on Dist::CheckConflicts
Fetching http://www.cpan.org/authors/id/D/DO/DOY/Dist-CheckConflicts-0.11.tar.gz ... OK
Configuring Dist-CheckConflicts-0.11 ... OK
Building and testing Dist-CheckConflicts-0.11 ... OK
Successfully installed Dist-CheckConflicts-0.11
Configuring Moose-2.2015 ... OK
==> Found dependencies: Eval::Closure, Devel::GlobalDestruction, Devel::OverloadInfo, Test::Requires, Class::Load::XS, Package::DeprecationManager, List::Util, Test::CleanNamespaces, Module::Runtime::Conflicts
--> Working on Eval::Closure
Fetching http://www.cpan.org/authors/id/D/DO/DOY/Eval-Closure-0.14.tar.gz ... OK
Configuring Eval-Closure-0.14 ... OK
==> Found dependencies: Test::Requires
--> Working on Test::Requires
Fetching http://www.cpan.org/authors/id/T/TO/TOKUHIROM/Test-Requires-0.11.tar.gz ... OK
Configuring Test-Requires-0.11 ... OK
Building and testing Test-Requires-0.11 ... OK
Successfully installed Test-Requires-0.11
Building and testing Eval-Closure-0.14 ... OK
Successfully installed Eval-Closure-0.14
--> Working on Devel::GlobalDestruction
Fetching http://www.cpan.org/authors/id/H/HA/HAARG/Devel-GlobalDestruction-0.14.tar.gz ... OK
Configuring Devel-GlobalDestruction-0.14 ... OK
Building and testing Devel-GlobalDestruction-0.14 ... OK
Successfully installed Devel-GlobalDestruction-0.14
--> Working on Devel::OverloadInfo
Fetching http://www.cpan.org/authors/id/I/IL/ILMARI/Devel-OverloadInfo-0.007.tar.gz ... OK
Configuring Devel-OverloadInfo-0.007 ... OK
Building and testing Devel-OverloadInfo-0.007 ... OK
Successfully installed Devel-OverloadInfo-0.007
--> Working on Class::Load::XS
Fetching http://www.cpan.org/authors/id/E/ET/ETHER/Class-Load-XS-0.10.tar.gz ... OK
Configuring Class-Load-XS-0.10 ... OK
Building and testing Class-Load-XS-0.10 ... OK
Successfully installed Class-Load-XS-0.10
--> Working on Package::DeprecationManager
Fetching http://www.cpan.org/authors/id/D/DR/DROLSKY/Package-DeprecationManager-0.17.tar.gz ... OK
Configuring Package-DeprecationManager-0.17 ... OK
Building and testing Package-DeprecationManager-0.17 ... OK
Successfully installed Package-DeprecationManager-0.17
--> Working on List::Util
Fetching http://www.cpan.org/authors/id/P/PE/PEVANS/Scalar-List-Utils-1.56.tar.gz ... OK
Configuring Scalar-List-Utils-1.56 ... OK
Building and testing Scalar-List-Utils-1.56 ... OK
Successfully installed Scalar-List-Utils-1.56 (upgraded from 1.50)
--> Working on Test::CleanNamespaces
Fetching http://www.cpan.org/authors/id/E/ET/ETHER/Test-CleanNamespaces-0.24.tar.gz ... OK
Configuring Test-CleanNamespaces-0.24 ... OK
Building and testing Test-CleanNamespaces-0.24 ... OK
Successfully installed Test-CleanNamespaces-0.24
--> Working on Module::Runtime::Conflicts
Fetching http://www.cpan.org/authors/id/E/ET/ETHER/Module-Runtime-Conflicts-0.003.tar.gz ... OK
Configuring Module-Runtime-Conflicts-0.003 ... OK
Building and testing Module-Runtime-Conflicts-0.003 ... OK
Successfully installed Module-Runtime-Conflicts-0.003
Building and testing Moose-2.2015 ... OK
Successfully installed Moose-2.2015
Building and testing Data-Visitor-0.31 ... OK
Successfully installed Data-Visitor-0.31
--> Working on Text::Trim
Fetching http://www.cpan.org/authors/id/R/RJ/RJT/Text-Trim-1.04.tar.gz ... OK
Configuring Text-Trim-1.04 ... OK
Building and testing Text-Trim-1.04 ... OK
Successfully installed Text-Trim-1.04
Building and testing Text-Hogan-2.03 ... OK
Successfully installed Text-Hogan-2.03
--> Working on Throwable
Fetching http://www.cpan.org/authors/id/R/RJ/RJBS/Throwable-1.000.tar.gz ... OK
Configuring Throwable-1.000 ... OK
Building and testing Throwable-1.000 ... OK
Successfully installed Throwable-1.000
--> Working on URI::Template
Fetching http://www.cpan.org/authors/id/B/BR/BRICAS/URI-Template-0.24.tar.gz ... OK
Configuring URI-Template-0.24 ... OK
Building and testing URI-Template-0.24 ... OK
Successfully installed URI-Template-0.24
--> Working on Parser::MGC
Fetching http://www.cpan.org/authors/id/P/PE/PEVANS/Parser-MGC-0.19.tar.gz ... OK
Configuring Parser-MGC-0.19 ... OK
==> Found dependencies: File::Slurp::Tiny, Feature::Compat::Try
--> Working on File::Slurp::Tiny
Fetching http://www.cpan.org/authors/id/L/LE/LEONT/File-Slurp-Tiny-0.004.tar.gz ... OK
Configuring File-Slurp-Tiny-0.004 ... OK
Building and testing File-Slurp-Tiny-0.004 ... OK
Successfully installed File-Slurp-Tiny-0.004
--> Working on Feature::Compat::Try
Fetching http://www.cpan.org/authors/id/P/PE/PEVANS/Feature-Compat-Try-0.04.tar.gz ... OK
Configuring Feature-Compat-Try-0.04 ... OK
==> Found dependencies: Syntax::Keyword::Try
--> Working on Syntax::Keyword::Try
Fetching http://www.cpan.org/authors/id/P/PE/PEVANS/Syntax-Keyword-Try-0.25.tar.gz ... OK
==> Found dependencies: XS::Parse::Keyword::Builder
--> Working on XS::Parse::Keyword::Builder
Fetching http://www.cpan.org/authors/id/P/PE/PEVANS/XS-Parse-Keyword-0.12.tar.gz ... OK
==> Found dependencies: ExtUtils::CChecker
--> Working on ExtUtils::CChecker
Fetching http://www.cpan.org/authors/id/P/PE/PEVANS/ExtUtils-CChecker-0.11.tar.gz ... OK
Configuring ExtUtils-CChecker-0.11 ... OK
Building and testing ExtUtils-CChecker-0.11 ... OK
Successfully installed ExtUtils-CChecker-0.11
Configuring XS-Parse-Keyword-0.12 ... OK
Building and testing XS-Parse-Keyword-0.12 ... OK
Successfully installed XS-Parse-Keyword-0.12
Configuring Syntax-Keyword-Try-0.25 ... OK
Building and testing Syntax-Keyword-Try-0.25 ... OK
Successfully installed Syntax-Keyword-Try-0.25
Building and testing Feature-Compat-Try-0.04 ... OK
Successfully installed Feature-Compat-Try-0.04
Building and testing Parser-MGC-0.19 ... OK
Successfully installed Parser-MGC-0.19
--> Working on Data::Util
Fetching http://www.cpan.org/authors/id/S/SY/SYOHEX/Data-Util-0.66.tar.gz ... OK
==> Found dependencies: Module::Build::XSUtil
--> Working on Module::Build::XSUtil
Fetching http://www.cpan.org/authors/id/H/HI/HIDEAKIO/Module-Build-XSUtil-0.19.tar.gz ... OK
Configuring Module-Build-XSUtil-0.19 ... OK
==> Found dependencies: File::Copy::Recursive::Reduced, Devel::CheckCompiler, Cwd::Guard
--> Working on File::Copy::Recursive::Reduced
Fetching http://www.cpan.org/authors/id/J/JK/JKEENAN/File-Copy-Recursive-Reduced-0.006.tar.gz ... OK
Configuring File-Copy-Recursive-Reduced-0.006 ... OK
Building and testing File-Copy-Recursive-Reduced-0.006 ... OK
Successfully installed File-Copy-Recursive-Reduced-0.006
--> Working on Devel::CheckCompiler
Fetching http://www.cpan.org/authors/id/S/SY/SYOHEX/Devel-CheckCompiler-0.07.tar.gz ... OK
==> Found dependencies: Module::Build::Tiny
--> Working on Module::Build::Tiny
Fetching http://www.cpan.org/authors/id/L/LE/LEONT/Module-Build-Tiny-0.039.tar.gz ... OK
Configuring Module-Build-Tiny-0.039 ... OK
Building and testing Module-Build-Tiny-0.039 ... OK
Successfully installed Module-Build-Tiny-0.039
Configuring Devel-CheckCompiler-0.07 ... OK
Building and testing Devel-CheckCompiler-0.07 ... OK
Successfully installed Devel-CheckCompiler-0.07
--> Working on Cwd::Guard
Fetching http://www.cpan.org/authors/id/K/KA/KAZEBURO/Cwd-Guard-0.05.tar.gz ... OK
Configuring Cwd-Guard-0.05 ... OK
Building and testing Cwd-Guard-0.05 ... OK
Successfully installed Cwd-Guard-0.05
Building and testing Module-Build-XSUtil-0.19 ... OK
Successfully installed Module-Build-XSUtil-0.19
Configuring Data-Util-0.66 ... OK
==> Found dependencies: Hash::Util::FieldHash::Compat, Scope::Guard
--> Working on Hash::Util::FieldHash::Compat
Fetching http://www.cpan.org/authors/id/E/ET/ETHER/Hash-Util-FieldHash-Compat-0.11.tar.gz ... OK
Configuring Hash-Util-FieldHash-Compat-0.11 ... OK
Building and testing Hash-Util-FieldHash-Compat-0.11 ... OK
Successfully installed Hash-Util-FieldHash-Compat-0.11
--> Working on Scope::Guard
Fetching http://www.cpan.org/authors/id/C/CH/CHOCOLATE/Scope-Guard-0.21.tar.gz ... OK
Configuring Scope-Guard-0.21 ... OK
Building and testing Scope-Guard-0.21 ... OK
Successfully installed Scope-Guard-0.21
Building and testing Data-Util-0.66 ... OK
Successfully installed Data-Util-0.66
--> Working on asa
Fetching http://www.cpan.org/authors/id/E/ET/ETHER/asa-1.04.tar.gz ... OK
Configuring asa-1.04 ... OK
Building and testing asa-1.04 ... OK
Successfully installed asa-1.04
--> Working on Text::CSV
Fetching http://www.cpan.org/authors/id/I/IS/ISHIGAKI/Text-CSV-2.01.tar.gz ... OK
Configuring Text-CSV-2.01 ... OK
Building and testing Text-CSV-2.01 ... OK
Successfully installed Text-CSV-2.01
--> Working on MooX::Aliases
Fetching http://www.cpan.org/authors/id/H/HA/HAARG/MooX-Aliases-0.001006.tar.gz ... OK
Configuring MooX-Aliases-0.001006 ... OK
Building and testing MooX-Aliases-0.001006 ... OK
Successfully installed MooX-Aliases-0.001006
--> Working on CGI::Expand
Fetching http://www.cpan.org/authors/id/B/BO/BOWMANBS/CGI-Expand-2.05.tar.gz ... OK
Configuring CGI-Expand-2.05 ... OK
Building and testing CGI-Expand-2.05 ... OK
Successfully installed CGI-Expand-2.05
--> Working on Path::Iterator::Rule
Fetching http://www.cpan.org/authors/id/D/DA/DAGOLDEN/Path-Iterator-Rule-1.014.tar.gz ... OK
Configuring Path-Iterator-Rule-1.014 ... OK
==> Found dependencies: Test::Filename
--> Working on Test::Filename
Fetching http://www.cpan.org/authors/id/D/DA/DAGOLDEN/Test-Filename-0.03.tar.gz ... OK
Configuring Test-Filename-0.03 ... OK
Building and testing Test-Filename-0.03 ... OK
Successfully installed Test-Filename-0.03
Building and testing Path-Iterator-Rule-1.014 ... OK
Successfully installed Path-Iterator-Rule-1.014
--> Working on Config::Onion
Fetching http://www.cpan.org/authors/id/D/DS/DSHEROH/Config-Onion-1.007.tar.gz ... OK
Configuring Config-Onion-1.007 ... OK
==> Found dependencies: Config::Any
--> Working on Config::Any
Fetching http://www.cpan.org/authors/id/H/HA/HAARG/Config-Any-0.32.tar.gz ... OK
Configuring Config-Any-0.32 ... OK
Building and testing Config-Any-0.32 ... OK
Successfully installed Config-Any-0.32
Building and testing Config-Onion-1.007 ... OK
Successfully installed Config-Onion-1.007
--> Working on IO::Handle::Util
Fetching http://www.cpan.org/authors/id/E/ET/ETHER/IO-Handle-Util-0.02.tar.gz ... OK
Configuring IO-Handle-Util-0.02 ... OK
==> Found dependencies: IO::String
--> Working on IO::String
Fetching http://www.cpan.org/authors/id/G/GA/GAAS/IO-String-1.08.tar.gz ... OK
Configuring IO-String-1.08 ... OK
Building and testing IO-String-1.08 ... OK
Successfully installed IO-String-1.08
Building and testing IO-Handle-Util-0.02 ... OK
Successfully installed IO-Handle-Util-0.02
Building and testing Catmandu-1.2015 ... OK
Successfully installed Catmandu-1.2015
--> Working on Catmandu::MARC
Fetching http://www.cpan.org/authors/id/H/HO/HOCHSTEN/Catmandu-MARC-1.254.tar.gz ... OK
Configuring Catmandu-MARC-1.254 ... OK
==> Found dependencies: XML::LibXML, MooX::Singleton, MARC::Schema, MARC::Lint, XML::XPath, MARC::File::MiJ, MARC::Parser::RAW, MARC::Record, MARC::File::MARCMaker, MARC::File::XML, MARC::Spec
--> Working on XML::LibXML
Fetching http://www.cpan.org/authors/id/S/SH/SHLOMIF/XML-LibXML-2.0207.tar.gz ... OK
==> Found dependencies: Alien::Base::Wrapper, Alien::Libxml2
--> Working on Alien::Base::Wrapper
Fetching http://www.cpan.org/authors/id/P/PL/PLICEASE/Alien-Build-2.41.tar.gz ... OK
Configuring Alien-Build-2.41 ... OK
==> Found dependencies: FFI::CheckLib, Test2::V0, File::chdir
--> Working on FFI::CheckLib
Fetching http://www.cpan.org/authors/id/P/PL/PLICEASE/FFI-CheckLib-0.28.tar.gz ... OK
Configuring FFI-CheckLib-0.28 ... OK
==> Found dependencies: Test2::Require::Module, Test2::Require::EnvVar, Test2::V0
--> Working on Test2::Require::Module
Fetching http://www.cpan.org/authors/id/E/EX/EXODIST/Test2-Suite-0.000141.tar.gz ... OK
Configuring Test2-Suite-0.000141 ... OK
==> Found dependencies: Term::Table, Test2::API, Importer, Sub::Info
--> Working on Term::Table
Fetching http://www.cpan.org/authors/id/E/EX/EXODIST/Term-Table-0.015.tar.gz ... OK
Configuring Term-Table-0.015 ... OK
==> Found dependencies: Importer
--> Working on Importer
Fetching http://www.cpan.org/authors/id/E/EX/EXODIST/Importer-0.026.tar.gz ... OK
Configuring Importer-0.026 ... OK
Building and testing Importer-0.026 ... OK
Successfully installed Importer-0.026
Building and testing Term-Table-0.015 ... OK
Successfully installed Term-Table-0.015
--> Working on Test2::API
Fetching http://www.cpan.org/authors/id/E/EX/EXODIST/Test-Simple-1.302186.tar.gz ... OK
Configuring Test-Simple-1.302186 ... OK
Building and testing Test-Simple-1.302186 ... OK
Successfully installed Test-Simple-1.302186 (upgraded from 1.302162)
--> Working on Sub::Info
Fetching http://www.cpan.org/authors/id/E/EX/EXODIST/Sub-Info-0.002.tar.gz ... OK
Configuring Sub-Info-0.002 ... OK
Building and testing Sub-Info-0.002 ... OK
Successfully installed Sub-Info-0.002
Building and testing Test2-Suite-0.000141 ... OK
Successfully installed Test2-Suite-0.000141
Building and testing FFI-CheckLib-0.28 ... OK
Successfully installed FFI-CheckLib-0.28
--> Working on File::chdir
Fetching http://www.cpan.org/authors/id/D/DA/DAGOLDEN/File-chdir-0.1010.tar.gz ... OK
Configuring File-chdir-0.1010 ... OK
Building and testing File-chdir-0.1010 ... OK
Successfully installed File-chdir-0.1010
Building and testing Alien-Build-2.41 ... OK
Successfully installed Alien-Build-2.41
--> Working on Alien::Libxml2
Fetching http://www.cpan.org/authors/id/P/PL/PLICEASE/Alien-Libxml2-0.17.tar.gz ... OK
Configuring Alien-Libxml2-0.17 ... OK
==> Found dependencies: Sort::Versions
--> Working on Sort::Versions
Fetching http://www.cpan.org/authors/id/N/NE/NEILB/Sort-Versions-1.62.tar.gz ... OK
Configuring Sort-Versions-1.62 ... OK
Building and testing Sort-Versions-1.62 ... OK
Successfully installed Sort-Versions-1.62
Building and testing Alien-Libxml2-0.17 ... OK
Successfully installed Alien-Libxml2-0.17
Configuring XML-LibXML-2.0207 ... OK
==> Found dependencies: XML::SAX::Exception, XML::SAX::DocumentLocator, XML::SAX::Base, XML::NamespaceSupport, XML::SAX
--> Working on XML::SAX::Exception
Fetching http://www.cpan.org/authors/id/G/GR/GRANTM/XML-SAX-Base-1.09.tar.gz ... OK
Configuring XML-SAX-Base-1.09 ... OK
Building and testing XML-SAX-Base-1.09 ... OK
Successfully installed XML-SAX-Base-1.09
--> Working on XML::SAX::DocumentLocator
Fetching http://www.cpan.org/authors/id/G/GR/GRANTM/XML-SAX-1.02.tar.gz ... OK
Configuring XML-SAX-1.02 ... OK
==> Found dependencies: XML::NamespaceSupport
--> Working on XML::NamespaceSupport
Fetching http://www.cpan.org/authors/id/P/PE/PERIGRIN/XML-NamespaceSupport-1.12.tar.gz ... OK
Configuring XML-NamespaceSupport-1.12 ... OK
Building and testing XML-NamespaceSupport-1.12 ... OK
Successfully installed XML-NamespaceSupport-1.12
Building and testing XML-SAX-1.02 ... OK
Successfully installed XML-SAX-1.02
Building and testing XML-LibXML-2.0207 ... OK
Successfully installed XML-LibXML-2.0207
--> Working on MooX::Singleton
Fetching http://www.cpan.org/authors/id/A/AJ/AJGB/MooX-Singleton-1.20.tar.gz ... OK
Configuring MooX-Singleton-1.20 ... OK
Building and testing MooX-Singleton-1.20 ... OK
Successfully installed MooX-Singleton-1.20
--> Working on MARC::Schema
Fetching http://www.cpan.org/authors/id/J/JO/JOROL/MARC-Schema-0.09.tar.gz ... OK
Configuring MARC-Schema-0.09 ... OK
==> Found dependencies: MARC::Parser::XML, Test::Script, File::Slurper, MARC::Parser::RAW, File::Share
--> Working on MARC::Parser::XML
Fetching http://www.cpan.org/authors/id/J/JO/JOROL/MARC-Parser-XML-0.03.tar.gz ... OK
Configuring MARC-Parser-XML-0.03 ... OK
Building and testing MARC-Parser-XML-0.03 ... OK
Successfully installed MARC-Parser-XML-0.03
--> Working on Test::Script
Fetching http://www.cpan.org/authors/id/P/PL/PLICEASE/Test-Script-1.29.tar.gz ... OK
Configuring Test-Script-1.29 ... OK
==> Found dependencies: Probe::Perl
--> Working on Probe::Perl
Fetching http://www.cpan.org/authors/id/K/KW/KWILLIAMS/Probe-Perl-0.03.tar.gz ... OK
Configuring Probe-Perl-0.03 ... OK
Building and testing Probe-Perl-0.03 ... OK
Successfully installed Probe-Perl-0.03
Building and testing Test-Script-1.29 ... OK
Successfully installed Test-Script-1.29
--> Working on File::Slurper
Fetching http://www.cpan.org/authors/id/L/LE/LEONT/File-Slurper-0.012.tar.gz ... OK
Configuring File-Slurper-0.012 ... OK
Building and testing File-Slurper-0.012 ... OK
Successfully installed File-Slurper-0.012
--> Working on MARC::Parser::RAW
Fetching http://www.cpan.org/authors/id/J/JO/JOROL/MARC-Parser-RAW-0.06.tar.gz ... OK
Configuring MARC-Parser-RAW-0.06 ... OK
Building and testing MARC-Parser-RAW-0.06 ... OK
Successfully installed MARC-Parser-RAW-0.06
--> Working on File::Share
Fetching http://www.cpan.org/authors/id/I/IN/INGY/File-Share-0.25.tar.gz ... OK
Configuring File-Share-0.25 ... OK
==> Found dependencies: File::ShareDir
--> Working on File::ShareDir
Fetching http://www.cpan.org/authors/id/R/RE/REHSACK/File-ShareDir-1.118.tar.gz ... OK
==> Found dependencies: File::ShareDir::Install
--> Working on File::ShareDir::Install
Fetching http://www.cpan.org/authors/id/E/ET/ETHER/File-ShareDir-Install-0.13.tar.gz ... OK
Configuring File-ShareDir-Install-0.13 ... OK
Building and testing File-ShareDir-Install-0.13 ... OK
Successfully installed File-ShareDir-Install-0.13
Configuring File-ShareDir-1.118 ... OK
==> Found dependencies: Class::Inspector
--> Working on Class::Inspector
Fetching http://www.cpan.org/authors/id/P/PL/PLICEASE/Class-Inspector-1.36.tar.gz ... OK
Configuring Class-Inspector-1.36 ... OK
Building and testing Class-Inspector-1.36 ... OK
Successfully installed Class-Inspector-1.36
Building and testing File-ShareDir-1.118 ... OK
Successfully installed File-ShareDir-1.118
Building and testing File-Share-0.25 ... OK
Successfully installed File-Share-0.25
Building and testing MARC-Schema-0.09 ... OK
Successfully installed MARC-Schema-0.09
--> Working on MARC::Lint
Fetching http://www.cpan.org/authors/id/E/EI/EIJABB/MARC-Lint_1.53.tar.gz ... OK
Configuring MARC-Lint-1.53 ... OK
==> Found dependencies: MARC::Record, Business::ISBN
--> Working on MARC::Record
Fetching http://www.cpan.org/authors/id/G/GM/GMCHARLT/MARC-Record-2.0.7.tar.gz ... OK
Configuring MARC-Record-v2.0.7 ... OK
Building and testing MARC-Record-v2.0.7 ... OK
Successfully installed MARC-Record-v2.0.7
--> Working on Business::ISBN
Fetching http://www.cpan.org/authors/id/B/BD/BDFOY/Business-ISBN-3.006.tar.gz ... OK
Configuring Business-ISBN-3.006 ... OK
==> Found dependencies: Business::ISBN::Data
--> Working on Business::ISBN::Data
Fetching http://www.cpan.org/authors/id/B/BD/BDFOY/Business-ISBN-Data-20210112.006.tar.gz ... OK
Configuring Business-ISBN-Data-20210112.006 ... OK
Building and testing Business-ISBN-Data-20210112.006 ... OK
Successfully installed Business-ISBN-Data-20210112.006
Building and testing Business-ISBN-3.006 ... OK
Successfully installed Business-ISBN-3.006
Building and testing MARC-Lint-1.53 ... OK
Successfully installed MARC-Lint-1.53
--> Working on XML::XPath
Fetching http://www.cpan.org/authors/id/M/MA/MANWAR/XML-XPath-1.44.tar.gz ... OK
Configuring XML-XPath-1.44 ... OK
Building and testing XML-XPath-1.44 ... OK
Successfully installed XML-XPath-1.44
--> Working on MARC::File::MiJ
Fetching http://www.cpan.org/authors/id/G/GM/GMCHARLT/MARC-File-MiJ-0.04.tar.gz ... OK
Configuring MARC-File-MiJ-0.04 ... OK
==> Found dependencies: ex::monkeypatched
--> Working on ex::monkeypatched
Fetching http://www.cpan.org/authors/id/A/AR/ARC/ex-monkeypatched-0.03.tar.gz ... OK
Configuring ex-monkeypatched-0.03 ... OK
Building and testing ex-monkeypatched-0.03 ... OK
Successfully installed ex-monkeypatched-0.03
Building and testing MARC-File-MiJ-0.04 ... OK
Successfully installed MARC-File-MiJ-0.04
--> Working on MARC::File::MARCMaker
Fetching http://www.cpan.org/authors/id/E/EI/EIJABB/MARC-File-MARCMaker-0.05.tar.gz ... OK
Configuring MARC-File-MARCMaker-0.05 ... OK
Building and testing MARC-File-MARCMaker-0.05 ... OK
Successfully installed MARC-File-MARCMaker-0.05
--> Working on MARC::File::XML
Fetching http://www.cpan.org/authors/id/G/GM/GMCHARLT/MARC-File-XML-1.0.5.tar.gz ... OK
Configuring MARC-File-XML-v1.0.5 ... OK
==> Found dependencies: MARC::Charset
--> Working on MARC::Charset
Fetching http://www.cpan.org/authors/id/G/GM/GMCHARLT/MARC-Charset-1.35.tar.gz ... OK
Configuring MARC-Charset-1.35 ... OK
==> Found dependencies: Class::Accessor
--> Working on Class::Accessor
Fetching http://www.cpan.org/authors/id/K/KA/KASEI/Class-Accessor-0.51.tar.gz ... OK
Configuring Class-Accessor-0.51 ... OK
Building and testing Class-Accessor-0.51 ... OK
Successfully installed Class-Accessor-0.51
Building and testing MARC-Charset-1.35 ... OK
Successfully installed MARC-Charset-1.35
Building and testing MARC-File-XML-v1.0.5 ... FAIL
! Installing MARC::File::XML failed. See /root/.cpanm/work/1629227216.167386/build.log for details. Retry with --force to force install it.
--> Working on MARC::Spec
Fetching http://www.cpan.org/authors/id/K/KL/KLEE/MARC-Spec-2.0.3.tar.gz ... OK
Configuring MARC-Spec-2.0.3 ... OK
==> Found dependencies: Const::Fast
--> Working on Const::Fast
Fetching http://www.cpan.org/authors/id/L/LE/LEONT/Const-Fast-0.014.tar.gz ... OK
Configuring Const-Fast-0.014 ... OK
Building and testing Const-Fast-0.014 ... OK
Successfully installed Const-Fast-0.014
Building and testing MARC-Spec-2.0.3 ... OK
Successfully installed MARC-Spec-2.0.3
! Installing the dependencies failed: Module 'MARC::File::XML' is not installed
! Bailing out the installation for Catmandu-MARC-1.254.
119 distributions installed
```

Apoi trebuie instalate pachetele lipsă.

```bash
sudo cpanm Catmandu Catmandu::Importer::MARC --force
--> Working on Catmandu
Fetching http://www.cpan.org/authors/id/N/NI/NICS/Catmandu-1.2015.tar.gz ... OK
Configuring Catmandu-1.2015 ... OK
Building and testing Catmandu-1.2015 ... OK
Successfully reinstalled Catmandu-1.2015
--> Working on Catmandu::Importer::MARC
Fetching http://www.cpan.org/authors/id/H/HO/HOCHSTEN/Catmandu-MARC-1.254.tar.gz ... OK
Configuring Catmandu-MARC-1.254 ... OK
==> Found dependencies: MARC::File::XML
--> Working on MARC::File::XML
Fetching http://www.cpan.org/authors/id/G/GM/GMCHARLT/MARC-File-XML-1.0.5.tar.gz ... OK
Configuring MARC-File-XML-v1.0.5 ... OK
Building and testing MARC-File-XML-v1.0.5 ... FAIL
! Testing MARC-File-XML-v1.0.5 failed but installing it anyway.
Successfully installed MARC-File-XML-v1.0.5
Building and testing Catmandu-MARC-1.254 ... OK
Successfully installed Catmandu-MARC-1.254
3 distributions installed
```

O instalare făcută cu multă dificultate.

## Instalare suport MongoDB

```bash
sudo cpanm Catmandu Catmandu::Store::MongoDB
[sudo] password for nicolaie:
Catmandu is up to date. (1.2015)
--> Working on Catmandu::Store::MongoDB
Fetching http://www.cpan.org/authors/id/N/NI/NICS/Catmandu-Store-MongoDB-0.0806.tar.gz ... OK
Configuring Catmandu-Store-MongoDB-0.0806 ... OK
==> Found dependencies: MongoDB, CQL::Parser
--> Working on MongoDB
Fetching http://www.cpan.org/authors/id/M/MO/MONGODB/MongoDB-v2.2.2.tar.gz ... OK
Configuring MongoDB-v2.2.2 ... OK
==> Found dependencies: BSON, BSON::Time, BSON::Types, Net::DNS, BSON::Regex, BSON::DBRef, Authen::SCRAM::Client, Authen::SASL::SASLprep, BSON::OID, BSON::Raw, BSON::XS, BSON::Bytes, BSON::Code, UUID::URandom, boolean, BSON::Decimal128, BSON::Timestamp, JSON::MaybeXS
--> Working on BSON
Fetching http://www.cpan.org/authors/id/M/MO/MONGODB/BSON-v1.12.2.tar.gz ... OK
Configuring BSON-v1.12.2 ... OK
==> Found dependencies: Crypt::URandom, JSON::MaybeXS, boolean
--> Working on Crypt::URandom
Fetching http://www.cpan.org/authors/id/D/DD/DDICK/Crypt-URandom-0.36.tar.gz ... OK
Configuring Crypt-URandom-0.36 ... OK
Building and testing Crypt-URandom-0.36 ... OK
Successfully installed Crypt-URandom-0.36
--> Working on JSON::MaybeXS
Fetching http://www.cpan.org/authors/id/E/ET/ETHER/JSON-MaybeXS-1.004003.tar.gz ... OK
Configuring JSON-MaybeXS-1.004003 ... OK
Building and testing JSON-MaybeXS-1.004003 ... OK
Successfully installed JSON-MaybeXS-1.004003
--> Working on boolean
Fetching http://www.cpan.org/authors/id/I/IN/INGY/boolean-0.46.tar.gz ... OK
Configuring boolean-0.46 ... OK
Building and testing boolean-0.46 ... OK
Successfully installed boolean-0.46
Building and testing BSON-v1.12.2 ... OK
Successfully installed BSON-v1.12.2
--> Working on Net::DNS
Fetching http://www.cpan.org/authors/id/N/NL/NLNETLABS/Net-DNS-1.32.tar.gz ... OK
Configuring Net-DNS-1.32 ... OK
==> Found dependencies: Digest::HMAC
--> Working on Digest::HMAC
Fetching http://www.cpan.org/authors/id/A/AR/ARODLAND/Digest-HMAC-1.04.tar.gz ... OK
Configuring Digest-HMAC-1.04 ... OK
Building and testing Digest-HMAC-1.04 ... OK
Successfully installed Digest-HMAC-1.04
Building and testing Net-DNS-1.32 ... OK
Successfully installed Net-DNS-1.32
--> Working on Authen::SCRAM::Client
Fetching http://www.cpan.org/authors/id/D/DA/DAGOLDEN/Authen-SCRAM-0.011.tar.gz ... OK
Configuring Authen-SCRAM-0.011 ... OK
==> Found dependencies: PBKDF2::Tiny, Test::FailWarnings, Authen::SASL::SASLprep
--> Working on PBKDF2::Tiny
Fetching http://www.cpan.org/authors/id/D/DA/DAGOLDEN/PBKDF2-Tiny-0.005.tar.gz ... OK
Configuring PBKDF2-Tiny-0.005 ... OK
Building and testing PBKDF2-Tiny-0.005 ... OK
Successfully installed PBKDF2-Tiny-0.005
--> Working on Test::FailWarnings
Fetching http://www.cpan.org/authors/id/D/DA/DAGOLDEN/Test-FailWarnings-0.008.tar.gz ... OK
Configuring Test-FailWarnings-0.008 ... OK
Building and testing Test-FailWarnings-0.008 ... OK
Successfully installed Test-FailWarnings-0.008
--> Working on Authen::SASL::SASLprep
Fetching http://www.cpan.org/authors/id/C/CF/CFAERBER/Authen-SASL-SASLprep-1.100.tar.gz ... OK
Configuring Authen-SASL-SASLprep-1.100 ... OK
==> Found dependencies: Test::NoWarnings, Unicode::Stringprep
--> Working on Test::NoWarnings
Fetching http://www.cpan.org/authors/id/H/HA/HAARG/Test-NoWarnings-1.06.tar.gz ... OK
Configuring Test-NoWarnings-1.06 ... OK
Building and testing Test-NoWarnings-1.06 ... OK
Successfully installed Test-NoWarnings-1.06
--> Working on Unicode::Stringprep
Fetching http://www.cpan.org/authors/id/C/CF/CFAERBER/Unicode-Stringprep-1.105.tar.gz ... OK
Configuring Unicode-Stringprep-1.105 ... OK
Building and testing Unicode-Stringprep-1.105 ... OK
Successfully installed Unicode-Stringprep-1.105
Building and testing Authen-SASL-SASLprep-1.100 ... OK
Successfully installed Authen-SASL-SASLprep-1.100
Building and testing Authen-SCRAM-0.011 ... OK
Successfully installed Authen-SCRAM-0.011
--> Working on BSON::XS
Fetching http://www.cpan.org/authors/id/M/MO/MONGODB/BSON-XS-v0.8.4.tar.gz ... OK
==> Found dependencies: Config::AutoConf
--> Working on Config::AutoConf
Fetching http://www.cpan.org/authors/id/A/AM/AMBS/Config-AutoConf-0.320.tar.gz ... OK
Configuring Config-AutoConf-0.320 ... OK
Building and testing Config-AutoConf-0.320 ... OK
Successfully installed Config-AutoConf-0.320
Configuring BSON-XS-v0.8.4 ... OK
Building and testing BSON-XS-v0.8.4 ... OK
Successfully installed BSON-XS-v0.8.4
--> Working on UUID::URandom
Fetching http://www.cpan.org/authors/id/D/DA/DAGOLDEN/UUID-URandom-0.001.tar.gz ... OK
Configuring UUID-URandom-0.001 ... OK
Building and testing UUID-URandom-0.001 ... OK
Successfully installed UUID-URandom-0.001
Building and testing MongoDB-v2.2.2 ... FAIL
! Installing MongoDB failed. See /root/.cpanm/work/1629488415.52160/build.log for details. Retry with --force to force install it.
--> Working on CQL::Parser
Fetching http://www.cpan.org/authors/id/B/BR/BRICAS/CQL-Parser-1.13.tar.gz ... OK
Configuring CQL-Parser-1.13 ... OK
==> Found dependencies: String::Tokenizer
--> Working on String::Tokenizer
Fetching http://www.cpan.org/authors/id/S/ST/STEVAN/String-Tokenizer-0.06.tar.gz ... OK
Configuring String-Tokenizer-0.06 ... OK
Building and testing String-Tokenizer-0.06 ... OK
Successfully installed String-Tokenizer-0.06
Building and testing CQL-Parser-1.13 ... OK
Successfully installed CQL-Parser-1.13
! Installing the dependencies failed: Module 'MongoDB' is not installed
! Bailing out the installation for Catmandu-Store-MongoDB-0.0806.
17 distributions installed
```

A eșuat, ceea ce a trebuit să aplic `--force`.

```bash
sudo cpanm Catmandu Catmandu::Store::MongoDB --force
[sudo] password for nicolaie:
--> Working on Catmandu
Fetching http://www.cpan.org/authors/id/N/NI/NICS/Catmandu-1.2015.tar.gz ... OK
Configuring Catmandu-1.2015 ... OK
Building and testing Catmandu-1.2015 ... OK
Successfully reinstalled Catmandu-1.2015
--> Working on Catmandu::Store::MongoDB
Fetching http://www.cpan.org/authors/id/N/NI/NICS/Catmandu-Store-MongoDB-0.0806.tar.gz ... OK
Configuring Catmandu-Store-MongoDB-0.0806 ... OK
==> Found dependencies: MongoDB
--> Working on MongoDB
Fetching http://www.cpan.org/authors/id/M/MO/MONGODB/MongoDB-v2.2.2.tar.gz ... OK
Configuring MongoDB-v2.2.2 ... OK
Building and testing MongoDB-v2.2.2 ... FAIL
! Testing MongoDB-v2.2.2 failed but installing it anyway.
Successfully installed MongoDB-v2.2.2
Building and testing Catmandu-Store-MongoDB-0.0806 ... OK
Successfully installed Catmandu-Store-MongoDB-0.0806
3 distributions installed
```

## Pentru suport XML

```bash
sudo apt-get install libxml-libxml-perl
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following packages were automatically installed and are no longer required:
  libllvm11 libllvm11:i386 libmlt++3 libmlt-data libmlt6 libopenshot-audio6 libopenshot16 libxdamage1:i386 melt
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  libxml-namespacesupport-perl libxml-sax-base-perl libxml-sax-expat-perl libxml-sax-perl
Suggested packages:
  libxml-sax-expatxs-perl
The following NEW packages will be installed:
  libxml-libxml-perl libxml-namespacesupport-perl libxml-sax-base-perl libxml-sax-expat-perl libxml-sax-perl
0 upgraded, 5 newly installed, 0 to remove and 4 not upgraded.
Need to get 418 kB of archives.
After this operation, 1.455 kB of additional disk space will be used.
Do you want to continue? [Y/n] Y
Get:1 http://archive.ubuntu.com/ubuntu focal/main amd64 libxml-namespacesupport-perl all 1.12-1 [13,2 kB]
Get:2 http://archive.ubuntu.com/ubuntu focal/main amd64 libxml-sax-base-perl all 1.09-1 [18,8 kB]
Get:3 http://archive.ubuntu.com/ubuntu focal/main amd64 libxml-sax-perl all 1.02+dfsg-1 [56,2 kB]
Get:4 http://archive.ubuntu.com/ubuntu focal/main amd64 libxml-libxml-perl amd64 2.0134+dfsg-1build1 [320 kB]
Get:5 http://archive.ubuntu.com/ubuntu focal/main amd64 libxml-sax-expat-perl all 0.51-1 [10,5 kB]
Fetched 418 kB in 1s (509 kB/s)
Selecting previously unselected package libxml-namespacesupport-perl.
(Reading database ... 451810 files and directories currently installed.)
Preparing to unpack .../libxml-namespacesupport-perl_1.12-1_all.deb ...
Unpacking libxml-namespacesupport-perl (1.12-1) ...
Selecting previously unselected package libxml-sax-base-perl.
Preparing to unpack .../libxml-sax-base-perl_1.09-1_all.deb ...
Unpacking libxml-sax-base-perl (1.09-1) ...
Selecting previously unselected package libxml-sax-perl.
Preparing to unpack .../libxml-sax-perl_1.02+dfsg-1_all.deb ...
Unpacking libxml-sax-perl (1.02+dfsg-1) ...
Selecting previously unselected package libxml-libxml-perl.
Preparing to unpack .../libxml-libxml-perl_2.0134+dfsg-1build1_amd64.deb ...
Unpacking libxml-libxml-perl (2.0134+dfsg-1build1) ...
Selecting previously unselected package libxml-sax-expat-perl.
Preparing to unpack .../libxml-sax-expat-perl_0.51-1_all.deb ...
Unpacking libxml-sax-expat-perl (0.51-1) ...
Setting up libxml-namespacesupport-perl (1.12-1) ...
Setting up libxml-sax-base-perl (1.09-1) ...
Setting up libxml-sax-perl (1.02+dfsg-1) ...
update-perl-sax-parsers: Non-vendor version of XML::SAX is installed.
update-perl-sax-parsers: Automatic registration of SAX parsers might not work.
update-perl-sax-parsers: Registering Perl SAX parser XML::SAX::PurePerl with priority 10...
update-perl-sax-parsers: Non-vendor version of XML::SAX is installed.
update-perl-sax-parsers: Automatic registration of SAX parsers might not work.
update-perl-sax-parsers: Updating overall Perl SAX parser modules info file...

Creating config file /etc/perl/XML/SAX/ParserDetails.ini with new version
Setting up libxml-libxml-perl (2.0134+dfsg-1build1) ...
update-perl-sax-parsers: Non-vendor version of XML::SAX is installed.
update-perl-sax-parsers: Automatic registration of SAX parsers might not work.
update-perl-sax-parsers: Registering Perl SAX parser XML::LibXML::SAX::Parser with priority 50...
update-perl-sax-parsers: Non-vendor version of XML::SAX is installed.
update-perl-sax-parsers: Automatic registration of SAX parsers might not work.
update-perl-sax-parsers: Registering Perl SAX parser XML::LibXML::SAX with priority 50...
update-perl-sax-parsers: Non-vendor version of XML::SAX is installed.
update-perl-sax-parsers: Automatic registration of SAX parsers might not work.
update-perl-sax-parsers: Updating overall Perl SAX parser modules info file...
Replacing config file /etc/perl/XML/SAX/ParserDetails.ini with new version
Setting up libxml-sax-expat-perl (0.51-1) ...
update-perl-sax-parsers: Non-vendor version of XML::SAX is installed.
update-perl-sax-parsers: Automatic registration of SAX parsers might not work.
update-perl-sax-parsers: Registering Perl SAX parser XML::SAX::Expat with priority 50...
update-perl-sax-parsers: Non-vendor version of XML::SAX is installed.
update-perl-sax-parsers: Automatic registration of SAX parsers might not work.
update-perl-sax-parsers: Updating overall Perl SAX parser modules info file...
Replacing config file /etc/perl/XML/SAX/ParserDetails.ini with new version
Processing triggers for man-db (2.9.1-1) ...
```

Verifică cu

```bash
xml2-config --version
```

Dacă n-ai

```bash
sudo apt install libxml2-dev
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following packages were automatically installed and are no longer required:
  libllvm11 libllvm11:i386 libmlt++3 libmlt-data libmlt6 libopenshot-audio6 libopenshot16 libxdamage1:i386 melt
Use 'sudo apt autoremove' to remove them.
The following additional packages will be installed:
  icu-devtools libicu-dev
Suggested packages:
  icu-doc
The following NEW packages will be installed:
  icu-devtools libicu-dev libxml2-dev
0 upgraded, 3 newly installed, 0 to remove and 4 not upgraded.
Need to get 10,4 MB of archives.
After this operation, 48,9 MB of additional disk space will be used.
Do you want to continue? [Y/n] Y
Get:1 http://archive.ubuntu.com/ubuntu focal/main amd64 icu-devtools amd64 66.1-2ubuntu2 [188 kB]
Get:2 http://archive.ubuntu.com/ubuntu focal/main amd64 libicu-dev amd64 66.1-2ubuntu2 [9.450 kB]
Get:3 http://archive.ubuntu.com/ubuntu focal-updates/main amd64 libxml2-dev amd64 2.9.10+dfsg-5ubuntu0.20.04.1 [735 kB]
Fetched 10,4 MB in 19s (547 kB/s)
Selecting previously unselected package icu-devtools.
(Reading database ... 451994 files and directories currently installed.)
Preparing to unpack .../icu-devtools_66.1-2ubuntu2_amd64.deb ...
Unpacking icu-devtools (66.1-2ubuntu2) ...
Selecting previously unselected package libicu-dev:amd64.
Preparing to unpack .../libicu-dev_66.1-2ubuntu2_amd64.deb ...
Unpacking libicu-dev:amd64 (66.1-2ubuntu2) ...
Selecting previously unselected package libxml2-dev:amd64.
Preparing to unpack .../libxml2-dev_2.9.10+dfsg-5ubuntu0.20.04.1_amd64.deb ...
Unpacking libxml2-dev:amd64 (2.9.10+dfsg-5ubuntu0.20.04.1) ...
Setting up icu-devtools (66.1-2ubuntu2) ...
Setting up libicu-dev:amd64 (66.1-2ubuntu2) ...
Setting up libxml2-dev:amd64 (2.9.10+dfsg-5ubuntu0.20.04.1) ...
Processing triggers for man-db (2.9.1-1) ...
```

## Instalare suport ElasticSearch

```bash
cpanm Catmandu::Store::ElasticSearch
--> Working on Catmandu::Store::ElasticSearch
Fetching http://www.cpan.org/authors/id/N/NI/NICS/Catmandu-Store-Elasticsearch-1.0202.tar.gz ... OK
Configuring Catmandu-Store-Elasticsearch-1.0202 ... OK
==> Found dependencies: Search::Elasticsearch
--> Working on Search::Elasticsearch
Fetching http://www.cpan.org/authors/id/E/EZ/EZIMUEL/Search-Elasticsearch-7.714.tar.gz ... OK
Configuring Search-Elasticsearch-7.714 ... OK
==> Found dependencies: Net::IP, Log::Any::Adapter::Callback, Test::SharedFork
--> Working on Net::IP
Fetching http://www.cpan.org/authors/id/M/MA/MANU/Net-IP-1.26.tar.gz ... OK
Configuring Net-IP-1.26 ... OK
Building and testing Net-IP-1.26 ... OK
Successfully installed Net-IP-1.26
--> Working on Log::Any::Adapter::Callback
Fetching http://www.cpan.org/authors/id/P/PE/PERLANCAR/Log-Any-Adapter-Callback-0.101.tar.gz ... OK
Configuring Log-Any-Adapter-Callback-0.101 ... OK
Building and testing Log-Any-Adapter-Callback-0.101 ... OK
Successfully installed Log-Any-Adapter-Callback-0.101
--> Working on Test::SharedFork
Fetching http://www.cpan.org/authors/id/E/EX/EXODIST/Test-SharedFork-0.35.tar.gz ... OK
Configuring Test-SharedFork-0.35 ... OK
Building and testing Test-SharedFork-0.35 ... OK
Successfully installed Test-SharedFork-0.35
Building and testing Search-Elasticsearch-7.714 ... OK
Successfully installed Search-Elasticsearch-7.714
Building and testing Catmandu-Store-Elasticsearch-1.0202 ... OK
Successfully installed Catmandu-Store-Elasticsearch-1.0202
5 distributions installed
```
