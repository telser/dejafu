Release Notes
=============

This project is versioned according to the PVP_, the *de facto*
standard Haskell versioning scheme.

.. _PVP: https://pvp.haskell.org/


2.4.0.7 (2025-01-06)
--------------------

* Git: :tag:`dejafu-2.4.0.7`
* Hackage: :hackage:`dejafu-2.4.0.7`

Miscellaneous
~~~~~~~~~~~~~

* The upper bound on :hackage:`random` is <1.4.


2.4.0.6 (2024-12-11)
--------------------

* Git: :tag:`dejafu-2.4.0.6`
* Hackage: :hackage:`dejafu-2.4.0.6`

**Contributors:** :u:`telser` (:pull:`417`).

Miscellaneous
~~~~~~~~~~~~~

* Update documentation link in ``Test.DejaFu``.
* Fix GHC compatibility warning.
* The upper bound on :hackage:`containers` is <0.8.


2.4.0.5 (2023-06-17)
--------------------

* Git: :tag:`dejafu-2.4.0.5`
* Hackage: :hackage:`dejafu-2.4.0.5`

Miscellaneous
~~~~~~~~~~~~~

* The upper bound on :hackage:`transformers` is <0.7.


2.4.0.4 (2022-08-22)
--------------------

* Git: :tag:`dejafu-2.4.0.4`
* Hackage: :hackage:`dejafu-2.4.0.4`

Miscellaneous
~~~~~~~~~~~~~

* Update doctest examples in `Test.DejaFu`.
* The upper bound on :hackage:`leancheck` is <2.


2.4.0.3 (2021-08-15)
--------------------

* Git: :tag:`dejafu-2.4.0.3`
* Hackage: :hackage:`dejafu-2.4.0.3`

Miscellaneous
~~~~~~~~~~~~~

* Remove reference to freenode in README.


2.4.0.2 (2021-03-14)
--------------------

* Git: :tag:`dejafu-2.4.0.2`
* Hackage: :hackage:`dejafu-2.4.0.2`

Fixed
~~~~~

* (:issue:`334`) Compilation error under GHC 9 due to use of
  ``const``.


2.4.0.1 (2020-12-28)
--------------------

* Git: :tag:`dejafu-2.4.0.1`
* Hackage: :hackage:`dejafu-2.4.0.1`

Fixed
~~~~~

* (:issue:`331`) Initial TVar values from setup actions are now
  restored for subsequent executions.


2.4.0.0 (2020-07-01)
--------------------

* Git: :tag:`dejafu-2.4.0.0`
* Hackage: :hackage:`dejafu-2.4.0.0`

Added
~~~~~

* Thread action constructor for STM transactions which throw an
  exception: ``Test.DejaFu.Types.ThreadAction`` ``ThrownSTM``

Changed
~~~~~~~

* ``Test.DejaFu.Types.ThreadAction``, ``Throw``, and ``ThrowTo`` now
  include the resultant masking state, and no bool.

Fixed
~~~~~

* (:issue:`324`) Jumping out of a restored mask into an exception
  handler now atomically restores the masking state.


2.3.0.1 (2020-06-24)
--------------------

* Git: :tag:`dejafu-2.3.0.1`
* Hackage: :hackage:`dejafu-2.3.0.1`

Miscellaneous
~~~~~~~~~~~~~

* The upper bound on :hackage:`random` is <1.3.


2.3.0.0 (2020-05-14)
--------------------

* Git: :tag:`dejafu-2.3.0.0`
* Hackage: :hackage:`dejafu-2.3.0.0`

Miscellaneous
~~~~~~~~~~~~~

* The version bound on :hackage:`concurrency` is >=1.11 <1.12.


2.2.0.0 (2020-05-10)
--------------------

* Git: :tag:`dejafu-2.2.0.0`
* Hackage: :hackage:`dejafu-2.2.0.0`

Added
~~~~~

* Thread action constructors for the ``MonadConc`` ``getMaskingState``
  function:

  * ``Test.DejaFu.Types.ThreadAction``, ``GetMaskingState``
  * ``Test.DejaFu.Types.Lookahead``, ``WillGetMaskingState``

Miscellaneous
~~~~~~~~~~~~~

* The version bound on :hackage:`concurrency` is >=1.10 <1.11.


2.1.0.3 (2020-02-29)
--------------------

* Git: :tag:`dejafu-2.1.0.3`
* Hackage: :hackage:`dejafu-2.1.0.3`

Fixed
~~~~~

* Fixed an internal error message.


2.1.0.2 (2020-02-29)
--------------------

* Git: :tag:`dejafu-2.1.0.2`
* Hackage: :hackage:`dejafu-2.1.0.2`

Miscellaneous
~~~~~~~~~~~~~

* The upper version bound on :hackage:`concurrency` is <1.10.


2.1.0.1 (2019-10-04)
--------------------

* Git: :tag:`dejafu-2.1.0.1`
* Hackage: :hackage:`dejafu-2.1.0.1`

Miscellaneous
~~~~~~~~~~~~~

* Fixed a compilation error with GHC 8.8
* The upper version bound on :hackage:`concurrency` is <1.9.


2.1.0.0 (2019-03-24)
--------------------

* Git: :tag:`dejafu-2.1.0.0`
* Hackage: :hackage:`dejafu-2.1.0.0`

Added
~~~~~

* The ``Test.DejaFu.Types.MonadDejaFu`` typeclass, containing the primitives
  needed to run a concurrent program.  There are instances for:

  * ``IO``, which is probably the ``MonadConc`` instance people used previously,
    so there is no breaking change there.
  * ``CatchT (ST t)``, meaning that concurrent programs can be run without
    ``IO`` once more.

* Thread action constructors for ``MonadConc`` ``supportsBoundThreads``
  function:

  * ``Test.DejaFu.Types.ThreadAction``, ``SupportsBoundThreads``
  * ``Test.DejaFu.Types.Lookahead``, ``WillSupportsBoundThreads``

Changed
~~~~~~~

* Many functions which had a ``MonadConc`` constraint now have a ``MonadDejaFu``
  constraint:

  * In ``Test.DejaFu``

    * ``autocheck``
    * ``autocheckWay``
    * ``autocheckWithSettings``
    * ``dejafu``
    * ``dejafuWay``
    * ``dejafuWithSettings``
    * ``dejafus``
    * ``dejafusWay``
    * ``dejafusWithSettings``
    * ``runTest``
    * ``runTestWay``
    * ``runTestWithSettings``

  * In ``Test.DejaFu.Conc``

    * ``runConcurrent``
    * ``recordSnapshot``
    * ``runSnapshot``

  * In ``Test.DejaFu.SCT``

    * ``runSCT``
    * ``resultsSet``
    * ``runSCT'``
    * ``resultsSet'``
    * ``runSCTWithSettings``
    * ``resultsSetWithSettings``
    * ``runSCTWithSettings'``
    * ``resultsSetWithSettings'``

Miscellaneous
~~~~~~~~~~~~~

* The version bound on :hackage:`concurrency` is >=1.7 and <1.8.


2.0.0.1 (2019-03-14)
--------------------

