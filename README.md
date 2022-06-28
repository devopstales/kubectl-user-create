# k8s-user
A kubectl plugin to creat qusers with certificate authentication. The program uses the current Kube Config file, either `~/.kube/config` or the one defined in the `KUBECONFIG` environment variable.

## Usage:

```bash
kubectl user create --username devopstales --email devopstales@k8s.intra --cluster k8s-main \
 --country HU  --province Pest --city Budapest  --orgUnit DevOps 
```

The command-line option can be explained as follows:
`--outdir`: The directory where you want the generated KUBECONFIG to be placed (defaults to the current working diectory)
`--username`: The name used for authentication (Required)

`--email`: The user's email (Required)

`--cluser`: The name of the cluster (Required). The program uses this name to extract the relevent information from the Kube Config file

`--country`: Optional

`--city`: Optional

`--orgUnit`: Optional

`--province`: Optional
## How to build

You must have Go version 1.14 or higher. Clone the repository, build the program and execute it with the above options. For example:

```bash
git clone https://github.com/devopstales/kubectl-user-create
cd kubectl-user-create
go build -o kubectl-user-create main.go
# mowe binary to $PATH
kubectl user create
```