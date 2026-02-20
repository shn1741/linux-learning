# Starting Processes in the Future

Linux provides multiple tools to schedule processes to run in the future or after a delay.

---

## at
Used to schedule a command to run **once** at a specific time in the future.

- Jobs are executed only once
- Suitable for one-time tasks

## Method 



    Create the file testat.sh containing:

    #!/bin/bash
    date > /tmp/datestamp

    and then make it executable and queue it up with at:

    $ chmod +x testat.sh
    $ at now + 1 minute -f testat.sh

    You can see if the job is queued up to run with atq:

    $ atq
    17      Wed Apr 22 08:55:00 2015 a student

    Make sure the job actually ran:

    $ cat /tmp/datestamp
    Wed Apr 22 08:55:00 CDT 2015

    What happens if you take the /tmp/datestamp out of the command? Hint: Type mail if not prompted to do so!

    Interactively, it is basically the same procedure. Just queue up the job with:

    $ at now + 1 minute
    at> date > /tmp/datestamp
    CTRL-D
    $ atq

---

## cron
Used to schedule **recurring tasks**.

- Jobs are defined using cron expressions
- Commonly used for maintenance, backups, and automation
- Runs continuously as a daemon


## Method

	Set up a cron job to do a simple task every day at 10 AM. Create a file named mycrontab with the following content:

	0 10 * * * /tmp/myjob.sh

	and then create /tmp/myjob.sh containing:

	#!/bin/bash
	echo Hello I am running $0 at $(date)

	and make it executable:

	$ chmod +x /tmp/myjob.sh

	Put it in the crontab system with:

	$ crontab mycrontab

	and verify it was loaded with:

	$ crontab -l

	0 10 * * * /tmp/myjob.sh
	$ sudo ls -l /var/spool/cron/student
	-rw------- 1 student student 25 Apr 22 09:59 /var/spool/cron/student
	$ sudo cat /var/spool/cron/student
	0 10 * * * /tmp/myjob.sh

	NOTE: If you don't really want this running every day, printing out messages like:

	Hello I am running /tmp/myjob.sh at Wed Apr 22 10:03:48 CDT 2015

	and mailing them to you, you can remove it with:

	$ crontab -r

	If the machine is not up at 10 AM on a given day, anacron will run the job at a suitable time.

---

## anacron
Designed for systems that are **not always running**.

- Ensures scheduled jobs run even if the system was powered off
- Commonly used on laptops and desktops

---

## sleep
Pauses execution of a command for a specified amount of time.

- Often used in scripts
- Useful for delaying execution
