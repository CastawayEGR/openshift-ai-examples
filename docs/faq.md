# FAQ

## Are all 3 deployments required?

At minimal you need to apply the Open-WebUI and Ollama manifests. AUTOMATIC1111 Stable-Diffusion is optional.

## Why are you using custom built Open-WebUI and AUTOMATIC1111 Stable Diffusion container images?

I wanted to run these images on OpenShift without have to make changes to the pods Security Context Constraints. OpenShift by default runs all containers as rootless and the respective upstream images needed changes to accomodate this.

## How often are the container images used in the deployments updated?

As new versions become available of Open-WebUI and Stable Diffusion they will be built and pushed to quay.io. I will update the manifests once I have tested and verifed these versions work in OpenShift properly. 

## How do I deploy if I only have one GPU but want to deploy all 3 manifests?

I recommend you setup [time-slicing](https://docs.nvidia.com/datacenter/cloud-native/gpu-operator/latest/gpu-sharing.html) using the Nvidia operator. This will also give you the ability to do deployment rollouts as well as running multiple pods that require GPU access. **Note**: You may not be able to use both ollama and stable diffusion depending on amount of vRAM available and used by the models.

## I have multiple GPUs, how do I specify which one is used by a particular pod?

You can set an environment variable in the deployment to specify which GPU is used by the pod.

```
          env:
            - name: NVIDIA_VISIBLE_DEVICES
              value: '1'
```

## Where can I learn more about available environment variables for deployments?

You can find those at the appropriate upstream projects documentation:
* [Open-WebUI](https://docs.openwebui.com/getting-started/env-configuration/)
* [Ollama](https://github.com/ollama/ollama/tree/main/docs)
* [Automatic1111](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki)
