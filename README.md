## Scheduler

<details>
<summary>Can you deploy multiple schedulers?</summary><br><b>

Yes, it is possible. You can run another pod with a command similar to:

```
spec:
  containers:
  - command:
    - kube-scheduler
    - --address=127.0.0.1
    - --leader-elect=true
    - --scheduler-name=some-custom-scheduler
...
```
</b></details>

<details>
<summary>Assuming you have multiple schedulers, how to know which scheduler was used for a given Pod?</summary><br><b>

Running `kubectl get events` you can see which scheduler was used.
</b></details>

<details>
<summary>You want to run a new Pod and you would like it to be scheduled by a custom scheduler. How to achieve it?</summary><br><b>

Add the following to the spec of the Pod:

```
spec:
  schedulerName: some-custom-scheduler
```
</b></details>
