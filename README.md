{:toc}
# Hets (The heterogeneous tool set)

Hets is a parsing, static analysis and proof management tool incorporating various provers and different specification languages, thus providing a tool for heterogeneous specifications. Logic translations are first-class citizens.

### Supported languages

* general-purpose logics: [Propositional](http://en.wikipedia.org/wiki/Propositional_calculus), [QBF](http://en.wikipedia.org/wiki/QBF), [TPTP](http://www.tptp.org/)/SoftFOL, [CASL](http://www.cofi.info/CASL) (FOL), [HasCASL](http://www.informatik.uni-bremen.de/agbkb/forschung/formal_methods/CoFI/HasCASL/) (HOL)
* logical frameworks: [Isabelle](http://www.cl.cam.ac.uk/research/hvg/Isabelle/), [LF](http://en.wikipedia.org/wiki/LF_%28logical_framework%29), DFOL
* modeling languages: [Meta-Object Facility (MOF)](https://en.wikipedia.org/wiki/Meta-Object_Facility), [Query/View/Transformation (QVT)](https://en.wikipedia.org/wiki/QVT)
* ontologies and constraint languages: [OWL](http://www.w3.org/TR/owl-features/), [CommonLogic](http://cl.tamu.edu/), [RelScheme](http://en.wikipedia.org/wiki/Database_schema), ConstraintCASL
* reactive systems: CspCASL, [CoCASL](http://www.informatik.uni-bremen.de/agbkb/forschung/formal_methods/CoFI/CoCASL/), ModalCASL, [Maude](http://maude.cs.uiuc.edu/)
* programming languages: [Haskell](http://www.haskell.org/), [VSE](http://www.dfki.de/vse/systems/vse/)
* logics of specific tools: Reduce, DMU ([CATIA](http://en.wikipedia.org/wiki/CATIA))

### The following provers have been connected to Hets:

* [minisat](http://minisat.se/) and [zChaff](http://www.princeton.edu/~chaff/zchaff.html), which are SAT solvers,
* [SPASS](http://www.spass-prover.org/), [Vampire](http://en.wikipedia.org/wiki/Vampire_(theorem_prover)), [Darwin](http://combination.cs.uiowa.edu/Darwin/), [KRHyper](http://userpages.uni-koblenz.de/~wernhard/krhyper/) and [MathServe](http://www.ags.uni-sb.de/~jzimmer/mathserve.html), which are automatic first-order theorem provers,
* [Pellet](http://clarkparsia.com/pellet/) and [Fact++](http://owl.man.ac.uk/factplusplus/), description logic tableau provers,
* [Leo II](http://www.ags.uni-sb.de/~leo) and [Satallax](http://www.ps.uni-saarland.de/~cebrown/satallax/), automated higher-order provers,
* [Isabelle](http://www.cl.cam.ac.uk/Research/HVG/Isabelle/), an interactive higher-order theorem prover,
* [CSPCASL-prover](http://dx.doi.org/10.1016/j.entcs.2009.08.018), an Isabelle-based prover for CspCASL,
* [VSE](http://www.dfki.de/vse/systems/vse/), an interactive prover for dynamic logic.

The structuring constructs of the heterogeneous specification language are those of the language [CASL](http://www.cofi.info/CASL.html), plus some constructs to select languages (logics) and language translations. The heterogeneous specification language of Hets is called [HetCASL](http://www.informatik.uni-bremen.de/agbkb/forschung/formal_methods/CoFI/HetCASL/index_e.htm). However, Hets can also read other structuring constructs, like those of Haskell, Maude or OWL. All these are mapped to so-called development graphs and processed with a proof calculus for heterogeneous development graphs that allows to decompose global proof obligations into local ones (during this, Hets also needs to compute [colimits](http://en.wikipedia.org/wiki/Limit_%28category_theory%29#Colimits_2) of theories over the involved logics).

Hets is based on a graph of logics and logic translations. The overall architecture is depicted below. Adding new logics and logic translations to Hets can be done with moderate effort by adding some Haskell code to the Hets source. With the [Latin](https://trac.omdoc.org/LATIN/) project, this becomes much easier: logics (and in the near future also logic translations) can be declaratively specified in [LF](http://twelf.plparty.org/wiki/Bibliography_of_LF).

<img src="https://github.com/spechub/attachment/raw/a0f26aadac374988f7bee3e191e95ca30e7be511/hets2010.png" alt="Architecture of the heterogeneous tool set Hets"></img>

## Using Hets

You can try out Hets sing the [Web-based interface](http://pollux.informatik.uni-bremen.de:8000/)

#### The best way to use hets is under Ubuntu. Possibly run this OS in a virtual box.
A compressed (1.2G, uncompressed 4.2 G) virtual box image can be [downloaded from here](http://www.informatik.uni-bremen.de/agbkb/forschung/formal_methods/CoFI/hets/vbox-x86-linux). username/password is ubuntu/reverse.

### Installing Hets under Ubuntu Trusty Tahr (14.04)

#### The basic system
```
sudo apt-add-repository ppa:hets/hets
sudo apt-get update
sudo apt-get install hets-core
```

* additionally, you can install (via apt-get) hets-ontology
* for the full system including all of these, use hets instead of hets-core

#### Hets development
For Hets development additionally type in
```
sudo apt-add-repository -s "deb http://ppa.launchpad.net/hets/hets/ubuntu trusty main"
sudo apt-get update
sudo apt-get build-dep hets
```

### Hets Images for Mac OS X 10.9 (Mavericks)

[Disk images for the Hets application](http://www.informatik.uni-bremen.de/agbkb/forschung/formal_methods/CoFI/hets/intel-mac/dmgs/) have only limited functionality. (GTK based menus are missing.)

### Hets binaries
(these are usually not needed but may replace the binaries from above)

* Linux x86
	* [Daily snapshot](http://www.informatik.uni-bremen.de/agbkb/forschung/formal_methods/CoFI/hets/linux/daily/)
	* [Latest release](http://www.informatik.uni-bremen.de/agbkb/forschung/formal_methods/CoFI/hets/linux/releasedhets.bz2)
	* [All versions](http://www.informatik.uni-bremen.de/agbkb/forschung/formal_methods/CoFI/hets/linux/versions/)
* Linux x86_64
	* [Daily snapshot](http://www.informatik.uni-bremen.de/agbkb/forschung/formal_methods/CoFI/hets/linux64/daily/)
	* [Latest release](http://www.informatik.uni-bremen.de/agbkb/forschung/formal_methods/CoFI/hets/linux64/releasedhets.bz2)
	* [All versions](http://www.informatik.uni-bremen.de/agbkb/forschung/formal_methods/CoFI/hets/linux64/versions/)
* (Mavericks) Intel Mac
	* [Daily snapshot](http://www.informatik.uni-bremen.de/agbkb/forschung/formal_methods/CoFI/hets/intel-mac/daily/)
	* [Latest release](http://www.informatik.uni-bremen.de/agbkb/forschung/formal_methods/CoFI/hets/intel-mac/releasedhets.bz2)
	* [All versions](http://www.informatik.uni-bremen.de/agbkb/forschung/formal_methods/CoFI/hets/intel-mac/versions/)
* Solaris
	* [Daily snapshot](http://www.informatik.uni-bremen.de/agbkb/forschung/formal_methods/CoFI/hets/pc-solaris/daily/)
	* [Latest release](http://www.informatik.uni-bremen.de/agbkb/forschung/formal_methods/CoFI/hets/pc-solaris/releasedhets.bz2)
	* [All versions](http://www.informatik.uni-bremen.de/agbkb/forschung/formal_methods/CoFI/hets/pc-solaris/versions/)


## Development
_How do I, as a developer, start working on the project?_ 

1. _What dependencies does it have (where are they expressed) and how do I install them?_
2. _How can I see the project working before I change anything?_



## Testing

_How do I run the project's automated tests?_

### Unit Tests

1. `rake spec`

### Integration Tests

1. _Run other local services / provide credentials for external services._
2. `rake spec:integration`

## Deploying

### _How to setup the deployment environment_

- _Required heroku addons, packages, or chef recipes._
- _Required environment variables or credentials not included in git._
- _Monitoring services and logging._

### _How to deploy_

## Troubleshooting & Useful Tools

_Examples of common tasks_

> e.g.
> 
> - How to make curl requests while authenticated via oauth.
> - How to monitor background jobs.
> - How to run the app through a proxy.

## Contributing changes

- _Internal git workflow_
- _Pull request guidelines_
- _Tracker project_
- _Google group_
- _irc channel_
- _"Please open github issues"_

## License
