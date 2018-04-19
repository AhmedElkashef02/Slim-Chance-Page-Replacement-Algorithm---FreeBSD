# Slim-Chance-Page-Replacement-Algorithm-FreeBSD
Implementing a FreeBSD Slim Chance Page Replacement Algorithm.
Experimenting with the FreeBSD pageout daemon to modify how it selects pages for replacement in page faults, and to see how effective the policy is.

## Automated Setup
- Run the executable file, which will remove and replace the new page replacement algorithm. build and install a new kernel for you. Use:`./SCA_setup`
- Reboot

## Steps to achieve Slim Chance Algorithm:
- Change the way that inactive and invalid pages are put in the free list, so instead of them being placed in the front, we will place them in the rear of the list.
- When you move a page to the inactive list, it goes on the front instead of the rear.
- Instead of subtracting from the activity count, you will divide it by two and move it to the front of the active list instead of to the rear.

## Stress Testing:
- Clear the message file in /var/log before stress testing: `cp /dev/null /var/log/messages`.
- Define a clear start before the stress testing by writing this to the log: `START_LOG`.
- Using 15 workers, initiate the stress testing: `stress --vm 15 --timeout 60s --vm-keep`.
- Define a clear end to the stress testing by writing this to the log: `END_LOG`.
