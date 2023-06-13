The benchmark directory contains OpenVINO sample code for asynchronous inference in latency mode.  It is based on OpenVINO's [throughput
sample](https://github.com/openvinotoolkit/openvino/tree/master/samples/cpp/benchmark/throughput_benchmark)
and includes input and output data.

Latency is shown in microseconds.

## Building the sample

### Install OpenVINO

Two options:
- Use precompiled builds: https://docs.openvino.ai/2023.0/openvino_docs_install_guides_installing_openvino_from_archive_linux.html (recommended)
- Build from source: https://github.com/openvinotoolkit/openvino/blob/master/docs/dev/build_linux.md

### Build the sample

- Set up environment: run `source setupvars.sh` in the directory where you installed OpenVINO. For the precompiled builds openvino installation this is in the /opt/intel/openvino_2023.0.0/ directory.

- Run the ./build_samples.sh script. 

The executable `latency_benchmark` will be created in the OpenVINO samples directory (the name of this directory will be displayed after building the samples).

## Run the sample

- Set up environment: run `source setupvars.sh` in the directory where you installed OpenVINO
- Run: `./latency_benchmark <path_to_model> <batch_size> <streams> <infer_requests> <device>`

By default `batch_size` is 1 and `device` GPU. `streams` and `infer_requests` are taken from OpenVINO Runtime.

### Example Command

numactl -C0 --localalloc ./latency_benchmark <path_to_model> 10 1 1 GPU
