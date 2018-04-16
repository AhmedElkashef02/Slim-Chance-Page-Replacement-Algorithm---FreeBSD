# Slim-Chance-Page-Replacement-Algorithm-FreeBSD
Implementing a FreeBSD Slim Chance Page Replacement Algorithm.
Experimenting with the FreeBSD pageout daemon to modify how it selects pages for replacement in page faults, and to see how effective the policy is.

## Automated Setup
- Run the executable file, which will remove and replace the new page replacement algorithm. Use:`./SCA_setup`
- Change Directory using `cd /usr/src/sys/amd64/conf`
- Copy the existence Kernel using `cp GENERIC ASGN3`
- Change Directory using `cd /usr/src/`
- Build the Kernel: `make buildkernel KERNCONF=ASGN3` Note: this may take time
- Install the Kernel: `make installkernel KERNCONF=ASGN3`
- Reboot

