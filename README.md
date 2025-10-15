# cf-multiprocess-sample-python
CF multiprocess sample app for python

### Deploying

Push the app:

`cf push`


By default, only the web process starts.
To start the worker process as well:

`cf scale multiprocess-sample -p worker -i 1`


Verify:
```
cf app multiprocess-sample
cf processes multiprocess-sample
```

You’ll see both web and worker processes listed.

📋 Notes

Each process runs in its own container (CF “instance”).

The web process is bound to routes and receives HTTP traffic.

The worker process runs independently — useful for background jobs, message queue consumers, etc.

Logs for each process type can be viewed with:

`cf logs multiprocess-sample --recent`
