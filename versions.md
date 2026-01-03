# Work with IBM i version info

## 1.0.1.13
Intial 2026 release of Work with IBM i with support for IBM i Access connectivity. (Ports 446-449, 8470-8479O.

```All older SSH based versions of Work with IBM i are immediately deprecated.``` We might re-add SSH support later but direct 
connectivity works so much better and is already available on most IBM i systems.

## 1.0.1.14
Updated date handling in member and IFS file lists to accomodate Non-US regions.

Resolved issue with date formatting errors: 
Non-US user was getting ```String was not recognized as a valid DateTime``` error message popup 
when source members were listed using "Use DSPFD for members" setting.

Added error handling around date formatting routines to handle date formatting oddities.

Workaround in prev version (V1.0.1.13): Uncheck the ```Use DSPFD for members``` checkbox value 
and see if the issue resolves itself. Or upgrade to V1.0.1.14 or above.









