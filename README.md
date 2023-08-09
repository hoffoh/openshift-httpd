Openshift templates with apache web server

[CONTENT]
------------------------------

/custom_image_dockerfile
  - Dockerfile

/custom_template_pvc
  - httpd_default_sc.json
  - httpd_gp2csi_sc.json
  - httpd_gp3csi_sc.json
  - httpd_nooba_sc.json

/images
  - wp.jpg

/index_git_image
  - index.html

/index_localfiles
  - index.html

README.md


[DETAILS]
------------------------------
* custom_image_dockerfile
  - Dockerfile that copy to container index.html and wp.jpg from git, need to manual expose svc to get route
  - Usage: "oc new-app --name echo https://github.com/hoffoh/openshift-httpd --context-dir custom_image_dockerfile/"

* custom_template_pvc
  - Creates a PVC and pod, svc and route, index.html and wp.jpg are pointed on git
  - Usage: "oc new-app --name default_sc -f https://raw.githubusercontent.com/hoffoh/openshift-httpd/main/custom_template_pvc/custom_template_pvc/httpd_default_sc.json"


* image
  - File used by apache on web

* index_git_image
  - index.html config file used by templates custom_template_pvc folder
  - Details: Points wp.jpg to git

* index_localfiles
  - index.html config file used on custom_image_dockerfile
  - Details: Use local index.html and wp.jpg on container, created by Dockerfile