* Git: :tag:`dejafu-2.0.0.1`
* Hackage: :hackage:`dejafu-2.0.0.1`

Fixed
~~~~~

* (:issue:`267`) Throwing an asynchronous exception to the current
  thread interrupts the current thread even if it is masked.


2.0.0.0 (2019-02-12)
--------------------

* Git: :tag:`dejafu-2.0.0.0`
* Hackage: :hackage:`dejafu-2.0.0.0`

Added
~~~~~

* The ``Program`` types and their constructors (re-exported from
  ``Test.DejaFu``):

  * ``Test.DejaFu.Conc.Program``
  * ``Test.DejaFu.Conc.Basic``
  * ``Test.DejaFu.Conc.WithSetup``
  * ``Test.DejaFu.Conc.WithSetupAndTeardown``
  * ``Test.DejaFu.Conc.withSetup``
  * ``Test.DejaFu.Conc.withTeardown``
  * ``Test.DejaFu.Conc.withSetupAndTeardown``

* The ``Invariant`` type and associated functions (re-exported from
  ``Test.DejaFu``):

  * ``Test.DejaFu.Conc.Invariant``
  * ``Test.DejaFu.Conc.registerInvariant``
  * ``Test.DejaFu.Conc.inspectIORef``
  * ``Test.DejaFu.Conc.inspectMVar``
  * ``Test.DejaFu.Conc.inspectTVar``

* New snapshotting functions:

  * ``Test.DejaFu.Conc.Snapshot``
  * ``Test.DejaFu.Conc.recordSnapshot``
  * ``Test.DejaFu.Conc.runSnapshot``

* ``Test.DejaFu.Settings.llengthBound``, which now applies to all ways
  of testing.

* ``Test.DejaFu.Types.isInvariantFailure`` (re-exported from
  ``Test.DejaFu``).

* ``Test.DejaFu.runTestWithSettings`` function.

* A simplified form of the concurrency state:

  * ``Test.DejaFu.Types.ConcurrencyState``
  * ``Test.DejaFu.Types.isBuffered``
  * ``Test.DejaFu.Types.numBuffered``
  * ``Test.DejaFu.Types.isFull``
  * ``Test.DejaFu.Types.canInterrupt``
  * ``Test.DejaFu.Types.canInterruptL``
  * ``Test.DejaFu.Types.isMaskedInterruptible``
  * ``Test.DejaFu.Types.isMaskedUninterruptible``

Changed
~~~~~~~

* ``Test.DejaFu.Schedule.Scheduler`` has a ``ConcurrencyState``
  parameter.

* ``Test.DejaFu.alwaysSameBy`` and ``Test.DejaFu.notAlwaysSameBy``
  return a representative trace for each unique condition.

* Functions which took a ``ConcT`` now take a ``Program pty``:

  * ``Test.DejaFu.autocheck``
  * ``Test.DejaFu.autocheckWay``
  * ``Test.DejaFu.autocheckWithSettings``
  * ``Test.DejaFu.dejafu``
  * ``Test.DejaFu.dejafuWay``
  * ``Test.DejaFu.dejafuWithSettings``
  * ``Test.DejaFu.dejafus``
  * ``Test.DejaFu.dejafusWay``
  * ``Test.DejaFu.dejafusWithSettings``
  * ``Test.DejaFu.runTest``
  * ``Test.DejaFu.runTestWay``
  * ``Test.DejaFu.runTestWithSettings``
  * ``Test.DejaFu.Conc.runConcurrent``
  * ``Test.DejaFu.SCT.runSCT``
  * ``Test.DejaFu.SCT.resultsSet``
  * ``Test.DejaFu.SCT.runSCT'``
  * ``Test.DejaFu.SCT.resultsSet'``
  * ``Test.DejaFu.SCT.runSCTWithSettings``
  * ``Test.DejaFu.SCT.resultsSetWithSettings``
  * ``Test.DejaFu.SCT.runSCTWithSettings'``
  * ``Test.DejaFu.SCT.resultsSetWithSettings'``

* ``Test.DejaFu.Conc.ConcT`` is an alias for ``Program Basic``.

* ``Test.DejaFu.Types.Bounds``:

  * Removed ``boundLength`` field.

* ``Test.DejaFu.Types.Condition``:

  * Added ``InvariantFailure`` constructor
  * Removed ``STMDeadlock`` constructor

* ``Test.DejaFu.Types.Error``:

  * Removed ``NestedSubconcurrency``, ``MultithreadedSubconcurrency``, and
    ``LateDontCheck`` constructors.

* ``Test.DejaFu.Types.Lookahead``:

  * Added ``WillRegisterInvariant`` constructor
  * Removed ``WillSubconcurrency``, ``WillStopSubconcurrency``, and
    ``WillDontCheck`` constructors

* ``Test.DejaFu.Types.ThreadAction``:

  * Added ``RegisterInvariant`` constructor
  * Removed ``Subconcurrency``, ``StopSubconcurrency``, and
    ``DontCheck`` constructors

Removed
~~~~~~~

* The deprecated functions:

  * ``Test.DejaFu.dejafuDiscard``
  * ``Test.DejaFu.SCT.runSCTDiscard``
  * ``Test.DejaFu.SCT.runSCTDiscard'``
  * ``Test.DejaFu.SCT.resultsSetDiscard``
  * ``Test.DejaFu.SCT.resultsSetDiscard'``
  * ``Test.DejaFu.SCT.sctBound``
  * ``Test.DejaFu.SCT.sctBoundDiscard``
  * ``Test.DejaFu.SCT.sctUniformRandom``
  * ``Test.DejaFu.SCT.sctUniformRandomDiscard``
  * ``Test.DejaFu.SCT.sctWeightedRandom``
  * ``Test.DejaFu.SCT.sctWeightedRandomDiscard``

* The deprecated type ``Test.DejaFu.Types.Failure``

* Old snapshotting functions:

  * ``Test.DejaFu.Conc.DCSnapshot``
  * ``Test.DejaFu.Conc.runForDCSnapshot``
  * ``Test.DejaFu.Conc.runWithDCSnapshot``
  * ``Test.DejaFu.Conc.canDCSnapshot``
  * ``Test.DejaFu.Conc.threadsFromDCSnapshot``

* ``Test.DejaFu.Conc.dontCheck``

* ``Test.DejaFu.Conc.subconcurrency``

* ``Test.DejaFu.Settings.defaultLengthBound``

* ``Test.DejaFu.Types.isIncorrectUsage``


1.12.0.0 (2019-01-20)
---------------------

* Git: :tag:`dejafu-1.12.0.0`
* Hackage: :hackage:`dejafu-1.12.0.0`

Added
~~~~~

* ``Test.DejaFu.Types.Error`` for internal errors and misuses, with
  predicates:

  * ``Test.DejaFu.Types.isSchedulerError``
  * ``Test.DejaFu.Types.isIncorrectUsage``

* Deprecated ``Test.DejaFu.Types.Failure`` type synonym for
  ``Condition``.

* The ``Test.DejaFu.Settings.lshowAborts`` option, to make SCT
  functions show ``Abort`` conditions.

