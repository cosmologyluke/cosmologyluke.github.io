---
layout: page
title: ipsa
description: power systems analysis tool development with tnei
img: /assets/img/Circle.jpg
importance: 3
category: work
---

_IPSA_ (Interactive Power Systems Analysis) is one of the longest running power systems analysis tools in the world. Developed by PhD researchers at UMIST in the 1970s, it boasts the innovation of the _fast decoupled Newton Raphson iterative method_ which speeds up power flow calculations owing to the decoupling assumptions that can be made for most power systems. Furthermore, IPSA was the first power systems analysis tool to be developed with a simple, easy-to-use GUI that allows the user to visualise the network in realtime and constructively design changes and examine the consequences on the underlying calculations. Full details on what the code is and how to use it can be found at the [website](http://www.ipsa-power.com).

---
<div class="row mt-3">
  <div class="col-sm mt-3 mt-md-0">
      <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/ipsa_ui.png' | relative_url }}" alt="" title="IPSA UI designed for the 2022 IPSA v2.10.0 release"/>
  </div>
</div>
<div class="caption">
  <em>The user interface for the IPSA program. This is the newest version of the interface developed for IPSA 2.10.0.</em>
</div>
---
Built up from a strong Fortran backend engine to calculate the load flow, fault level and other modular calculations; IPSA has many features that allow the user to analyse networks in many different ways. It has even been wrapped into an effective Python API called _PyIPSA_ which can efficiently be called from script or Python shell in order to perform recursive and more detailed simulations on big networks.

---
<div class="row mt-3">
  <div class="col-sm mt-3 mt-md-0">
    <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/pyipsa.png' | relative_url }}" alt="" title="Snapshot of the python scripting interface PyIPSA" />
  </div>
</div>
<div class="caption">
  <em>Script snippet of PyIPSA, the Python interface that allows users to script detailed simulations using the IPSA backend.</em>
</div>
---
### IPSA 2.10.0

For IPSA 2.10.0, released in May 2022, we have developed several exciting new enhancements. We present the _ArcFlash 2.0_ module that includes modernised, updated arc flash calculations penned to IEEE standards as well as an easier to use interface for the new arc flash parametrisation and even some scripting features that allow for broader arc flash testing across the entire network. This entire module was embedded into the IPSA C++ codebase with a reliable and optimised version of the IEEE-1584 polynomial calculations and interpolation.

One of the biggest inclusions in this new release is the arrival of many data conversion tools, none moreso than _CIM2IPSA_: the interface between IPSA and the [_Common Information Model_](https://ieeexplore.ieee.org/document/5772503?arnumber=5772503) (CIM), a framework designed by the electric power industry and adopted by the IEC. Discussions on the origin of CIM and where the model arose from in the context of the power industry can be found [here](https://site.ieee.org/pes-enews/2015/12/10/a-brief-history-the-common-information-model/). This UML based framework is now fully compatible with IPSA 2 and has state-of-the-art mappings to CGMES 2.4.15 standard network profiles. In the next release of IPSA, we plan to improve this tool with further features. The IPSA team developed a standalone patch onto IPSA that builds the network topology infrastructure required for a 1-1 correspondence between CIM and IPSA, something we are very proud of.

The _IPSA User Interface_ has also undergone a makeover in this newest release. By utilising some of the more detailed features of the [Qt Framework](https://www.qt.io/?hsLang=en), we have added another layer of personalisation and wrestled several tenets of IPSA into the 21st century. Further work includes making a more ergonomic design to the UI panels and also tidying up a huge number of UI based bugs that would hinder the user's experience - no longer!

### Upcoming features

For futuristic IPSA development, we are focussing on building in new components, adding in advanced runtime methods and even probabilistic featurettes - this may even lean into some of the statistical methods that I have already worked on in my PhD!
We've also developed the UI to be even more user-friendly, added in some wider functionality for the user to be applied in the harmonics applications and even some higher-level technology types in our DC networks package!!

For more exciting news about our new directions in IPSA, we are holding a [User Group Meeting](https://www.linkedin.com/events/ipsaugm20226958775897554354176/) for our user-base to connect with our current clients and get to know the names and faces that use IPSA.
