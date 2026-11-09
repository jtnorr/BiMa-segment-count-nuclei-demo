# Report for BiMi Segmentation Work

## Question

How to create a reproducible mask and count nuclei from an image using a Python script. Research what Python packages are used for these tasks in professional environments. After that, read the package documentations and get accommodated with the packages and write a couple of test scripts to get some results.

## Method

Using scikit-image package on Python, and the Jupyter notebooks I can iterate through different versions of the code relatively quickly. I decided to write the code in Visual Studio Code and use Ruff for checking the file for any issues. GitHub repository is created to backup the work (<https://github.com/jtnorr/BiMa-segment-count-nuclei-demo>).

## Result

To see the output images, you can find them either in the “output” directory or on GitHub (<https://github.com/jtnorr/BiMa-segment-count-nuclei-demo/tree/32379c1aed71a32f91e7f60efc124b5018913650/output>). The different automatic thresholding methods held up over multiple images better than manual tries, so the manual way was discarded. From the automatic thresholding methods, four were chosen: Otsu, Li, Yen and Isodata. The different algorithms worked rather well, but Li and Isodata seemed to provide the best results with these. The summary can be seen in the segmentation_summary.csv for each image.

## Limitations

All the different thresholding methods had their drawbacks. Most of the issues arose from the fact that some of the nuclei were bunched up together and the watershedding couldn’t be directly used with the same parametres across the pictures. This led to some extra nuclei counts or sometimes nuclei that weren’t entirely outlined. The counts were different across the different methods, which leads to a simple conclusion: none of them are 100 % robust or accurate. The best method to count the nuclei would probably be computer-aided manual work by a human, but for an automatic method, they cut a lot of the time out of the process. The script could also be written in a more efficient way and in a more efficient language to improve processing speed.