* ``Test.DejaFu.Utils.showCondition``

Changed
~~~~~~~

* Renamed ``Test.DejaFu.Types.Failure`` to
  ``Test.DejaFu.Types.Condition``.

* The SCT functions drop ``Left Abort`` results by default, restore
  the old behaviour with ``Test.DejaFu.Settings.lshowAborts``.

Removed
~~~~~~~

* ``Test.DejaFu.Types.isInternalError``
* ``Test.DejaFu.Types.isIllegalDontCheck``
* ``Test.DejaFu.Types.isIllegalSubconcurrency``
* ``Test.DejaFu.Utils.showFail``


1.11.0.5 (2019-01-17)
---------------------

* Git: :tag:`dejafu-1.11.0.5`
* Hackage: :hackage:`dejafu-1.11.0.5`

Miscellaneous
~~~~~~~~~~~~~

* The upper bound on :hackage:`leancheck` is <0.10.


1.11.0.4 (2018-12-02)
---------------------

* Git: :tag:`dejafu-1.11.0.4`
* Hackage: :hackage:`dejafu-1.11.0.4`

**Contributors:** :u:`pepeiborra` (:pull:`290`).

Miscellaneous
~~~~~~~~~~~~~

* (:pull:`290`) The upper bound on :hackage:`containers` is <0.7.
* (:pull:`290`) The upper bound on :hackage:`leancheck` is <0.9.


1.11.0.3 (2018-07-15)
---------------------

* Git: :tag:`dejafu-1.11.0.3`
* Hackage: :hackage:`dejafu-1.11.0.3`

Fixed
~~~~~

* (:issue:`275`) In trace simplification, only remove a commit if
  there are no other buffered writes for that same `IORef`.


1.11.0.2 (2018-07-08)
---------------------

* Git: :tag:`dejafu-1.11.0.2`
* Hackage: :hackage:`dejafu-1.11.0.2`

Miscellaneous
~~~~~~~~~~~~~

* The upper bound on :hackage:`profunctors` is <6.


1.11.0.1 (2018-07-02)
---------------------

* Git: :tag:`dejafu-1.11.0.1`
* Hackage: :hackage:`dejafu-1.11.0.1`

Miscellaneous
~~~~~~~~~~~~~

* The upper bound on :hackage:`contravariant` is <1.6.


1.11.0.0 - IORefs (2018-07-01)
------------------------------

* Git: :tag:`dejafu-1.11.0.0`
* Hackage: :hackage:`dejafu-1.11.0.0`

Changed
~~~~~~~

* (:issue:`274`) ``CRef`` is now ``IORef``: all functions, data
  constructors, and types have been renamed.

* The lower bound on :hackage:`concurrency` is 1.6.


1.10.1.0 (2018-06-17)
---------------------

* Git: :tag:`dejafu-1.10.1.0`
* Hackage: :hackage:`dejafu-1.10.1.0`

Added
~~~~~

* (:issue:`224`) The ``Test.DejaFu.Settings.lsafeIO`` option, for when
  all lifted IO is thread-safe (such as exclusively managing
  thread-local state).


1.10.0.0 (2018-06-17)
---------------------

* Git: :tag:`dejafu-1.10.0.0`
* Hackage: :hackage:`dejafu-1.10.0.0`

Added
~~~~~

* The ``Test.DejaFu.notAlwaysSameOn`` and ``notAlwaysSameBy``
  predicates, generalising ``notAlwaysSame``.

Changed
~~~~~~~

* ``Test.DejaFu.autocheck`` and related functions use the
  ``successful`` predicate, rather than looking specifically for
  deadlocks and uncaught exceptions.

* (:issue:`259`) The ``Test.DejaFu.alwaysSame``, ``alwaysSameOn``,
  ``alwaysSameBy``, and ``notAlwaysSame`` predicates fail if the
  computation under test fails.


1.9.1.0 (2018-06-10)
--------------------

* Git: :tag:`dejafu-1.9.1.0`
* Hackage: :hackage:`dejafu-1.9.1.0`

Added
~~~~~

* A ``Test.DejaFu.successful`` predicate, to check that a computation
  never fails.


1.9.0.0 (2018-06-10)
--------------------

* Git: :tag:`dejafu-1.9.0.0`
* Hackage: :hackage:`dejafu-1.9.0.0`

Changed
~~~~~~~

* (:issue:`190`) ``Test.DejaFu.Types.Throw`` and ``ThrowTo`` have a
  ``Bool`` parameter, which is ``True`` if the exception kills the
  thread.


1.8.0.0 (2018-06-03)
--------------------

* Git: :tag:`dejafu-1.8.0.0`
* Hackage: :hackage:`dejafu-1.8.0.0`

Changed
~~~~~~~

* (:issue:`258`) Length bounding is disabled by default.  This is not
  a breaking API change, but it is a breaking semantics change.


1.7.0.0 (2018-06-03)
--------------------

* Git: :tag:`dejafu-1.7.0.0`
* Hackage: :hackage:`dejafu-1.7.0.0`

Changed
~~~~~~~

* (:issue:`237`) ``Test.DejaFu.SCT.sctWeightedRandom`` and
  ``sctWeightedRandomDiscard`` no longer take the number of executions
  to use the same weights for as a parameter.

Removed
~~~~~~~

* (:issue:`237`) The deprecated function
  ``Test.DejaFu.Settings.swarmy``.


1.6.0.0 (2018-05-11)
--------------------

* Git: :tag:`dejafu-1.6.0.0`
* Hackage: :hackage:`dejafu-1.6.0.0`

Removed
~~~~~~~

* The deprecated module ``Test.DejaFu.Defaults``.


1.5.1.0 (2018-03-29)
--------------------

* Git: :tag:`dejafu-1.5.1.0`
* Hackage: :hackage:`dejafu-1.5.1.0`

Added
~~~~~

- (:issue:`210`) ``Test.DejaFu.Types.Weaken`` and ``Strengthen``
  newtype wrappers around discard functions, with ``Semigroup``,
  ``Monoid``, ``Contravariant``, and ``Divisible`` instances
  corresponding to ``weakenDiscard`` and ``strengthenDiscard``.


1.5.0.0 - No More 7.10 (2018-03-28)
-----------------------------------

* Git: :tag:`dejafu-1.5.0.0`
* Hackage: :hackage:`dejafu-1.5.0.0`

Miscellaneous
~~~~~~~~~~~~~

* GHC 7.10 support is dropped.  Dependency lower bounds are:

  * :hackage:`base`: 4.9
  * :hackage:`concurrency`: 1.5
  * :hackage:`transformers`: 0.5

* The upper bound on :hackage:`concurrency` is 1.6.


1.4.0.0 (2018-03-17)
--------------------

* Git: :tag:`dejafu-1.4.0.0`
* Hackage: :hackage:`dejafu-1.4.0.0`

Changed
~~~~~~~

- (:issue:`201`) ``Test.DejaFu.Conc.ConcT r n a`` drops its ``r``
  parameter, becoming ``ConcT n a``.

