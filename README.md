# secur8
A collection of sensible defaults for Kubernetes security. Most of these, I've seen recommended everywhere and should be minimally invasive:

* `kube-bench` cronjob for scanning for vulnerabilities.
* `kube-hunter` cronjob for scanning for vulnerabilities. I've got this one disabled as I'm not sure about whether it's useful.
* `kyverno-policies` to ensure security good practices. This could be improved upon but I've found it pretty useful to prevent some careless mistakes.
* `network-policies`: Actually this one is pretty invasive. A default network policy to forbid all traffic. Allowing only:
  * kubelet-to-pod traffic. Otherwise probes won't work.
  * pod-to-dns traffic. Minimally dangerous and widely necessary.
