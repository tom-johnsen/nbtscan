# Changelog

Version 1.6 - July 2023 (Forked)

! Forked version

- Fixed numerous C99 violations
- Fixed missing header declarations
- Fixed formatting
- Cleaned up source code
- Builds and tests ok on OS X arm64 (M1)

Version 1.5.1 - June 2003

- Fixed segmentation fault when using -f option (noticed by Brian Lovrin)
- Fixed printing ugliness (noticed by Darren Critchley)
- Changed version number :) (1.5 said that it is 1.0.3 - now it proudly says 1.5.1)

Version 1.5 - May 2002

- Fixed a bug in displaying of 15-character NetBIOS names (15th character wasn't displayed). Bug reported by Tom Kustner (<Tom.Kustner@mortgage.wellsFargo.COM>), Kenny Breck (<KCBreck@NetZero.net>) and Richard IJzermans (<richard.ijzermans@lgphilips-displays.com>)
- Fixed a bug in interpreting netmask /32 and /0. Patch provided by Thomas Poindessous (<thomas@poindessous.com>) for Debian Linux
- List of hosts to scan can now be read from stdin as well as from file. Suggested by Kevin Kadow (<kadokev@msg.net>)
- Fixed a bug in timing. (nbtscan waited for two seconds after scanning not doing anything). Reported by Ceri Hopkins (<ceri@sandc.demon.co.uk>)
- Nbtscan now works on Darwin. Patches provided by Mohammad A. Haque (<mhaque@haque.net>)
- timeout option -t is now in milliseconds, not seconds
- Fixed some Solaris portability problems. Patches provided by Petter Reinholdtsen (<pere@hungry.com>)

Version 1.0.3 - February 2002

- NBTscan now returns meaningful exit code (patch by James Troup for Debian Linux)
- Added /etc/hosts and lmhosts format output (suggested by Anahuac de Paula Gil and Sigmund Baginov)
- configure script now honours --prefix argument (patch by Petter Reinholdtsen)
- Error messages now include IP address that caused error
- NBTscan accepts a file with a list of IP addresses to scan (suggested by Omas Jakobsson)
- Service number is printed for unknown NetBIOS services in -h mode (suggested by Dan Wright)
- Fixed some compile-time warnings on Linux
- Corrected some typos

Version 1.0.2 - March 30, 2000

- Added retransmits (-m option) (Several people asked)
- Added output bandwidth throttling (-b option) (Suggested
  by Jason Garman <jgarman@wedgie.org>)
- Rewrote sending queries and receiving answers part for more
  reliable scanning of large blocks of addresses. (Suggested
  by Jason Garman <jgarman@wedgie.org>)
- Added script-friendly output option (-s) (Suggested by
  Patrick Heim <Maldoror@Worldnet.att.net>)
- Added printing of human-readable NetBIOS service names (-h)
  (Suggested by Patrick Heim <Maldoror@Worldnet.att.net>)
- Added -q command line option that suppresses printing
  banners and error messages. (Suggested by Sam Bayne
  <sbayne@sccd.ctc.edu>)
- Rewrote parse_response completely. This allows for better
  parsing of Samba servers' responses. (Bug reported by
  Sam Bayne <sbayne@sccd.ctc.edu>)
- Added -d command line option which makes whole packets
  get printed
- Various cosmetic improvements including fixing some
  spelling errors

Version 1.0.1 - May 5, 1999

- Fixed incorrect parsing of MAC address in parse_response()
  which made last byte of MAC addresses appear as 00. Bug
  pointed by Joseph Moon.  
- Changed message saying "Warning: -r option not supported
  under NT." to more accurate saying: "Warning: -r option not
  supported under Windows."
- Corrected a typo in README.
