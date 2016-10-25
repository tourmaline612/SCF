____________________________________________________
Project webpage: http://arxiv.org/pdf/1601.06032.pdf

This MATLAB code implements the tracking pipeline based on the SCF, MSCF, KSCF and SKSCF.
SCF: support correlation filter
MSCF: multi-channel support correlaiton filter
KSCF: kernel support correlation filter
SKSCF: scale-adaptive correlation filter

The initializaiton of filter has a great influence on the tracking performance.
Thus we provide 2 version of the code: the one-iteration version and the optimal version.
One-iteration version is the simplified version by using the initialization of filter with 'params.maxiter = 1' in makeParams.m;
and the optimal version is the one with the optimal number of iterations when learning the filter. 
The optimal iterations range from 5 to 10 in 'MSCF.m', 'KSCF.m' and 'SKSCF.m'.

Note：
SCF is the single-channel model, whose implementation is inlcuded in the MSCF with the 'feature_type' variable to 'gray'.

__________
Quickstart

1. Extract code somewhere.

2. The tracker is available for the 50 videos of the Visual Tracking
   Benchmark [3]. You need to put all videos under the default location 'base_path' in 'run.m'.

3. The videos can be downloaded from http://cvlab.hanyang.ac.kr/tracker_benchmark/datasets.html.

4. Execute 'run' without parameters to test on it. For SCF, do not forget to change the 'feature_type' variable to 'gray'.


Note: The tracker uses the 'fhog'/'gradientMex' functions from Piotr's Toolbox.
Some pre-compiled MEX files are provided for convenience. If they do not work for your
system, just get the toolbox from http://vision.ucsd.edu/~pdollar/toolbox/doc/index.html

__________
References

[1] W. Zuo, X. Wu, L. Lin, L. Zhang, M.-H Yang. "Learning Support Correlation 
Filters for Visual Tracking", arXiv preprint arXiv:1601.06032, 2016.

[2] J. F. Henriques, R. Caseiro, P. Martins, J. Batista, "High-Speed Tracking with
Kernelized Correlation Filters", TPAMI 2014.

[3] J. F. Henriques, R. Caseiro, P. Martins, J. Batista, "Exploiting the Circulant
Structure of Tracking-by-detection with Kernels", ECCV 2012.

[4] Y. Wu, J. Lim, M.-H. Yang, "Online Object Tracking: A Benchmark", CVPR 2013.
Website: http://visual-tracking.net/

________
Citation

If you find the code and dataset useful in your research, please consider citing:

@article{zuo2016learning,
  title={Learning Support Correlation Filters for Visual Tracking},
  author={Zuo, Wangmeng and Wu, Xiaohe and Lin, Liang and Zhang, Lei and Yang, Ming-Hsuan},
  journal={arXiv preprint arXiv:1601.06032},
  year={2016}
}

________
Contents

|  Folder    | description |
| ---|---|

Feedbacks and comments are welcome! Feel free to contact us via [lotuswxh@gmail.com] or [angela612@126.com].

________
Liscense
Copyright (c) 2016, Xiaohe Wu
All rights reserved. 
Redistribution and use in source and binary forms, with or without modification, are 
permitted provided that the following conditions are met:
* Redistributions of source code must retain the above copyright 
  notice, this list of conditions and the following disclaimer.
* Redistributions in binary form must reproduce the above copyright 
  notice, this list of conditions and the following disclaimer in 
  the documentation and/or other materials provided with the distribution
        
THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" 
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE 
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE 
ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE 	
LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR 
CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF 
SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS 
INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN 
CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) 
ARISING IN ANY WAY OUT OF 