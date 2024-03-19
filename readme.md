Follow Instructions here: https://labs.epi2me.io/nextflow-on-windows/

The link above is the primary steps, and we shall refer that to most of the troubleshooting.

If you get stuck here:
![image](https://github.com/hackslay/nextflow-epi2me/assets/7382735/84032409-66f1-46cc-8636-4d861f05b1ea)


## Possible Docker issue
Then this could be caused by incorrect docker settings.
To verfiy if docker is running via wsl. Run command: `docker --version`

If there's an error with the docker, we will follow epi2me document and follow Step 8: Enable WSL2 in docker. Which is outlined below.

1. Start Docker Desktop from the Windows Start menu.
2. 2. From the Docker menu, select Settings > General
3. The ‘Use the WSL 2 based engine’ box should already be ticked, if not tick the box and click Apply & Restart. </br>
![image](https://github.com/hackslay/nextflow-epi2me/assets/7382735/939d380e-bae7-46e4-8932-197128f807df)

4. Go to Settings > Resources > WSL Integration
5. ‘Enable integration with my default WSL distro’ should be ticked and select Enable integration with the Ubuntu version you have just downloaded. </br>
![image](https://github.com/hackslay/nextflow-epi2me/assets/7382735/d6ff8f87-79b7-4a7a-8782-2a633226d5bf)


## Need test data for the parameters to run.
The final step (Step 11) of the epi2me help doc is incomplete. 
For the final step follow the instructions here instead: https://github.com/epi2me-labs/wf-template.git

Particularly run the following to download test data first:
```
wget https://ont-exd-int-s3-euwst1-epi2me-labs.s3.amazonaws.com/wf-template/wf-template-demo.tar.gz
tar -xzvf wf-template-demo.tar.gz
```

The workflow can be run with the demo data using:
```
nextflow run epi2me-labs/wf-template \
--fastq wf-template-demo/test_data/reads.fastq.gz \
-profile standard
```