- (:issue:`201`) All functions drop the ``MonadConc`` constraint.

Removed
~~~~~~~

- (:issue:`201`) The ``MonadRef`` and ``MonadAtomicRef`` instances for
  ``Test.DejaFu.Conc.ConcT``.

- (:issue:`198`) The ``Test.DejaFu.Types.Killed`` thread action, which
  was unused.

Fixed
~~~~~

- (:issue:`250`) Add missing dependency for ``throwTo`` actions.


1.3.2.0 (2018-03-12)
--------------------

* Git: :tag:`dejafu-1.3.2.0`
* Hackage: :hackage:`dejafu-1.3.2.0`

Added
~~~~~

* (:issue:`183`) SCT settings for trace simplification:

  * ``Test.DejaFu.Settings.lequality``
  * ``Test.DejaFu.Settings.lsimplify``

* (:pull:`248`) ``Test.DejaFu.Utils.toTIdTrace`` to extract thread IDs
  from a trace.

* (:pull:`248`) SCT setting to make some recoverable errors fatal:
  ``Test.DejaFu.Settings.ldebugFatal``

Performance
~~~~~~~~~~~

* (:pull:`248`) Prune some unnecessary interleavings of ``CRef``
  actions in systematic testing when using sequential consistency.


1.3.1.0 (2018-03-11)
--------------------

* Git: :tag:`dejafu-1.3.1.0`
* Hackage: :hackage:`dejafu-1.3.1.0`

Added
~~~~~

* (:pull:`246`) ``Generic`` instances for:

  * ``Test.DejaFu.Types.ThreadId``
  * ``Test.DejaFu.Types.CRefId``
  * ``Test.DejaFu.Types.MVarId``
  * ``Test.DejaFu.Types.TVarId``
  * ``Test.DejaFu.Types.Id``
  * ``Test.DejaFu.Types.ThreadAction``
  * ``Test.DejaFu.Types.Lookahead``
  * ``Test.DejaFu.Types.TAction``
  * ``Test.DejaFu.Types.Decision``
  * ``Test.DejaFu.Types.Failure``
  * ``Test.DejaFu.Types.Bounds``
  * ``Test.DejaFu.Types.PreemptionBound``
  * ``Test.DejaFu.Types.FairBound``
  * ``Test.DejaFu.Types.LengthBound``
  * ``Test.DejaFu.Types.Discard``
  * ``Test.DejaFu.Types.MemType``
  * ``Test.DejaFu.Types.MonadFailException``

* (:pull:`246`) ``NFData`` instance for
  ``Test.DejaFu.Types.MonadFailException``

Fixed
~~~~~

* (:issue:`199`) Missing cases in the ``NFData`` instances for
  ``Test.DejaFu.Types.ThreadAction`` and ``TAction``


1.3.0.3 (2018-03-11)
--------------------

* Git: :tag:`dejafu-1.3.0.3`
* Hackage: :hackage:`dejafu-1.3.0.3`

Miscellaneous
~~~~~~~~~~~~~

* (:pull:`245`) The upper bound on :hackage:`exceptions` is <0.11.


1.3.0.2 (2018-03-11)
--------------------

* Git: :tag:`dejafu-1.3.0.2`
* Hackage: :hackage:`dejafu-1.3.0.2`

Fixed
~~~~~

* (:pull:`244`) Add missing dependency for ``setNumCapabilities``
  actions.


1.3.0.1 (2018-03-08)
--------------------

* Git: :tag:`dejafu-1.3.0.1`
* Hackage: :hackage:`dejafu-1.3.0.1`

Fixed
~~~~~

* (:pull:`242`) A compilation error when building with
  :hackage:`exceptions-0.9.0`.


1.3.0.0 (2018-03-06)
--------------------

* Git: :tag:`dejafu-1.3.0.0`
* Hackage: :hackage:`dejafu-1.3.0.0`

Deprecated
~~~~~~~~~~

* (:pull:`240`) ``Test.DejaFu.Settings.swarmy``


1.2.0.0 - The Settings Release (2018-03-06)
-------------------------------------------

* Git: :tag:`dejafu-1.2.0.0`
* Hackage: :hackage:`dejafu-1.2.0.0`

**Contributors:** :u:`qrilka` (:pull:`236`).

Added
~~~~~

* (:pull:`238`) A record-based approach to SCT configuration:

  * ``Test.DejaFu.Settings`` (re-exported from ``Test.Dejafu`` and
    ``Test.DejaFu.SCT``)
  * ``Test.DejaFu.Settings.Settings``
  * ``Test.DejaFu.Settings.defaultSettings``
  * ``Test.DejaFu.Settings.fromWayAndMemType``

  * Lenses:

    * ``Test.DejaFu.Settings.lway``
    * ``Test.DejaFu.Settings.lmemtype``
    * ``Test.DejaFu.Settings.ldiscard``
    * ``Test.DejaFu.Settings.learlyExit``
    * ``Test.DejaFu.Settings.ldebugShow``
    * ``Test.DejaFu.Settings.ldebugPrint``

  * Lens helpers:

    * ``Test.DejaFu.Settings.get``
    * ``Test.DejaFu.Settings.set``

  * Runners:

    * ``Test.DejaFu.SCT.runSCTWithSettings``
    * ``Test.DejaFu.SCT.runSCTWithSettings'``
    * ``Test.DejaFu.SCT.resultsSetWithSettings``
    * ``Test.DejaFu.SCT.resultsSetWithSettings'``

* (:pull:`238`) Settings-based test functions:

  * ``Test.DejaFu.autocheckWithSettings``
  * ``Test.DejaFu.dejafuWithSettings``
  * ``Test.DejaFu.dejafusWithSettings``
  * ``Test.DejaFu.runTestWithSettings``

Deprecated
~~~~~~~~~~

* (:pull:`238`) SCT function variants:

  * ``Test.DejaFu.SCT.runSCTDiscard``
  * ``Test.DejaFu.SCT.resultSetDiscard``
  * ``Test.DejaFu.SCT.runSCTDiscard'``
  * ``Test.DejaFu.SCT.resultSetDiscard'``
  * ``Test.DejaFu.SCT.sctBound``
  * ``Test.DejaFu.SCT.sctBoundDiscard``
  * ``Test.DejaFu.SCT.sctUniformRandom``
  * ``Test.DejaFu.SCT.sctUniformRandomDiscard``
  * ``Test.DejaFu.SCT.sctWeightedRandom``
  * ``Test.DejaFu.SCT.sctWeightedRandomDiscard``

* (:pull:`238`) The ``Test.DejaFu.Defaults`` module.  Import
  ``Test.DejaFu.Settings`` instead.

* (:pull:`238`) ``Test.DejaFu.dejafuDiscard``.

Removed
~~~~~~~

* (:pull:`238`) ``Test.DejaFu.Defaults.defaultDiscarder``, as the
  discard function is optional.


1.1.0.2 (2018-03-01)
--------------------

* Git: :tag:`dejafu-1.1.0.2`
* Hackage: :hackage:`dejafu-1.1.0.2`

Miscellaneous
~~~~~~~~~~~~~

