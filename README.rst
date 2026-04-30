##################################
frontend-app-authn (OpenLMS fork)
##################################

.. note::

   This is a fork of `openedx/frontend-app-authn`_, maintained by the OpenLMS team
   (`opswerks-swg`_). We forked because our stakeholders' customization
   requirements exceed what is achievable through the standard Open edX
   customization mechanisms (branding, theming, site configuration, plugins,
   etc.).

   We intend to periodically sync this fork with upstream. For the canonical
   description of the MFE's purpose, architecture, and full environment-variable
   reference, refer to the `upstream README`_.

.. _openedx/frontend-app-authn: https://github.com/openedx/frontend-app-authn
.. _opswerks-swg: https://github.com/opswerks-swg
.. _upstream README: https://github.com/openedx/frontend-app-authn/blob/master/README.rst

********
Purpose
********

This micro-frontend handles login, registration, password reset, and
progressive profiling for Open edX:

- Register page
- Login page
- Forgot password page
- Reset password page
- Progressive profiling page

*************************
Differences from Upstream
*************************

Record intentional divergence from upstream here so contributors can tell
deliberate changes from drift.

- ``@edx/brand`` is pinned to ``npm:@openedx/brand-openedx@^1.2.3`` (commit ``211cfcb``).
- *Add further OpenLMS-specific deltas (branding overrides, added pages, removed
  features, patched dependencies, etc.) as they land.*
- *EXAMPLE ONLY* 

***************
Getting Started
***************

Prerequisites and general setup match upstream; `Tutor`_ is the recommended
development environment (see the `tutor-mfe docs`_).

.. _Tutor: https://github.com/overhangio/tutor
.. _tutor-mfe docs: https://github.com/overhangio/tutor-mfe?tab=readme-ov-file#mfe-development

1. Clone this fork:

   .. code-block:: bash

      git clone git@github.com:opswerks-swg/OpenLMS-MFE-frontend-app-authn.git

2. Use the Node version specified in ``.nvmrc`` (via ``nvm`` for convenience).

3. Install dependencies:

   .. code-block:: bash

      cd OpenLMS-MFE-frontend-app-authn && npm install

4. The default port is ``1999``. To change it, update ``PORT=1999`` in every
   ``.env.*`` file.

5. Start the dev server at ``localhost:1999``:

   .. code-block:: bash

      npm run dev

For enabling SSO locally, see `docs/how_tos/enable_social_auth.rst
<docs/how_tos/enable_social_auth.rst>`_.

*********************
Environment Variables
*********************

All environment variables documented in the `upstream README`_ apply to this
fork. Document OpenLMS-specific variables below as they are introduced.

.. list-table:: OpenLMS-specific Environment Variables
   :widths: 30 50 20
   :header-rows: 1

   * - Name
     - Description / Usage
     - Example
   * - *(none yet)*
     -
     -

*********************
Syncing with Upstream
*********************

Document the chosen sync strategy here — which upstream branch/tag we track,
merge vs. rebase policy, who owns sync cadence, and any known conflict
hotspots.

A typical sync looks like:

.. code-block:: bash

   git remote add upstream git@github.com:openedx/frontend-app-authn.git
   git fetch upstream
   git checkout master
   git merge upstream/master   # or rebase, per the chosen policy

*********************
Maintainers & Support
*********************

Maintained by the OpenLMS team at `opswerks-swg`_.

- **Fork-specific issues** (OpenLMS customizations, sync problems, fork CI):
  file in this repository's issue tracker.
- **General / upstream issues** (bugs present in ``openedx/frontend-app-authn``
  itself): file at https://github.com/openedx/frontend-app-authn/issues.

*********************
License & Attribution
*********************

Original work is © edX / Open edX contributors, licensed under AGPL-3.0.
Modifications in this fork are © OpenLMS / opswerks-swg, also licensed under
AGPL-3.0.

See `LICENSE <LICENSE>`_ for details.

Reporting Security Issues
=========================

Please do not report security issues in public. For issues affecting upstream
Open edX, email security@openedx.org. For issues specific to this fork's
customizations, contact the OpenLMS maintainers privately.
