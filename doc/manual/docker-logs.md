### docker:logs

With this goal it is possible to print out the logs of containers
started from images configured in this plugin. By default only the
latest container started is printed, but this can be changed with a
property. The format of the log output is influenced by run
configuration of the configured images. The following system
properties can the behaviour of this goal:

* **docker.logAll** if set to `true` the logs of all containers
  created from images configured for this plugin are printed. The
  container id is then prefixed before every log line. These images
  can contain many containers which are already stopped. It is
  probably a better idea to use `docker logs` diretly from the command
  line. 
* **docker.follow** if given will wait for subsequent log output until
  CRTL-C is pressed. This is similar to the behaviour of `docker logs
  -f` (or `tail -f`).
* **docker.image** can be used to restrict the set of images for which
  log should be fetched. This can be a comma separated list of image
  or alias names. 
* **docker.logDate** specifies the log date to use. See
  "[Log configuration](#log-configuration)" above for the available
  formats. 

Example:

````
$ mvn docker:logs -Ddocker.follow -Ddocker.logDate=DEFAULT
````
