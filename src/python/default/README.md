# Changing default python version to 3

Command is
```
update-alternatives: --install needs <link> <name> <path> <priority>
```

So run
```
sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.4 1
```

Make sure to change the <path> accordingly. you can add another python version say `python3.6` with priority 2 as well

Then run 
```
sudo update-alternatives --config python
```

or
```
sudo update-alternatives  --set python /usr/bin/python3.6
```