* (:pull:`235`) The documentation for ``Test.DejaFu.Conc.dontCheck``
  and ``subconcurrency`` clarify that an illegal use does not
  necessarily cause a failing test.


1.1.0.1 (2018-02-26)
--------------------

* Git: :tag:`dejafu-1.1.0.1`
* Hackage: :hackage:`dejafu-1.1.0.1`

**Contributors:** :u:`qrilka` (:pull:`229`).

Miscellaneous
~~~~~~~~~~~~~

* The upper bound on :hackage:`exceptions` is <0.10.


1.1.0.0 (2018-02-22)
--------------------

* Git: :tag:`dejafu-1.1.0.0`
* Hackage: :hackage:`dejafu-1.1.0.0`

**Contributors:** :u:`qrilka` (:pull:`228`).

Added
~~~~~

* (:pull:`219`) The testing-only ``Test.DejaFu.Conc.dontCheck``
  function, and associated definitions:

  * ``Test.DejaFu.Types.DontCheck``
  * ``Test.DejaFu.Types.WillDontCheck``
  * ``Test.DejaFu.Types.IllegalDontCheck``
  * ``Test.DejaFu.Types.isIllegalDontCheck``

* (:pull:`219`) A snapshotting approach based on
  ``Test.DejaFu.Conc.dontCheck``:

  * ``Test.DejaFu.Conc.runForDCSnapshot``
  * ``Test.DejaFu.Conc.runWithDCSnapshot``
  * ``Test.DejaFu.Conc.canDCSnapshot``
  * ``Test.DejaFu.Conc.threadsFromDCSnapshot``

Changed
~~~~~~~

* (:pull:`219`) SCT functions automatically use the snapshotting
  mechanism when possible.


1.0.0.2 (2018-02-18)
--------------------

* Git: :tag:`dejafu-1.0.0.2`
* Hackage: :hackage:`dejafu-1.0.0.2`

**Contributors:** :u:`qrilka` (:pull:`214`).

Changed
~~~~~~~

* (:issue:`193`) Deterministically assign commit thread IDs.

Fixed
~~~~~

* (:issue:`189`) Remove an incorrect optimisation in systematic
  testing for ``getNumCapabilities`` and ``setNumCapabilities``.

* (:issue:`204`) Fix missed interleavings in systematic testing with
  some uses of STM.

* (:issue:`205`) Fix ``forkOS`` being recorded in an execution trace
  as if it were a ``fork``.

Miscellaneous
~~~~~~~~~~~~~

* (:pull:`180`) Doctest Haddock examples in ``Test.DejaFu`` and
  ``Test.DejaFu.Refinement``.

* (:pull:`185`, :pull:`215`) Check some more internal invariants and
  throw on error.

* (:pull:`214`) Remove unnecessary use of ``head``.


1.0.0.1 (2018-01-19)
--------------------

* Git: :tag:`dejafu-1.0.0.1`
* Hackage: :hackage:`dejafu-1.0.0.1`

Miscellaneous
~~~~~~~~~~~~~

* The upper bound on :hackage:`concurrency` is <1.5.


1.0.0.0 - The API Friendliness Release (2017-12-23)
---------------------------------------------------

* Git: :tag:`dejafu-1.0.0.0`
* Hackage: :hackage:`dejafu-1.0.0.0`

Added
~~~~~

* ``Test.DejaFu.alwaysSameOn`` and ``alwaysSameBy`` predicate helpers.

* ``Test.DejaFu.SCT.strengthenDiscard`` and ``weakenDiscard``
  functions to combine discard functions.

* (:issue:`124`) The ``Test.DejaFu.ProPredicate`` type, which contains
  both an old-style ``Predicate`` and a discard function.  It is also
  a ``Profunctor``, parameterised by the input and output types.

* (:issue:`124`) ``Test.DejaFu.alwaysNothing`` and
  ``somewhereNothing`` predicate helpers, like ``alwaysTrue`` and
  ``somewhereTrue``, to lift regular functions into a
  ``ProPredicate``.

* (:issue:`137`) The ``Test.DejaFu.Types.Id`` type.

* (:pull:`145`) Thread action and lookahead values for bound threads:

  * ``Test.DejaFu.Types.ForkOS``
  * ``Test.DejaFu.Types.IsCurrentThreadBound``
  * ``Test.DejaFu.Types.WillForkOS``
  * ``Test.DejaFu.Types.WillIsCurrentThreadBound``

* (:issue:`155`) ``Test.DejaFu.Types`` and ``Test.DejaFu.Utils``
  modules, each containing some of what was in ``Test.DejaFu.Common``.

Changed
~~~~~~~

* All testing functions require ``MonadConc``, ``MonadRef``, and
  ``MonadIO`` constraints.  Testing with ``ST`` is no longer possible.

* The ``Test.DejaFu.alwaysSame`` predicate helper gives the simplest
  trace leading to each distinct result.

* The ``MonadIO Test.DejaFu.Conc.ConcIO`` instance is now the more
  general ``MonadIO n => MonadIO (ConcT r n)``.

* (:issue:`121`) The chosen thread is no longer redundantly included
  in trace lookahead.

* (:issue:`123`) All testing functions in ``Test.DejaFu`` take the
  action to run as the final parameter.

* (:issue:`124`) All testing functions in ``Test.DejaFu`` have been
  generalised to take a ``ProPredicate`` instead of a ``Predicate``.

* (:issue:`124`) The ``Test.DejaFu.Predicate`` type is an alias for
  ``ProPredicate a a``.

* (:issue:`124`) The ``Test.DejaFu.Result`` type no longer includes a
  number of cases checked.

* (:issue:`137`) The ``Test.DejaFu.Types.ThreadId``, ``CRefId``,
  ``MVarId``, and ``TVarId`` types are now wrappers for an ``Id``.

* (:pull:`145`) If built with the threaded runtime, the main thread in
  a test is executed as a bound thread.

* (:issue:`155`) The ``Test.DejaFu.SCT.Discard`` type is defined in
  ``Test.DejaFu.Types``, and re-exported from ``Test.DejaFu.SCT``.

* (:issue:`155`) The ``Test.DejaFu.Schedule.tidOf`` and ``decisionOf``
  functions are defined in ``Test.DejaFu.Utils``, but not re-exported
  from ``Test.DejaFu.Schedule``.

Removed
~~~~~~~

* The ``IO`` specific testing functions:

  * ``Test.DejaFu.autocheckIO``
  * ``Test.DejaFu.dejafuIO``
  * ``Test.DejaFu.dejafusIO``
  * ``Test.DejaFu.autocheckWayIO``
  * ``Test.DejaFu.dejafuWayIO``
  * ``Test.DejaFu.dejafusWayIO``
  * ``Test.DejaFu.dejafuDiscardIO``
  * ``Test.DejaFu.runTestM``
  * ``Test.DejaFu.runTestWayM``

* The ``Test.DejaFu.Conc.ConcST`` type alias.

* The ``MonadBaseControl IO Test.DejaFu.Conc.ConcIO`` typeclass instance.

