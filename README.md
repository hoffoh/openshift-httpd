Apache static web server for openshift


[CONTENT]

├── custom_image_dockerfile
│  └── Dockerfile
├── custom_template_pvc
│  ├── httpd_default_sc.json
│  ├── httpd_gp2csi_sc.json
│  ├── httpd_gp3csi_sc.json
│  └── httpd_nooba_sc.json
├── images
│  └── wp.jpg
├── index_git_image
│  └── index.html
├── index_localfiles
│  └── index.html
└── README.md


[DETAILS]

* custom_image_dockerfile
  - Custom image that copy to container index.html and wp.jpg from git, need to manual expose svc to get route

* custom_template_pvc
  - Creates a PVC and pod, svc and route, index.html and wp.jpg are pointed on git

* image
  - File used to show on web

* index_git_image
  - index.html config file used on templates custom_template_pvc folder

* index_localfiles
  - index.html config file used on custom_image_dockerfile
