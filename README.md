# OpenShift AI Examples

[![MIT License](https://img.shields.io/badge/License-MIT-brightgreen.svg)](https://opensource.org/licenses/MIT)
[![GitHub repo size in bytes](https://img.shields.io/github/repo-size/CastawayEGR/openshift-ai-examples.svg?logoColor=brightgreen)](https://github.com/CastawayEGR/openshift-ai-examples)
[![GitHub last commit](https://img.shields.io/github/last-commit/CastawayEGR/openshift-ai-examples.svg?logoColor=brightgreen)](https://github.com/CastawayEGR/openshift-ai-examples)

## Overview
These deployments are designed to simplify the process of setting up Open-WebUI, Ollama, and Stable Diffusion WebUI using Red Hat's OpenShift platform. Custom containers images have been built to support OpenShift and are able to run without any custom SCC configuration.

## Prerequisites

* OpenShift Container Platform
* Nvidia Operator
* Nvidia GPU

## Manifests

### Open-WebUI
-----------------

* **Description**: Open-WebUI is an open-source web interface for interacting with AI models.
* **Deployment File**: `00-open-webui.yaml`
* **Usage**: Run the deployment using `oc apply -f manifests/00-open-webui.yaml`

### Ollama
------------

* **Description**: Ollama is a simple, user-friendly way to prompt AI models that provides an OpenAI-like API.
* **Deployment File**: `01-ollama.yaml`
* **Usage**: Run the deployment using `oc apply -f manifests/01-ollama.yaml`

### Stable Diffusion WebUI
---------------------

* **Description**: Stable Diffusion is a text-to-image webui that generates high-quality images from text prompts with a web interface and API to query.
* **Deployment File**: `02-stable-diffusion.yaml`
* **Usage**: Run the deployment using `oc apply -f manifests/02-stable-diffusion.yaml`

## Getting Started
To use these deployments, simply clone this repository and run the `oc apply` command for each deployment you want to use. For example:

```bash
$ git clone https://github.com/castawayegr/openshift-ai-examples.git
$ cd openshift-ai-examples
$ oc apply -f manifests/
```

## Credits
This would not be possible without the great work of the following communities:

* [Open-WebUI](https://github.com/open-webui/open-webui)
* [Ollama](https://github.com/ollama/ollama)
* [AUTOMATIC1111 Stable Diffusion WebUI](https://github.com/AUTOMATIC1111/stable-diffusion-webui)

## Contributing
You can contribute to this project by submitting a pull request or issue. We appreciate any feedback, bug reports, or feature requests.

## License
[MIT](https://choosealicense.com/licenses/mit/)

## Author Information

This repo is mantained by [Michael Tipton](https://ibeta.org).