* The ``Test.DejaFu.alwaysTrue2`` function, which had confusing
  behaviour.

* The ``Test.DejaFu.Common.TTrace`` type synonym for ``[TAction]``.

* The ``Test.DejaFu.Common.preEmpCount`` function.

* Re-exports of ``Decision`` and ``NonEmpty`` from
  ``Test.DejaFu.Schedule``.

* (:issue:`155`) The ``Test.DejaFu.Common`` and ``Test.DejaFu.STM``
  modules.

Fixed
~~~~~

* In refinement property testing, a blocking interference function is
  not reported as a deadlocking execution.

Performance
~~~~~~~~~~~

* (:issue:`124`) Passing tests should use substantially less memory.

* (:issue:`168`) Prune some unnecessary interleavings of ``MVar``
  actions in systematic testing.

Miscellaneous
~~~~~~~~~~~~~

* The lower bound on :hackage:`concurrency` is >=1.3.


0.9.1.2 (2017-12-12)
--------------------

* Git: :tag:`dejafu-0.9.1.2`
* Hackage: :hackage:`dejafu-0.9.1.2`

Miscellaneous
~~~~~~~~~~~~~

* The upper bound on :hackage:`leancheck` is <0.8.


0.9.1.1 (2017-12-08)
--------------------

* Git: :tag:`dejafu-0.9.1.1`
* Hackage: :hackage:`dejafu-0.9.1.1`

Fixed
~~~~~

* (:issue:`160`) Fix an off-by-one issue with nested masks during
  systematic testing.


0.9.1.0 (2017-11-26)
--------------------

* Git: :tag:`dejafu-0.9.1.0`
* Hackage: :hackage:`dejafu-0.9.1.0`

Added
~~~~~

* ``MonadFail`` instance for ``Test.DejaFu.Conc.ConcT``.
* ``MonadFail`` instance for ``Test.DejaFu.STM.STMLike``.

Changed
~~~~~~~

* Pretty-printed traces display a pre-emption following a yield with a
  little "p".

Fixed
~~~~~

* Some incorrect Haddock ``@since`` comments.


0.9.0.3 (2017-11-06)
--------------------

* Git: :tag:`dejafu-0.9.0.3`
* Hackage: :hackage:`dejafu-0.9.0.3`

Fixed
~~~~~

* (:issue:`138`) Fix missed interleavings in systematic testing with
  some relaxed memory programs.


0.9.0.2 (2017-11-02)
--------------------

* Git: :tag:`dejafu-0.9.0.2`
* Hackage: :hackage:`dejafu-0.9.0.2`

Changed
~~~~~~~

* A fair bound of 0 prevents yielding or delaying.

Performance
~~~~~~~~~~~

* Prune some unnecessary interleavings of STM transactions in
  systematic testing.


0.9.0.1 (2017-10-28)
--------------------

* Git: :tag:`dejafu-0.9.0.1`
* Hackage: :hackage:`dejafu-0.9.0.1`

Fixed
~~~~~

* (:issue:`139`) Fix double pop of exception handler stack.


0.9.0.0 (2017-10-11)
--------------------

* Git: :tag:`dejafu-0.9.0.0`
* Hackage: :hackage:`dejafu-0.9.0.0`

Added
~~~~~

* Failure predicates (also exported from ``Test.DejaFu``):

  * ``Test.DejaFu.Common.isAbort``
  * ``Test.DejaFu.Common.isDeadlock``
  * ``Test.DejaFu.Common.isIllegalSubconcurrency``
  * ``Test.DejaFu.Common.isInternalError``
  * ``Test.DejaFu.Common.isUncaughtException``

* Thread action and lookahead values for ``threadDelay``:

  * ``Test.DejaFu.Common.ThreadDelay``
  * ``Test.DejaFu.Common.WillThreadDelay``

Changed
~~~~~~~

* The ``UncaughtException`` constructor for
  ``Test.DejaFu.Common.Failure`` now includes the exception value.

* Uses of ``threadDelay`` are no longer reported in the trace as a use
  of ``yield``.

Removed
~~~~~~~

* The ``Bounded``, ``Enum``, and ``Read`` instances for
  ``Test.DejaFu.Common.Failure``.


0.8.0.0 (2017-09-26)
--------------------

* Git: :tag:`dejafu-0.8.0.0`
* Hackage: :hackage:`dejafu-0.8.0.0`

Changed
~~~~~~~

* (:issue:`80`) STM traces now include the ID of a newly-created
  ``TVar``.

* (:issue:`106`) Schedulers are not given the execution trace so far.

* (:issue:`120`) Traces only include a single action of lookahead.

* (:issue:`122`) The ``Test.DejaFu.Scheduler.Scheduler`` type is now a
  newtype, rather than a type synonym.


0.7.3.0 (2017-09-26)
--------------------

* Git: :tag:`dejafu-0.7.3.0`
* Hackage: :hackage:`dejafu-0.7.3.0`

Added
~~~~~

* The ``Test.DejaFu.Common.threadNames`` function.

Fixed
~~~~~

* (:issue:`101`) Named threads which are only started by a pre-emption
  are shown in the pretty-printed trace key.

