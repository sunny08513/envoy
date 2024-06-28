# kube builder

# download kubebuilder and install locally.
curl -L -o kubebuilder "https://go.kubebuilder.io/dl/latest/$(go env GOOS)/$(go env GOARCH)"
chmod +x kubebuilder && mv kubebuilder /usr/local/bin/


https://medium.com/developingnodes/mastering-kubernetes-operators-your-definitive-guide-to-starting-strong-70ff43579eb9

mkdir configmapsync
cd configmapsync
kubebuilder init --domain apps.example.com
kubebuilder create api --version v1 --kind ConfigMapSync

make chnages in api/v1/name_types.go in nameSpec struct and nameStatus as per need
make chages in internal/controller

make run
make install

kubectl create namespace source 
kubectl create namespace destination
kubectl apply -f configmap.yaml
kubectl apply -f configmapsync.yaml







