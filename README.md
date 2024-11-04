# flux-demo

```sh
curl -s https://fluxcd.io/install.sh | sudo FLUX_VERSION=2.0.0 bash
curl -s https://fluxcd.io/install.sh | sudo FLUX_VERSION=2.4.0 bash
sudo chmod +x /usr/local/bin/flux

minikube start
kubectl get pod -A

wget https://gitlab.com/gitlab-org/cli/-/releases/v1.48.0/downloads/glab_1.48.0_linux_amd64.deb

sudo dpkg -i glab_1.48.0_linux_amd64.deb

flux bootstrap gitlab \
--hostname=gitlab.com \
--owner=jyasuu \
--repository=flux-demo \
--branch=main \
--path=clusters/testing \
--deploy-token-auth 

glab auth login
glab project clone flux-demo
glab cluster agent bootstrap flux-demo

```