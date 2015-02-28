This project demonstrates how Message Queues work on POSIX systems. It create a central process with initialization temperature. It then create 4 child (external) processes, all with their own initialization temperature. The central process broadcasts (through message queues) its temperature to the external processes, which then use that temperature and their own temperature to calculate a new temperature value. This value is then sent back to the central process. The central process then calculates a new temperature for itself using it's current temperature value as well as the 4 temperatures it just received. This process continue until every child process calculates the same temperature 2x in a row.