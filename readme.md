Follow Instructions here: https://labs.epi2me.io/nextflow-on-windows/
The link above is the primary steps, and we shall refer that to most of the troubleshooting.

If you get stuck here:

![image](https://github.com/hackslay/nextflow-epi2me/assets/7382735/43151427-faf8-4b2d-9b9b-352ea51d0058)

### Possible Docker issue
Then this could be caused by incorrect docker settings.
To verfiy if docker is running via wsl. Run command: `docker --version`

If there's an error with the docker, go back to the epi2me document and follow Step 8: Enable WSL2 in docker.

### Need test data. 
The final step of the epi2me help doc is incomplete. For the final step follow the instructions here instead: https://github.com/epi2me-labs/wf-template.git

Particularly run the following to download test data first:
`wget https://ont-exd-int-s3-euwst1-epi2me-labs.s3.amazonaws.com/wf-template/wf-template-demo.tar.gz
tar -xzvf wf-template-demo.tar.gz`

The workflow can be run with the demo data using:
`nextflow run epi2me-labs/wf-template \
--fastq wf-template-demo/test_data/reads.fastq.gz \
-profile standard`

