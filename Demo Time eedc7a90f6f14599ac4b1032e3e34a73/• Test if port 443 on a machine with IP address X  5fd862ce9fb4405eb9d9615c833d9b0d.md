# • Test if port 443 on a machine with IP address X.X.X.X is reachable.

You can test if port 443 on a machine with IP address X.X.X.X is reachable using the `telnet` or `nc` (netcat) command. Here are examples using both methods:

Using `telnet`:

```bash
telnet X.X.X.X 443

```

Using `nc` (netcat):

```bash
nc -zv X.X.X.X 443

```

In both cases, replace `X.X.X.X` with the actual IP address you want to test. If the port is reachable, you will see a successful connection message. If it's not reachable, you'll get an error message indicating that the connection was refused or timed out.