* (:issue:`118`) Escaping a mask by raising an exception correctly
  restores the masking state (#118).


0.7.2.0 (2017-09-16)
--------------------

* Git: :tag:`dejafu-0.7.2.0`
* Hackage: :hackage:`dejafu-0.7.2.0`

Added
~~~~~

* ``Alternative`` and ``MonadPlus`` instances for
  ``Test.DejaFu.STM.STM``.

Fixed
~~~~~

* The ``Eq`` and ``Ord`` instances for
  ``Test.DejaFu.Common.ThreadId``, ``CRefId``, ``MVarId``, and
  ``TVarId`` are consistent.

Miscellaneous
~~~~~~~~~~~~~

* The upper bound on :hackage:`concurrency` is <1.2.


0.7.1.3 (2017-09-08)
--------------------

* Git: :tag:`dejafu-0.7.1.3`
* Hackage: :hackage:`dejafu-0.7.1.3`

Fixed
~~~~~

* (:issue:`111`) Aborted STM transactions are correctly rolled back.

Performance
~~~~~~~~~~~

* (:issue:`105`) Use a more efficient approach for an internal
  component of the systematic testing.


0.7.1.2 (2017-08-21)
--------------------

* Git: :tag:`dejafu-0.7.1.2`
* Hackage: :hackage:`dejafu-0.7.1.2`

Fixed
~~~~~

* (:issue:`110`) Errors thrown with ``Control.Monad.fail`` are
  correctly treated as asynchronous exceptions.


0.7.1.1 (2017-08-16)
--------------------

* Git: :tag:`dejafu-0.7.1.1`
* Hackage: :hackage:`dejafu-0.7.1.1`

Performance
~~~~~~~~~~~

* (:issue:`64`) Greatly reduce memory usage in systematic testing when
  discarding traces by using an alternative data structure.

  * Old: ``O(max trace length * number of executions)``
  * New: ``O(max trace length * number of traces kept)``


0.7.1.0 - The Discard Release (2017-08-10)
------------------------------------------

* Git: :tag:`dejafu-0.7.1.0`
* Hackage: :hackage:`dejafu-0.7.1.0`

Added
~~~~~

* (:issue:`90`) A way to selectively discard results or traces:

  * Type: ``Test.DejaFu.SCT.Discard``
  * Functions: ``Test.DejaFu.SCT.runSCTDiscard``, ``resultsSetDiscard``,
    ``sctBoundDiscard``, ``sctUniformRandomDiscard``, and
    ``sctWeightedRandomDiscard``.

* (:issue:`90`) Discarding variants of the testing functions:

  * ``Test.DejaFu.dejafuDiscard``
  * ``Test.DejaFu.dejafuDiscardIO``

* (:issue:`90`) ``Test.DejaFu.Defaults.defaultDiscarder``.

Performance
~~~~~~~~~~~

* (:issue:`90`) The ``Test.DejaFu.SCT.resultsSet`` and ``resultsSet'``
  functions discard traces as they are produced, rather than all at
  the end.


0.7.0.2 (2017-06-12)
--------------------

* Git: :tag:`dejafu-0.7.0.2`
* Hackage: :hackage:`dejafu-0.7.0.2`

Changed
~~~~~~~

* Remove unnecessary typeclass constraints from
  ``Test.DejaFu.Refinement.check``, ``check'``, ``checkFor``, and
  ``counterExamples``.

Miscellaneous
~~~~~~~~~~~~~

* Remove an unnecessary dependency on :hackage:`monad-loops`.


0.7.0.1 (2017-06-09)
--------------------

* Git: :tag:`dejafu-0.7.0.1`
* Hackage: :hackage:`dejafu-0.7.0.1`

Performance
~~~~~~~~~~~

* The ``Test.DejaFu.Refinement.check``, ``check'``, and ``checkFor``
  functions no longer need to compute all counterexamples before
  showing only one.

* The above and ``counterExamples`` are now faster even if there is
  only a single counterexample in some cases.


0.7.0.0 - The Refinement Release (2017-06-07)
---------------------------------------------

* Git: :tag:`dejafu-0.7.0.0`
* Hackage: :hackage:`dejafu-0.7.0.0`

Added
~~~~~

* The ``Test.DejaFu.Refinement`` module, re-exported from
  ``Test.DejaFu``.

* The ``Test.DejaFu.SCT.sctUniformRandom`` function for SCT via random
  scheduling.

* Smart constructors for ``Test.DejaFu.SCT.Way`` (also re-exported
  from ``Test.DejaFu``):

  * ``Test.DejaFu.SCT.systematically``, like the old ``Systematically``.
  * ``Test.DejaFu.SCT.randomly``, like the old ``Randomly``.
  * ``Test.DejaFu.SCT.uniformly``, a new uniform (as opposed to weighted) random
    scheduler.
  * ``Test.DejaFu.SCT.swarmy``, like the old ``Randomly`` but which can use the
    same weights for multiple executions.

Changed
~~~~~~~

* The ``default*`` values are defined in ``Test.DejaFu.Defaults`` and
  re-exported from ``Test.DejaFu``.

* The ``Test.DejaFu.SCT.sctRandom`` function is now called
  ``sctWeightedRandom`` and can re-use the same weights for multiple
  executions.

Removed
~~~~~~~

* The ``Test.DejaFu.SCT.Way`` type is now abstract, so its
  constructors are no longer exported:

  * ``Test.DejaFu.SCT.Systematically``
  * ``Test.DejaFu.SCT.Randomly``

* The ``Test.DejaFu.SCT.sctPreBound``, ``sctFairBound``, and
  ``sctLengthBound`` functions.

Fixed
~~~~~

* (:issue:`81`) ``Test.DejaFu.Conc.subconcurrency`` no longer re-uses
  IDs.


0.6.0.0 (2017-04-08)
--------------------

* Git: :tag:`dejafu-0.6.0.0`
* Hackage: :hackage:`dejafu-0.6.0.0`

Changed
~~~~~~~

* The ``Test.DejaFu.Conc.Conc n r a`` type is ``ConcT r n a``, and has
  a ``MonadTrans`` instance.

* The ``Test.DejaFu.SCT.Way`` type is a GADT, and does not expose the
  type parameter of the random generator.

Removed
~~~~~~~

* The ``NFData`` instance for ``Test.DejaFu.SCT.Way``.

Miscellaneous
~~~~~~~~~~~~~

* ``Test.DejaFu.Common`` forms part of the public API.

* Every definition, class, and instance now has a Haddock ``@since``
  annotation.


0.5.1.3 (2017-04-05)
--------------------

* Git: :tag:`dejafu-0.5.1.3`
* Hackage: :hackage:`dejafu-0.5.1.3`

Miscellaneous
~~~~~~~~~~~~~

* The version bounds on :hackage:`concurrency` are 1.1.*.


0.5.1.2 (2017-03-04)
--------------------

* Git: :tag:`dejafu-0.5.1.2`
* Hackage: :hackage:`dejafu-0.5.1.2`

**Note:** this version was misnumbered! It should have caused a minor
 version bump!

Added
~~~~~

* ``MonadRef`` and ``MonadAtomicRef`` instances for
  ``Test.DejaFu.Conc.Conc`` using ``CRef``.

Fixed
~~~~~

* A long-standing bug where if the main thread is killed with a
  ``throwTo``, the throwing neither appears in the trace nor correctly
  terminates the execution.

Miscellaneous
~~~~~~~~~~~~~

* The upper bound on :hackage:`concurrency` is <1.1.1.


0.5.1.1 (2017-02-25)
--------------------

* Git: :tag:`dejafu-0.5.1.1`
* Hackage: :hackage:`dejafu-0.5.1.1`

Fixed
~~~~~

* Fix using incorrect correct scheduler state after a `subconcurrency`
  action.

* Fix infinite loop in SCT of subconcurrency.


0.5.1.0 (2017-02-25)
--------------------

* Git: :tag:`dejafu-0.5.1.0`
* Hackage: :hackage:`dejafu-0.5.1.0`

Added
~~~~~

* ``NFData`` instances for:

  * ``Test.DejaFu.Result``
  * ``Test.DejaFu.Common.ThreadId``
  * ``Test.DejaFu.Common.CRefId``
  * ``Test.DejaFu.Common.MVarId``
  * ``Test.DejaFu.Common.TVarId``
  * ``Test.DejaFu.Common.IdSource``
  * ``Test.DejaFu.Common.ThreadAction``
  * ``Test.DejaFu.Common.Lookahead``
  * ``Test.DejaFu.Common.ActionType``
  * ``Test.DejaFu.Common.TAction``
  * ``Test.DejaFu.Common.Decision``
  * ``Test.DejaFu.Common.Failure``
  * ``Test.DejaFu.Common.MemType``
  * ``Test.DejaFu.SCT.Bounds``
  * ``Test.DejaFu.SCT.PreemptionBound``
  * ``Test.DejaFu.SCT.FairBound``
  * ``Test.DejaFu.SCT.LengthBound``
  * ``Test.DejaFu.SCT.Way``
  * ``Test.DejaFu.STM.Result``

* ``Eq``, ``Ord``, and ``Show`` instances for
  ``Test.DejaFu.Common.IdSource``.

* Strict variants of ``Test.DejaFu.SCT.runSCT`` and ``resultsSet``:
  ``runSCT'`` and ``resultsSet'``.


0.5.0.2 (2017-02-22)
--------------------

* Git: :tag:`dejafu-0.5.0.2`
* Hackage: :hackage:`dejafu-0.5.0.2`

**Note:** this version was misnumbered! It should have caused a major
 version bump!

Added
~~~~~

* ``StopSubconcurrency`` constructor for
  ``Test.DejaFu.Common.ThreadAction``.

Changed
~~~~~~~

* A ``Test.DejaFu.Common.StopConcurrency`` action appears in the
  execution trace immediately after the end of a
  ``Test.DejaFu.Conc.subconcurrency`` action.

Fixed
~~~~~

* A ``Test.DejaFu.Conc.subconcurrency`` action inherits the number of
  capabilities from the outer computation.

Miscellaneous
~~~~~~~~~~~~~

- ``Test.DejaFu.SCT`` compiles with ``MonoLocalBinds`` enabled
  (implied by ``GADTs`` and ``TypeFamilies``), which may be relevant
  to hackers.


0.5.0.1 (2017-02-21)
--------------------

* Git: :tag:`dejafu-0.5.0.1`
* Hackage: :hackage:`ps!**`

Fixed
~~~~~

* ``readMVar`` is considered a "release action" for the purposes of
  fair-bounding.


0.5.0.0 - The Way Release (2017-02-21)
--------------------------------------

* Git: :tag:`dejafu-0.5.0.0`
* Hackage: :hackage:`dejafu-0.5.0.0`

Added
~~~~~

* ``Eq`` instances for ``Test.DejaFu.Common.ThreadAction`` and
  ``Lookahead``.

* Thread action and lookahead values for ``tryReadMVar``:

  * ``Test.DejaFu.Common.TryReadMVar``
  * ``Test.DejaFu.Common.WillTryReadMVar``

* The testing-only ``Test.DejaFu.Conc.subconcurrency`` function.

* SCT through weighted random scheduling:
  ``Test.DejaFu.SCT.sctRandom``.

* The ``Test.DejaFu.SCT.Way`` type, used by the new functions
  ``runSCT`` and ``resultsSet``.

Changed
~~~~~~~

* All the functions which took a ``Test.DejaFu.SCT.Bounds`` now take a
  ``Way`` instead.

Fixed
~~~~~

* Some previously-missed ``CRef`` action dependencies are no longer
  missed.

Miscellaneous
~~~~~~~~~~~~~

* The version bounds on :hackage:`concurrency` are 1.1.0.*.

* A bunch of things were called "Var" or "Ref", these are now
  consistently "MVar" and "CRef".

* Significant performance improvements in both time and space.

* The :hackage:`dpor` package has been merged back into this, as it
  turned out not to be very generally useful.


0.4.0.0 - The Packaging Release (2016-09-10)
--------------------------------------------

* Git: :tag:`dejafu-0.4.0.0`
* Hackage: :hackage:`dejafu-0.4.0.0`

Added
~~~~~

* The ``Test.DejaFu.runTestM`` and ``runTestM'`` functions.

* The ``Test.DejaFu.Conc.runConcurrent`` function.

* The ``Test.DejaFu.STM.runTransaction`` function.

* The ``Test.DejaFu.Common`` module.

Changed
~~~~~~~

* The ``Control.*`` modules have all been split out into a separate
  :hackage:`concurrency` package.

* The ``Test.DejaFu.Deterministic`` module has been renamed to
  ``Test.DejaFu.Conc``.

* Many definitions from other modules have been moved to the
  ``Test.DejaFu.Common`` module.

* The ``Test.DejaFu.autocheck'`` function takes the schedule bounds as
  a parameter.

* The ``Test.DejaFu.Conc.Conc`` type no longer has the STM type as a
  parameter.

* The ``ST`` specific functions in ``Test.DejaFu.SCT`` are polymorphic
  in the monad.

* The termination of the main thread in execution traces appears as a
  single ``Stop``, rather than the previous ``Lift, Stop``.

* Execution traces printed by the helpful functions in ``Test.DejaFu``
  include a key of thread names.

Removed
~~~~~~~

* The ``Test.DejaFu.runTestIO`` and ``runTestIO'`` functions: use
  ``runTestM`` and ``runTestM'`` instead.

* The ``Test.DejaFu.Conc.runConcST`` and ``runConcIO`` functions: use
  ``runConcurrent`` instead.

* The ``Test.DejaFu.STM.runTransactionST`` and ``runTransactionIO``
  functions: use ``runTransaction`` instead.

* The ``IO`` specific functions in ``Test.DejaFu.SCT``.



0.3.2.1 (2016-07-21)
--------------------

* Git: :tag:`dejafu-0.3.2.1`
* Hackage: :hackage:`dejafu-0.3.2.1`

Fixed
~~~~~

* (:issue:`55`) Fix incorrect detection of deadlocks with some nested
  STM transactions.


0.3.2.0 (2016-06-06)
--------------------

* Git: :tag:`dejafu-0.3.2.0`
* Hackage: :hackage:`dejafu-0.3.2.0`

Fixed
~~~~~

* (:issue:`40`) Fix missing executions with daemon threads with
  uninteresting first actions.  This is significantly faster with
  :hackage:`dpor-0.2.0.0`.

Performance
~~~~~~~~~~~

* When using :hackage:`dpor-0.2.0.0`, greatly improve dependency
  inference of exceptions during systematic testing.

* Improve dependency inference of STM transactions during systematic
  testing.


0.3.1.1 (2016-05-26)
--------------------

* Git: :tag:`dejafu-0.3.1.1`
* Hackage: :hackage:`dejafu-0.3.1.1`

Miscellaneous
~~~~~~~~~~~~~

* Now supports GHC 8.


0.3.1.0 (2016-05-02)
--------------------

* Git: :tag:`dejafu-0.3.1.0`
* Hackage: :hackage:`dejafu-0.3.1.0`

Fixed
~~~~~

* Fix inaccurate counting of pre-emptions in an execution trace when
  relaxed memory commit actions are present.


0.3.0.0 (2016-04-03)
--------------------

* Git: :tag:`dejafu-0.3.0.0`
* Hackage: :hackage:`dejafu-0.3.0.0`

**The minimum supported version of GHC is now 7.10.**

I didn't write proper release notes, and this is so far back I don't
really care to dig through the logs.


0.2.0.0 (2015-12-01)
--------------------

* Git: :tag:`0.2.0.0`
* Hackage: :hackage:`dejafu-0.2.0.0`

I didn't write proper release notes, and this is so far back I don't
really care to dig through the logs.


0.1.0.0 - The Initial Release (2015-08-27)
------------------------------------------

* Git: :tag:`0.1.0.0`
* Hackage: :hackage:`dejafu-0.1.0.0`

Added
~~~~~

* Everything.
