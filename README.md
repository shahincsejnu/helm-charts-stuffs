# helm-charts-stuffs

N.B: Always use lower case during naming a helm `chart`.

# How to use this repo in your machine

* At first add this repo in your local machine by:
  - `helm repo add <repo_name> https://shahincsejnu.github.io/helm-charts-stuffs`
* Then update your repo by:
  - `helm repo update`
* Check whether it has been added by (it will show all the charts that are in my repo):
  - `helm search repo <repo_name>`
* Now install any chart from this repo by:
  - `helm install <release_name> <repo_name>/<chart_name>`


# Helm
The Kubernetes package manager. Helm deploys charts, which you can think of as a packaged application. It is a collection of all your versioned, pre-configured application resources which can be deployed as one unit.

## Common actions for Helm:

- `helm search`: search for charts
- `helm pull`: download a chart to your local directory to view
- `helm install`: upload the chart to Kubernetes
- `helm list`: list releases of charts
- To know more use `helm` or `helm --help` in the terminal

# Charts

Helm uses a packaging format called charts, helm packages are called charts. A Chart is a Helm package, bundle of YAML files. It contains all of the resource definitions necessary to run an application, tool, or service inside of a Kubernetes cluster. 

# Helm Chart Directory Structure

For example, `helm create foo` will create a directory structure that looks
something like this:

    foo/
    |── .helmignore   # Contains patterns to ignore when packaging Helm charts.
    ├── Chart.yaml    # Information about your chart
    ├── values.yaml   # The default values for your templates
    ├── charts/       # Charts that this chart depends on
    └── templates/    # The template files
        └── tests/    # The test files

## Some techiniques

- `helm install --debug --dry-run <release_name> ./<chart_name>`: For checking/testing purpose without installing the chart. This will render the templates. But instead of installing the chart, it will return the rendered template to you so you can see the output.
- In YAML we can do typecast like: `age: !!str 21` or `port: !!int "80"`: !str tells the parser that age is a string, even if it looks like an int. And port is treated as an int, even though it is quoted.
- `helm create <chart_name>`: It create a new chart for you with the chart structure by default, also can look [this tuto](https://helm.sh/docs/helm/helm_package/)
- `helm package <chart_name>`: Helm can package your chart into an archive for you, which can be uploaded in helm hub and people can install it
- `helm repo index <dir>`: after the prev command (use this one) then for giving your chart to a remote repository follow [this tuto](https://helm.sh/docs/helm/helm_repo_index/)
- `helm lint <chart_name>`: You can also use helm to help you find issues with your chart's formatting or information.


# Resources:

- [x] [Quickstart Guide](https://helm.sh/docs/intro/quickstart/)
- [x] [Installing Helm](https://helm.sh/docs/intro/install/)
- [x] [Using Helm](https://helm.sh/docs/intro/using_helm/)
- [x] [What is Helm?](https://www.youtube.com/watch?v=fy8SHvNZGeE)
- [x] [An Introduction to Helm - Matt Farina](https://www.youtube.com/watch?v=Zzwq9FmZdsU)
- [x] [What is Helm in Kubernetes? Helm and Helm Charts explained](https://www.youtube.com/watch?v=Zzwq9FmZdsU)
- [x] [What is Helm Charts | Helm Kubernetes Demo with NGINX](https://www.youtube.com/watch?v=j-YBgTnV2v0)
- [x] [Helm 3 Deep Dive](https://www.youtube.com/watch?v=afCRt5Gd6Rk&t=1120s)
- [x] [The Chart Template Developer's Guide](https://helm.sh/docs/chart_template_guide/)
- [x] [Charts](https://helm.sh/docs/topics/charts/)
- [x] [The Chart Best Practices Guide](https://helm.sh/docs/chart_best_practices/)
- [x] [Chart Hooks](https://helm.sh/docs/topics/charts_hooks/)
- [x] [Chart Development Tips and Tricks](https://helm.sh/docs/howto/charts_tips_and_tricks/)
- [x] [Building Helm Charts From the Ground Up](https://www.youtube.com/watch?v=vQX5nokoqrQ)
