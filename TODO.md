# Tasks
* Some way of automating AppArmor profiles would be nice. `bane` would be useful for this, but is there any way to automate it? Maybe a controller or operator.
* Some way of checking image signatures to prevent supply chain attacks. I think kyverno can handle this.
* Use Apprise instead of gotify-only alerting. Currently I use gotify for `kube-bench` and `kube-hunter`
* More reporting, but I think I'll need something very specific, like controllers (also, implement with Apprise):
  * `falco` reporting
  * `trivy` reporting
  * Reporting on failed kyverno policies. Kyverno already saves reports of the `PolicyReport` kind (`k get policyreports`). Automate sending these to Apprise (likely using a controller)
* `kube-hunter` doesn't seem very useful in its state, since running it as a pod only gives the vulnerabilities you'd be exposed to if a pod gets compromised. Of course you could secure the pod, but what's the point? It only tells you that that pod has no vulnerabilities, and gives you nothing about the rest of the system. See if I can run it to check for vulnerabilities as an external attacker.
