# Approach to troubleshooting performance, defects, anything

Some general ideas and approaches I've learned and/or applied while investigating various things in software and computing.

* Try to rule out the different variables to find the main culprit.
* Add more logging or tracing.
* Correlate with other systems to see what they can reveal.
* Know your tools.
* Add diagnostics code to exercise components independently of others.
* Replace various parts with different implementations to spot differences.
* Try to reproduce the problem with a small case.
