# GANDataset

## Steps
1). Split the file into <2 GB chunks using `split`  
2). Commit the chunks with Git LFS  
3). Reconstruct them after cloning  

## Commands:
### Git LFS Setup
`brew install git-lfs`  
`git lfs install`  
_Split Command_  
`git lfs track "part_*"`  
`git add .`  
`git commit -m "Initial Commit."`  
`git branch -M main`  
`git push -u origin main`

### Split Command
`split -b 1900M training_data_256_256.npy.zip ./part_`  

### Join Command
`cat part_* > training_data_256_256.npy.zip`  

## SHA Verification
## Local:
`shasum training_data_256_256.npy.zip` returns:  
5a82f2097b123a2fa1c6ae85780eacaf8a894576

Verify this is still the same on colab after stitching back together!

## Cloud:
`shasum training_data_256_256.npy` returns:


