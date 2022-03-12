

```shell
mkdir demo
cd demo
kubebuilder init --domain demo.lvsoso.io --repo operator-demo

kubebuilder create api --group demo --version v1 --kind DemoVolume

# edit type

make generate

make manifest

# edit controller

make install

kubectl get crd

# edit samples

kubectl create -f config/samples/demo_v1_demovolume.yaml

kubectl get demovolumes.demo.demo.lvsoso.io

kubectl get demovolumes.demo.demo.lvsoso.io -o yaml

# run controller
make run 

# trigger event
kubectl delete -f config/samples/demo_v1_demovolume.yaml

kubectl apply -f config/samples/demo_v1_demovolume.yaml
```