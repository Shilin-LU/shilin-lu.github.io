---
layout: distill
title: a distill-style blog post
description: an example of a distill-style blog post and main elements
tags: distill formatting
giscus_comments: true
date: 2021-05-22
featured: true

authors:
  - name: Albert Einstein
    url: "https://en.wikipedia.org/wiki/Albert_Einstein"
    affiliations:
      name: IAS, Princeton
  - name: Boris Podolsky
    url: "https://en.wikipedia.org/wiki/Boris_Podolsky"
    affiliations:
      name: IAS, Princeton
  - name: Nathan Rosen
    url: "https://en.wikipedia.org/wiki/Nathan_Rosen"
    affiliations:
      name: IAS, Princeton

bibliography: 2018-12-22-distill.bib

# Optionally, you can add a table of contents to your post.
# NOTES:
#   - make sure that TOC names match the actual section names
#     for hyperlinks within the post to work correctly.
#   - we may want to automate TOC generation in the future using
#     jekyll-toc plugin (https://github.com/toshimaru/jekyll-toc).
toc:
  - name: Equations
    # if a section has subsections, you can add them as follows:
    # subsections:
    #   - name: Example Child Subsection 1
    #   - name: Example Child Subsection 2
  - name: Citations
  - name: Footnotes
  - name: Code Blocks
  - name: Interactive Plots
  - name: Layouts
  - name: Other Typography?

# Below is an example of injecting additional post-specific styles.
# If you use this post as a template, delete this _styles block.

_styles: >
  .fake-img {
    background: #bbb;
    border: 1px solid rgba(0, 0, 0, 0.1);
    box-shadow: 0 0px 4px rgba(0, 0, 0, 0.1);
    margin-bottom: 12px;
  }
  .fake-img p {
    font-family: monospace;
    color: white;
    text-align: left;
    margin: 12px 0;
    text-align: center;
    font-size: 16px;
  }
---

<br>

{{< keywordList >}}
{{< keyword icon="fingerprint" >}} 2410.18775 {{< /keyword >}}
{{< keyword icon="writer" >}} Shilin Lu et el. {{< /keyword >}}
 
{{< /keywordList >}}

{{< button href="https://arxiv.org/abs/2410.18775" target="_self" >}}
↗ arXiv
{{< /button >}}
{{< button href="https://huggingface.co/papers/2410.18775" target="_self" >}}
↗ Hugging Face
{{< /button >}}




### TL;DR


{{< lead >}}

Current watermarking faces threats from AI editing. **W-Bench** is introduced to tackle this, serving as the first benchmark to evaluate how well watermarks hold up against image editing methods like regeneration and video creation. Evaluations on existing methods reveal failures against these edits. This highlights the pressing need for methods to protect copyright in the AI era.



Addressing the issues, **VINE** enhances watermarking. It analyzes frequency of image editing, using blurring as a surrogate to boost watermark robustness during training. VINE uses diffusion model SDXL-Turbo for robust embedding. Experiments show VINE achieves outstanding watermarking under image editing, outperforming prior work in image quality and robustness.

{{< /lead >}}


#### Key Takeaways

{{< alert "star" >}}
{{< typeit speed=10 lifeLike=true >}} W-Bench, a new benchmark, evaluates watermarking robustness against modern image editing techniques. {{< /typeit >}}
{{< /alert >}}

{{< alert "star" >}}
{{< typeit speed=10 startDelay=1000 lifeLike=true >}} VINE, a novel watermarking method, enhances robustness against image editing while preserving image quality. {{< /typeit >}}
{{< /alert >}}

{{< alert "star" >}}
{{< typeit speed=10 startDelay=2000 lifeLike=true >}} Blurring distortions can serve as surrogate attacks during training to bolster watermark robustness. {{< /typeit >}}
{{< /alert >}}

#### Why does it matter?
This paper introduces **W-Bench**, a benchmark that aids researchers in assessing watermark robustness against generative editing. The VINE model offers new ways to improve watermarking. This work opens new avenues for research, emphasizing the need to adapt to evolving editing.

------
#### Visual Insights


<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {(https://arxiv.org/html/2410.18775/x1.png)}
    </div>
</div>



> 🔼 Figure 1 is a two-part figure summarizing the W-Bench benchmark. (a) shows the evaluation process flow, from watermark encoding to image editing and watermark decoding. (b) presents a visual comparison of 11 watermarking methods. Each method is represented by a diamond (size indicating encoding capacity, y-coordinate showing normalized image quality (average of PSNR, SSIM, LPIPS, and FID), and x-coordinate representing robustness (TPR@0.1%FPR across four editing types)). Four bars extend from the diamond, representing performance against four image editing types: image regeneration (left), global editing (top), local editing (right), and image-to-video generation (bottom). Bar length indicates normalized TPR@0.1%FPR; longer bars represent better performance.
> <details>
> <summary>read the caption</summary>
> Figure 1: (a) Flowchart of the W-Bench evaluation process. (b) Watermarking performance. Each method is illustrated with a diamond and four bars. The area of the diamond represents the method’s encoding capacity. The y-coordinate of the diamond’s center indicates normalized image quality, calculated by averaging the normalized PSNR, SSIM, LPIPS, and FID between watermarked and input images. The x-coordinate represents robustness, measured by the True Positive Rate at a 0.1% False Positive Rate (TPR@0.1%FPR) averaged across four types of image editing methods, encompassing a total of seven distinct models and algorithms. The four bars are oriented to signify different editing tasks: image regeneration (left), global editing (top), local editing (right), and image-to-video generation (bottom). The length of each bar reflects the method’s normalized TPR@0.1%FPR after each type of image editing—the longer the bar, the better the performance.
> </details>





{{< table-caption >}}
<table class="ltx_tabular ltx_align_middle" id="S4.T1.6.6.6">
<tr class="ltx_tr" id="S4.T1.6.6.6.6">
<td class="ltx_td ltx_align_left ltx_border_tt" id="S4.T1.6.6.6.6.7" rowspan="3"><span class="ltx_text" id="S4.T1.6.6.6.6.7.1">Method</span></td>
<td class="ltx_td ltx_align_center ltx_border_tt" id="S4.T1.1.1.1.1.1" rowspan="3"><span class="ltx_text" id="S4.T1.1.1.1.1.1.1">Cap <math alttext="\uparrow" class="ltx_Math" display="inline" id="S4.T1.1.1.1.1.1.1.m1.1"><semantics id="S4.T1.1.1.1.1.1.1.m1.1a"><mo id="S4.T1.1.1.1.1.1.1.m1.1.1" stretchy="false" xref="S4.T1.1.1.1.1.1.1.m1.1.1.cmml">↑</mo><annotation-xml encoding="MathML-Content" id="S4.T1.1.1.1.1.1.1.m1.1b"><ci id="S4.T1.1.1.1.1.1.1.m1.1.1.cmml" xref="S4.T1.1.1.1.1.1.1.m1.1.1">↑</ci></annotation-xml><annotation encoding="application/x-tex" id="S4.T1.1.1.1.1.1.1.m1.1c">\uparrow</annotation><annotation encoding="application/x-llamapun" id="S4.T1.1.1.1.1.1.1.m1.1d">↑</annotation></semantics></math></span></td>
<td class="ltx_td ltx_align_center ltx_border_tt" id="S4.T1.2.2.2.2.2" rowspan="3"><span class="ltx_text" id="S4.T1.2.2.2.2.2.1">PSNR <math alttext="\uparrow" class="ltx_Math" display="inline" id="S4.T1.2.2.2.2.2.1.m1.1"><semantics id="S4.T1.2.2.2.2.2.1.m1.1a"><mo id="S4.T1.2.2.2.2.2.1.m1.1.1" stretchy="false" xref="S4.T1.2.2.2.2.2.1.m1.1.1.cmml">↑</mo><annotation-xml encoding="MathML-Content" id="S4.T1.2.2.2.2.2.1.m1.1b"><ci id="S4.T1.2.2.2.2.2.1.m1.1.1.cmml" xref="S4.T1.2.2.2.2.2.1.m1.1.1">↑</ci></annotation-xml><annotation encoding="application/x-tex" id="S4.T1.2.2.2.2.2.1.m1.1c">\uparrow</annotation><annotation encoding="application/x-llamapun" id="S4.T1.2.2.2.2.2.1.m1.1d">↑</annotation></semantics></math></span></td>
<td class="ltx_td ltx_align_center ltx_border_tt" id="S4.T1.3.3.3.3.3" rowspan="3"><span class="ltx_text" id="S4.T1.3.3.3.3.3.1">SSIM <math alttext="\uparrow" class="ltx_Math" display="inline" id="S4.T1.3.3.3.3.3.1.m1.1"><semantics id="S4.T1.3.3.3.3.3.1.m1.1a"><mo id="S4.T1.3.3.3.3.3.1.m1.1.1" stretchy="false" xref="S4.T1.3.3.3.3.3.1.m1.1.1.cmml">↑</mo><annotation-xml encoding="MathML-Content" id="S4.T1.3.3.3.3.3.1.m1.1b"><ci id="S4.T1.3.3.3.3.3.1.m1.1.1.cmml" xref="S4.T1.3.3.3.3.3.1.m1.1.1">↑</ci></annotation-xml><annotation encoding="application/x-tex" id="S4.T1.3.3.3.3.3.1.m1.1c">\uparrow</annotation><annotation encoding="application/x-llamapun" id="S4.T1.3.3.3.3.3.1.m1.1d">↑</annotation></semantics></math></span></td>
<td class="ltx_td ltx_align_center ltx_border_tt" id="S4.T1.4.4.4.4.4" rowspan="3"><span class="ltx_text" id="S4.T1.4.4.4.4.4.1">LPIPS <math alttext="\downarrow" class="ltx_Math" display="inline" id="S4.T1.4.4.4.4.4.1.m1.1"><semantics id="S4.T1.4.4.4.4.4.1.m1.1a"><mo id="S4.T1.4.4.4.4.4.1.m1.1.1" stretchy="false" xref="S4.T1.4.4.4.4.4.1.m1.1.1.cmml">↓</mo><annotation-xml encoding="MathML-Content" id="S4.T1.4.4.4.4.4.1.m1.1b"><ci id="S4.T1.4.4.4.4.4.1.m1.1.1.cmml" xref="S4.T1.4.4.4.4.4.1.m1.1.1">↓</ci></annotation-xml><annotation encoding="application/x-tex" id="S4.T1.4.4.4.4.4.1.m1.1c">\downarrow</annotation><annotation encoding="application/x-llamapun" id="S4.T1.4.4.4.4.4.1.m1.1d">↓</annotation></semantics></math></span></td>
<td class="ltx_td ltx_align_center ltx_border_tt" id="S4.T1.5.5.5.5.5" rowspan="3"><span class="ltx_text" id="S4.T1.5.5.5.5.5.1">FID <math alttext="\downarrow" class="ltx_Math" display="inline" id="S4.T1.5.5.5.5.5.1.m1.1"><semantics id="S4.T1.5.5.5.5.5.1.m1.1a"><mo id="S4.T1.5.5.5.5.5.1.m1.1.1" stretchy="false" xref="S4.T1.5.5.5.5.5.1.m1.1.1.cmml">↓</mo><annotation-xml encoding="MathML-Content" id="S4.T1.5.5.5.5.5.1.m1.1b"><ci id="S4.T1.5.5.5.5.5.1.m1.1.1.cmml" xref="S4.T1.5.5.5.5.5.1.m1.1.1">↓</ci></annotation-xml><annotation encoding="application/x-tex" id="S4.T1.5.5.5.5.5.1.m1.1c">\downarrow</annotation><annotation encoding="application/x-llamapun" id="S4.T1.5.5.5.5.5.1.m1.1d">↓</annotation></semantics></math></span></td>
<td class="ltx_td ltx_align_center ltx_border_tt" colspan="8" id="S4.T1.6.6.6.6.6">TPR@0.1%FPR <math alttext="\uparrow" class="ltx_Math" display="inline" id="S4.T1.6.6.6.6.6.m1.1"><semantics id="S4.T1.6.6.6.6.6.m1.1a"><mo id="S4.T1.6.6.6.6.6.m1.1.1" stretchy="false" xref="S4.T1.6.6.6.6.6.m1.1.1.cmml">↑</mo><annotation-xml encoding="MathML-Content" id="S4.T1.6.6.6.6.6.m1.1b"><ci id="S4.T1.6.6.6.6.6.m1.1.1.cmml" xref="S4.T1.6.6.6.6.6.m1.1.1">↑</ci></annotation-xml><annotation encoding="application/x-tex" id="S4.T1.6.6.6.6.6.m1.1c">\uparrow</annotation><annotation encoding="application/x-llamapun" id="S4.T1.6.6.6.6.6.m1.1d">↑</annotation></semantics></math> (%) (averaged over all difficulty levels)</td>
</tr>
<tr class="ltx_tr" id="S4.T1.6.6.6.7">
<td class="ltx_td ltx_align_center ltx_border_t" colspan="2" id="S4.T1.6.6.6.7.1">Regeneration</td>
<td class="ltx_td ltx_align_center ltx_border_t" colspan="3" id="S4.T1.6.6.6.7.2">Global Editing</td>
<td class="ltx_td ltx_align_center ltx_border_t" colspan="2" id="S4.T1.6.6.6.7.3">Local Editing</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.7.4">I2V</td>
</tr>
<tr class="ltx_tr" id="S4.T1.6.6.6.8">
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.8.1">Sto</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.8.2">Det</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.8.3">Pix2Pix</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.8.4">Ultra</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.8.5">Magic</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.8.6">Ultra</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.8.7">CtrlN</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.8.8">SVD</td>
</tr>
<tr class="ltx_tr" id="S4.T1.6.6.6.9">
<td class="ltx_td ltx_align_left ltx_border_t" id="S4.T1.6.6.6.9.1">MBRS <cite class="ltx_cite ltx_citemacro_citep">(Jia et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib28" title="">2021</a>)</cite>
</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.9.2">30</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.9.3">27.37</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.9.4">0.8940</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.9.5">0.1877</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.9.6">6.85</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.9.7"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T1.6.6.6.9.7.1">99.53</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.9.8"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T1.6.6.6.9.8.1">99.35</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.9.9">83.50</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.9.10">7.50</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.9.11">88.54</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.9.12"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T1.6.6.6.9.12.1">99.60</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.9.13">89.16</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.9.14">13.55</td>
</tr>
<tr class="ltx_tr" id="S4.T1.6.6.6.10">
<td class="ltx_td ltx_align_left" id="S4.T1.6.6.6.10.1">CIN <cite class="ltx_cite ltx_citemacro_citep">(Ma et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib44" title="">2022</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.10.2">30</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.10.3"><span class="ltx_text ltx_font_bold" id="S4.T1.6.6.6.10.3.1">43.19</span></td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.10.4">0.9847</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.10.5">0.0270</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.10.6">1.13</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.10.7">44.85</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.10.8">51.65</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.10.9">51.40</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.10.10">17.00</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.10.11">68.38</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.10.12">51.28</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.10.13">66.04</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.10.14">2.93</td>
</tr>
<tr class="ltx_tr" id="S4.T1.6.6.6.11">
<td class="ltx_td ltx_align_left" id="S4.T1.6.6.6.11.1">PIMoG <cite class="ltx_cite ltx_citemacro_citep">(Fang et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib18" title="">2022</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.11.2">30</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.11.3">37.72</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.11.4">0.9863</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.11.5">0.0289</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.11.6">3.43</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.11.7">82.85</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.11.8">71.18</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.11.9">72.78</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.11.10">40.14</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.11.11">81.88</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.11.12">74.30</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.11.13">64.22</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.11.14">14.33</td>
</tr>
<tr class="ltx_tr" id="S4.T1.6.6.6.12">
<td class="ltx_td ltx_align_left" id="S4.T1.6.6.6.12.1">RivaGAN <cite class="ltx_cite ltx_citemacro_citep">(Zhang et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib86" title="">2019</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.12.2">32</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.12.3">40.43</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.12.4">0.9702</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.12.5">0.0488</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.12.6">1.86</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.12.7">10.12</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.12.8">12.50</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.12.9">6.22</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.12.10">4.14</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.12.11">33.96</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.12.12">34.28</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.12.13">56.92</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.12.14">3.15</td>
</tr>
<tr class="ltx_tr" id="S4.T1.6.6.6.13">
<td class="ltx_td ltx_align_left" id="S4.T1.6.6.6.13.1">SepMark <cite class="ltx_cite ltx_citemacro_citep">(Wu et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib75" title="">2023</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.13.2">30</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.13.3">35.48</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.13.4">0.9814</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.13.5">0.0150</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.13.6">1.72</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.13.7">61.21</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.13.8">73.85</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.13.9">87.74</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.13.10">51.84</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.13.11">82.58</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.13.12">92.94</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.13.13"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T1.6.6.6.13.13.1">97.14</span></td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.13.14">8.81</td>
</tr>
<tr class="ltx_tr" id="S4.T1.6.6.6.14">
<td class="ltx_td ltx_align_left" id="S4.T1.6.6.6.14.1">DWTDCT <cite class="ltx_cite ltx_citemacro_citep">(Al-Haj, <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib1" title="">2007</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.14.2">30</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.14.3">40.46</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.14.4">0.9705</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.14.5">0.0136</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.14.6">0.24</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.14.7">0.09</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.14.8">0.00</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.14.9">0.04</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.14.10">0.06</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.14.11">0.04</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.14.12">0.32</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.14.13">0.56</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.14.14">0.01</td>
</tr>
<tr class="ltx_tr" id="S4.T1.6.6.6.15">
<td class="ltx_td ltx_align_left" id="S4.T1.6.6.6.15.1">DWTDCTSVD <cite class="ltx_cite ltx_citemacro_citep">(Navas et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib50" title="">2008</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.15.2">30</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.15.3">40.40</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.15.4">0.9799</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.15.5">0.0265</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.15.6">0.86</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.15.7">3.12</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.15.8">1.43</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.15.9">3.82</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.15.10">4.02</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.15.11">30.84</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.15.12">24.56</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.15.13">50.04</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.15.14">0.76</td>
</tr>
<tr class="ltx_tr" id="S4.T1.6.6.6.16">
<td class="ltx_td ltx_align_left" id="S4.T1.6.6.6.16.1">SSL <cite class="ltx_cite ltx_citemacro_citep">(Fernandez et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib20" title="">2022</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.16.2">30</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.16.3">41.77</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.16.4">0.9796</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.16.5">0.0350</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.16.6">3.54</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.16.7">1.76</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.16.8">9.70</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.16.9">25.06</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.16.10">10.58</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.16.11">50.10</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.16.12">25.28</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.16.13">31.46</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.16.14">3.65</td>
</tr>
<tr class="ltx_tr" id="S4.T1.6.6.6.17">
<td class="ltx_td ltx_align_left" id="S4.T1.6.6.6.17.1">StegaStamp <cite class="ltx_cite ltx_citemacro_citep">(Tancik et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib69" title="">2020</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.17.2">100</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.17.3">29.65</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.17.4">0.9107</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.17.5">0.0645</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.17.6">7.61</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.17.7">91.09</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.17.8">92.13</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.17.9">93.72</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.17.10">51.24</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.17.11"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T1.6.6.6.17.11.1">91.18</span></td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.17.12">98.84</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.17.13"><span class="ltx_text ltx_font_bold" id="S4.T1.6.6.6.17.13.1">99.06</span></td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.17.14">30.85</td>
</tr>
<tr class="ltx_tr" id="S4.T1.6.6.6.18">
<td class="ltx_td ltx_align_left" id="S4.T1.6.6.6.18.1">TrustMark <cite class="ltx_cite ltx_citemacro_citep">(Bui et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib8" title="">2023</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.18.2">100</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.18.3"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T1.6.6.6.18.3.1">41.27</span></td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.18.4">0.9910</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.18.5"><span class="ltx_text ltx_font_bold" id="S4.T1.6.6.6.18.5.1">0.0026</span></td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.18.6">0.86</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.18.7">9.22</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.18.8">34.20</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.18.9">77.72</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.18.10">43.48</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.18.11">85.90</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.18.12">76.62</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.18.13">59.78</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.18.14"><span class="ltx_text ltx_font_bold" id="S4.T1.6.6.6.18.14.1">39.60</span></td>
</tr>
<tr class="ltx_tr" id="S4.T1.6.6.6.19">
<td class="ltx_td ltx_align_left" id="S4.T1.6.6.6.19.1">EditGuard <cite class="ltx_cite ltx_citemacro_citep">(Zhang et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib90" title="">2024d</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.19.2">64</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.19.3">37.58</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.19.4">0.9406</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.19.5">0.0171</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.19.6">0.51</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.19.7">0.09</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.19.8">6.00</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.19.9">0.06</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.19.10">1.16</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.19.11">0.24</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.19.12">0.18</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.19.13">2.66</td>
<td class="ltx_td ltx_align_center" id="S4.T1.6.6.6.19.14">0.18</td>
</tr>
<tr class="ltx_tr" id="S4.T1.6.6.6.20">
<td class="ltx_td ltx_align_left ltx_border_t" id="S4.T1.6.6.6.20.1">VINE-Base</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.20.2">100</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.20.3">40.51</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.20.4"><span class="ltx_text ltx_font_bold" id="S4.T1.6.6.6.20.4.1">0.9954</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.20.5"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T1.6.6.6.20.5.1">0.0029</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.20.6"><span class="ltx_text ltx_font_bold" id="S4.T1.6.6.6.20.6.1">0.08</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.20.7">91.03</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.20.8">99.25</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.20.9"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T1.6.6.6.20.9.1">96.30</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.20.10"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T1.6.6.6.20.10.1">80.90</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.20.11">89.29</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.20.12"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T1.6.6.6.20.12.1">99.60</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.20.13">89.68</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T1.6.6.6.20.14">25.44</td>
</tr>
<tr class="ltx_tr" id="S4.T1.6.6.6.21">
<td class="ltx_td ltx_align_left ltx_border_bb" id="S4.T1.6.6.6.21.1">VINE-Robust</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T1.6.6.6.21.2">100</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T1.6.6.6.21.3">37.34</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T1.6.6.6.21.4"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T1.6.6.6.21.4.1">0.9934</span></td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T1.6.6.6.21.5">0.0063</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T1.6.6.6.21.6"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T1.6.6.6.21.6.1">0.15</span></td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T1.6.6.6.21.7"><span class="ltx_text ltx_font_bold" id="S4.T1.6.6.6.21.7.1">99.66</span></td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T1.6.6.6.21.8"><span class="ltx_text ltx_font_bold" id="S4.T1.6.6.6.21.8.1">99.98</span></td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T1.6.6.6.21.9"><span class="ltx_text ltx_font_bold" id="S4.T1.6.6.6.21.9.1">97.46</span></td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T1.6.6.6.21.10"><span class="ltx_text ltx_font_bold" id="S4.T1.6.6.6.21.10.1">86.86</span></td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T1.6.6.6.21.11"><span class="ltx_text ltx_font_bold" id="S4.T1.6.6.6.21.11.1">94.58</span></td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T1.6.6.6.21.12"><span class="ltx_text ltx_font_bold" id="S4.T1.6.6.6.21.12.1">99.96</span></td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T1.6.6.6.21.13">93.04</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T1.6.6.6.21.14"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T1.6.6.6.21.14.1">36.33</span></td>
</tr>
</table>{{< /table-caption >}}

> 🔼 This table presents a comprehensive comparison of eleven watermarking techniques' performance across various image editing methods.  It evaluates both the quality of the watermarked images (using PSNR, SSIM, LPIPS, and FID) and the robustness of the watermarks against four types of image editing: stochastic and deterministic image regeneration, global editing, local editing, and image-to-video generation. For each editing method, the True Positive Rate at 0.1% False Positive Rate (TPR@0.1%FPR) is calculated, indicating the robustness of the watermarking method against that specific type of editing.  The table also shows the encoding capacity of each method.  Higher values in PSNR, SSIM, and TPR@0.1%FPR represent better image quality and watermark robustness, while lower values in LPIPS and FID, indicate better perceptual similarity between the original and watermarked images. The best performing method in each category is shown in bold, and the second best is underlined.
> <details>
> <summary>read the caption</summary>
> Table 1: Comparison of watermarking performance in terms of watermarked image quality and detection accuracy across various image editing methods. Quality metrics are averaged over 10,000 images, and the TPR@0.1%FPR for each specific editing method is averaged over 5,000 images. The best value in each column is highlighted in bold, and the second best value is underlined. Abbreviations: Cap = Encoding Capacity; Sto = Stochastic Regeneration; Det = Deterministic Regeneration; Pix2Pix = Instruct-Pix2Pix; Ultra = UltraEdit; Magic = MagicBrush; CtrlN = ControlNet-Inpainting; SVD = Stable Video Diffusion.
> </details>





### In-depth insights


#### W-Bench: T2I Edit
While the provided document doesn't explicitly define a section titled "W-Bench: T2I Edit," we can infer its potential scope. Considering the paper's focus, such a section would likely detail the **evaluation of watermarking schemes against image editing techniques** powered by Text-to-Image (T2I) models. This benchmark, being part of W-Bench, would involve subjecting watermarked images to various T2I editing operations, and then assessing the ability to **recover the embedded watermark**. Key aspects likely covered include the specific T2I editing models employed, the range of prompts used to guide the edits, and the metrics used to quantify both the **robustness of the watermark and the quality of the edited image**. Furthermore, the results likely **highlight the vulnerabilities of existing watermarking techniques** when confronted with these advanced T2I editing capabilities, thus motivating the need for more robust solutions like VINE.

#### Freq. Analysis
The document includes a frequency analysis to understand how image editing techniques affect the spectrum of an image. This analysis aims to identify surrogate attacks, **especially blurring distortions**, that can enhance the robustness of watermarking against image editing. The key insight is that image editing tends to remove patterns embedded in **high-frequency bands** while those in low-frequency bands are less affected. This property is similar to blurring distortions. Understanding the frequency characteristics of image editing allows the model to learn to embed watermarks in the less-affected frequency bands, improving robustness. Blurring distortions are used as surrogate attacks during training to achieve this.

#### VINE: Prior boost
**VINE (Visual Information NEtwork)** leverages the power of pre-trained generative models as a **prior boost** for watermarking. It recognizes that watermarking can be framed as a conditional generation task. By adapting a powerful generator, the model is capable of embedding watermarks in a more robust and imperceptible manner, as it learns a more intricate data distribution for watermarked images. This **prior knowledge** is crucial for upholding both image quality and resilience. The method's strength comes from this smart use of prior knowledge. It enables **high watermark strength with minimal impact on image quality**.

#### Quant. Editing
While the provided document doesn't contain a heading explicitly titled "Quant. Editing," the intersection of quantitative analysis and image editing suggests several key aspects.  Such a field would likely involve **quantifying the impact of various editing operations** on images. This could entail measuring changes in image quality metrics (PSNR, SSIM), perceptual similarity (LPIPS, FID), or even the detectability of specific features or objects.  Furthermore, "Quant. Editing" could focus on developing **algorithms that automatically optimize editing parameters** based on quantitative criteria.  For instance, an algorithm might aim to minimize perceptual distortion while achieving a desired artistic style transfer. It might also be important for comparing effects brought by human edits and those that could be replicated in **large language model driven image edits**, so more quantifiable metrics would bring improvements there. 

#### I2V still Limited
The phrase 'I2V still Limited' suggests that while progress has been made in various aspects of the research, the Image-to-Video (I2V) domain faces persistent limitations. This could mean that **existing techniques struggle to maintain watermark robustness** when images are transformed into video, possibly due to temporal inconsistencies or alterations during video generation. The algorithms may not handle dynamic scenes well, or the method that are used may not be robust enough when there is a change. The **need for a more robust and adaptable method** is therefore important. The **complexity of watermarking videos is high**, since it should consider frame consistency and potential distortions during the process.


### More visual insights

<details>
<summary>More on figures
</summary>


![](https://arxiv.org/html/2410.18775/x2.png)

> 🔼 This figure demonstrates how image editing affects an image's frequency components.  The Instruct-Pix2Pix model is used as an example of an image editing process. The image is first Fourier transformed (ℱ(⋅)), and then the editing model is applied to both the original image and the Fourier transformed image.  A comparison of the Fourier transforms of both the original and edited images reveals which frequency components are most affected by the editing process. The magnitude of the Fourier transform is shown on a logarithmic scale for better visualization of changes across different frequency bands.
> <details>
> <summary>read the caption</summary>
> Figure 2: Process for analyzing the impact of image editing on an image’s frequency spectrum. In this example, the editing model Instruct-Pix2Pix, denoted as ϵ⁢(⋅)italic-ϵ⋅\epsilon(\cdot)italic_ϵ ( ⋅ ), is employed. The function ℱ⁢(⋅)ℱ⋅\mathcal{F}(\cdot)caligraphic_F ( ⋅ ) represents the Fourier transform, and we visualize its magnitude on a logarithmic scale.
> </details>



![](https://arxiv.org/html/2410.18775/x3.png)

> 🔼 Figure 3 visualizes the effects of image editing and various image distortions on the frequency components of images.  The analysis, performed on 1000 images, reveals a consistent trend: image editing and blurring techniques (like pixelation and defocus blur) primarily affect the mid and high-frequency patterns, removing them largely while leaving the low-frequency components relatively untouched. Conversely, common distortions such as JPEG compression and saturation do not show this frequency-specific behavior. Notably, Stable Video Diffusion (SVD), a method that completely removes all frequency patterns, was excluded from the analysis due to the complete removal of any frequency information.
> <details>
> <summary>read the caption</summary>
> Figure 3: Impact of various image editing techniques and distortions on the frequency spectra of images. Results are averaged over 1,000 images. Image editing methods tend to remove frequency patterns in the mid- and high-frequency bands, while low-frequency patterns remain largely unaffected. This trend is also observed with blurring distortions such as pixelation and defocus blur. In contrast, commonly used distortions like JPEG compression and saturation do not exhibit similar behavior in the frequency domain. The analysis of SVD is not included, as it removes all patterns, rendering them invisible to the human eye. A discussion on SVD can be found in Section 4.3.
> </details>



![](https://arxiv.org/html/2410.18775/x4.png)

> 🔼 This figure illustrates the architecture of VINE, a novel watermarking method.  VINE leverages the pre-trained SDXL-Turbo model, a one-step text-to-image diffusion model, as its watermark encoder.  A key innovation is the 'condition adaptor' module, which effectively combines the watermark information with the input image before feeding it into the VAE encoder. This fusion step ensures seamless integration of the watermark into the image.  To enhance the perceptual similarity between the watermarked and original images, zero-convolution layers and skip connections are incorporated into the encoder-decoder structure. Finally, the watermark decoder uses the ConvNeXt-B model, augmented with a fully connected layer, to recover the 100-bit watermark. Importantly, during training, the SDXL-Turbo model's text prompt is set to 'null' to focus training on the watermarking task.  Details of the condition adaptor are shown separately in Figure 9.
> <details>
> <summary>read the caption</summary>
> Figure 4: The overall framework of our method, VINE. We utilize the pretrained one-step text-to-image model SDXL-Turbo as the watermark encoder. A condition adaptor is incorporated to fuse the watermark with the image before passing the information to the VAE encoder. Zero-convolution layers (Zhang et al., 2023) and skip connections are added for better perceptual similarity. For decoding the watermark, we employ ConvNeXt-B (Liu et al., 2022b) as the decoder, with an additional fully connected layer to output a 100-bit watermark. Throughout the entire training process, the SDXL-Turbo text prompt is set to null prompt. Figure 9 shows the condition adaptor architecture.
> </details>



![](https://arxiv.org/html/2410.18775/x5.png)

> 🔼 Figure 5 presents a comprehensive comparison of eleven watermarking techniques across three distinct image editing scenarios: stochastic image regeneration, global image editing, and local image editing.  Each scenario presents various difficulty levels to assess robustness.  The figure uses TPR@0.1%FPR (True Positive Rate at 0.1% False Positive Rate) to measure the watermark's resilience against each editing method, showing the percentage of correctly identified watermarks.  It also displays image quality metrics (PSNR, SSIM, LPIPS, and FID) to evaluate the perceptual impact of each watermarking method on image quality, illustrating the trade-off between robustness and quality. Additional results involving different editing methods are provided in Figure 16.
> <details>
> <summary>read the caption</summary>
> Figure 5: The performance of watermarking methods under (a) Stochastic regeneration, (b) Global editing, and (c) Local editing. Additional results are available in Figure 16.
> </details>



![](https://arxiv.org/html/2410.18775/x6.png)

> 🔼 This figure visualizes the frequency patterns of eleven watermarking methods by using a 2D Fourier transform. The magnitude of the frequency spectrum is shown on a logarithmic scale.  The patterns are analyzed to determine how the watermarking methods distribute information across different frequency bands.  The DWTDCT method is omitted because its pattern is very similar to DWTDCTSVD and both are too faint to clearly distinguish at this scale.  The image should be zoomed to see the details.
> <details>
> <summary>read the caption</summary>
> Figure 6: Frequency pattern visualizations for each watermarking method. The DWTDCT method is excluded because it closely resembles DWTDCTSVD and their pattern intensity is too weak to be discerned on the uniform scale. Please zoom in for a closer look.
> </details>



![](https://arxiv.org/html/2410.18775/x7.png)

> 🔼 Figure 7 displays the performance of various watermarking techniques when subjected to different image distortions at a resolution of 512 x 512 pixels.  Each subplot represents a different type of distortion: (a) Gaussian blurring (varying kernel size), (b) brightness adjustments (changing brightness factor), (c) contrast modifications (changing contrast factor), (d) Gaussian noise (varying standard deviation), and (e) JPEG compression (varying compression factor). For each distortion type, the figure shows how the True Positive Rate at a 0.1% False Positive Rate (TPR@0.1%FPR), True Positive Rate at a 1% False Positive Rate (TPR@1%FPR), bit accuracy, and Area Under the Receiver Operating Characteristic Curve (AUROC) of each watermarking method change in response to the increasing level of distortion. This allows for a comparative analysis of the robustness of different watermarking methods against various common image processing manipulations.
> <details>
> <summary>read the caption</summary>
> Figure 7: Performance of watermarking methods at a resolution of 512×\times×512 pixels under (a) Gaussian blurring, (b) brightness adjustments, (c) contrast modifications, (d) Gaussian noise, and (e) JPEG compression.
> </details>



![](https://arxiv.org/html/2410.18775/x8.png)

> 🔼 Figure 8 displays the performance of different watermarking methods when subjected to various image distortions at their original training resolutions.  The distortions tested include Gaussian blurring, brightness adjustments, contrast modifications, Gaussian noise, and JPEG compression. The figure highlights how each method's robustness varies depending on the type and severity of distortion. Importantly, different watermarking methods were trained on different image resolutions (MBRS, CIN, PIMoG, and SepMark at 128x128; TrustMark, VINE-B, and VINE-R at 256x256; and StegaStamp at 400x400), demonstrating the impact of training resolution on robustness against common image processing artifacts.
> <details>
> <summary>read the caption</summary>
> Figure 8: Assessment of watermarking methods at their respective training resolutions under the following conditions: (a) Gaussian blurring, (b) brightness adjustments, (c) contrast modifications, (d) Gaussian noise, and (e) JPEG compression. Training resolutions: MBRS, CIN, PIMoG, and SepMark were trained at 128×\times×128 pixels; TrustMark, VINE-B, and VINE-R at 256×\times×256 pixels; and StegaStamp at 400×\times×400 pixels.
> </details>



![](https://arxiv.org/html/2410.18775/x9.png)

> 🔼 This figure details the architecture of the 'condition adaptor' module used within the VINE watermarking model (Figure 4 of the paper). The condition adaptor's role is to effectively combine the input image and watermark data before this combined information is passed to the VAE encoder.  The architecture consists of several fully connected and convolutional layers, each followed by a ReLU activation function. This design ensures that the relevant information from both the watermark and image is properly fused for optimal watermark embedding.
> <details>
> <summary>read the caption</summary>
> Figure 9: Architecture of the condition adaptor in Figure 4. Each fully connected and convolutional layer is followed by an activation layer.
> </details>



![](https://arxiv.org/html/2410.18775/x10.png)

> 🔼 This figure displays the reconstruction quality for both stochastic and deterministic image regeneration methods.  Stochastic regeneration introduces noise to the image, then uses a diffusion model to reconstruct a clean image. Deterministic regeneration uses the diffusion model to deterministically create a noisy image, and then reconstructs it.  The x-axis in (a) represents the noise level (timestep), and the y-axis is the peak signal-to-noise ratio (PSNR) to measure the difference between the regenerated and original image. Similarly, the x-axis in (b) shows the number of sampling steps used to create the noisy version, and the y-axis is the PSNR. Higher PSNR values indicate better reconstruction quality, with lower values suggesting degradation due to higher noise levels. The plots show that as the difficulty of the regeneration task increases (higher noise levels or fewer sampling steps), the PSNR decreases.
> <details>
> <summary>read the caption</summary>
> Figure 10: The reconstruction quality of (a) stochastic regeneration and (b) deterministic regeneration. The PSNR is calculated by comparing the regenerated image to the original image.
> </details>



![](https://arxiv.org/html/2410.18775/x11.png)

> 🔼 Figure 11 shows a comparison of image reconstruction quality for stochastic and deterministic image regeneration methods.  The top row displays the original images used for testing. Each subsequent row illustrates the results of regenerating the image using stochastic methods with increasing levels of noise (60, 100, 140, 180, 220) and deterministic methods with increasing levels of sampling steps (15, 25, 35, 45). The figure shows that higher noise levels in stochastic methods and higher sampling steps in deterministic methods result in lower quality reconstruction.  This degradation is apparent in the detail loss and/or introduction of artifacts.  It is recommended to zoom in for a closer examination.
> <details>
> <summary>read the caption</summary>
> Figure 11: The reconstruction quality of stochastic regeneration and deterministic regeneration. Please zoom in for a closer look.
> </details>



![](https://arxiv.org/html/2410.18775/x12.png)

> 🔼 This figure demonstrates the results of global image editing applied to images watermarked using different methods.  Two example images are shown, each edited using three different methods (UltraEdit, InstructPix2Pix, and MagicBrush). For each image and each editing method, the original image, the watermarked version, and the edited watermarked version are displayed. The results show that despite being edited, the watermarks have a minimal effect on the final edited image, only causing minor visual changes.
> <details>
> <summary>read the caption</summary>
> Figure 12: Different watermarks have minimal impact on the image global editing outcomes, resulting in only slight changes.
> </details>



![](https://arxiv.org/html/2410.18775/x13.png)

> 🔼 This figure displays the results of local image editing experiments using different watermarking methods.  Two example images (a stop sign and a pizza) are shown with various local edits applied. Each row represents a different watermarking technique. The 'Unedited' column shows the original image, followed by columns showing the edited images using three different methods (UltraEdit, ControlNet-Inpainting, and Mask). The results demonstrate that the watermarks have minimal effect on the final appearance of the images after local editing, with only minor changes visible.
> <details>
> <summary>read the caption</summary>
> Figure 13: Different watermarks have minimal impact on the image local editing outcomes, resulting in only slight changes.
> </details>



![](https://arxiv.org/html/2410.18775/x14.png)

> 🔼 This figure displays the results of applying image-to-video generation to images watermarked using various methods.  The process involves taking a single watermarked image and converting it into a short video clip. Each row represents a different watermarking technique applied to two example images. The columns show the original unedited image, followed by the watermarked image and then a series of frames from the generated video clip. The caption indicates that the presence of the watermarks has a minimal impact on the image-to-video generation process, leading to only minor visual differences in the resulting videos.
> <details>
> <summary>read the caption</summary>
> Figure 14: Different watermarks have little effect on image-to-video generation, leading to only minor changes.
> </details>



![](https://arxiv.org/html/2410.18775/x15.png)

> 🔼 Figure 15 presents a qualitative comparison of different watermarking methods by visually inspecting the residual images obtained after watermark removal. Two example images are used for comparison: a canal scene and a dog eating food. For each watermarking method, it showcases the original image, watermarked image, and the residual image resulting from subtracting the original from the watermarked image. This visual representation helps assess the perceptual quality and invisibility of the watermarks. The residuals should ideally be imperceptible (noise-like) to the human eye.  Note that the quality of the residuals can be further analyzed by zooming into the image.
> <details>
> <summary>read the caption</summary>
> Figure 15: Qualitative comparison of the evaluated watermarking methods. Please zoom in for a closer look.
> </details>



![](https://arxiv.org/html/2410.18775/x16.png)

> 🔼 Figure 16 presents a comprehensive evaluation of eleven watermarking techniques across five distinct image manipulation scenarios.  Each subfigure (a-e) illustrates the performance metrics (TPR@0.1%FPR, TPR@1%FPR, bit accuracy, and AUROC) for each watermarking method under a specific image editing technique.  (a) shows results for deterministic image regeneration using DPM-Solver, showcasing robustness at varying sampling steps. (b) and (c) evaluate global editing capabilities using UltraEdit and Instruct-Pix2Pix, respectively, across different text guidance scales, revealing methods that maintain watermark integrity under various editing prompts. (d) assesses robustness against local editing using ControlNet-Inpainting at different mask sizes, providing insights into the methods’ resilience to targeted image modifications. Finally, (e) shows the performance of each method when generating videos from images with Stable Video Diffusion, determining which watermarks can be successfully extracted in the generated video frames.
> <details>
> <summary>read the caption</summary>
> Figure 16: The performance of watermarking methods under (a) Deterministic regeneration with DPM-Solver, (b) Global editing with UltraEdit, (c) Global editing with Instruct-Pix2Pix, (d) Local editing with ControlNet-Inpainting, and (e) Image-to-video generation with Stable Video Diffusion.
> </details>



</details>




<details>
<summary>More on tables
</summary>


{{< table-caption >}}
<table class="ltx_tabular ltx_align_middle" id="S4.T2.5.5.5">
<tr class="ltx_tr" id="S4.T2.5.5.5.5">
<td class="ltx_td ltx_align_left ltx_border_tt" id="S4.T2.5.5.5.5.6" rowspan="2"><span class="ltx_text" id="S4.T2.5.5.5.5.6.1">Config</span></td>
<td class="ltx_td ltx_align_center ltx_border_tt" id="S4.T2.5.5.5.5.7">Blurring</td>
<td class="ltx_td ltx_align_center ltx_border_tt" colspan="5" id="S4.T2.5.5.5.5.8">Watermark Encoder</td>
<td class="ltx_td ltx_align_center ltx_border_tt" id="S4.T2.1.1.1.1.1" rowspan="2"><span class="ltx_text" id="S4.T2.1.1.1.1.1.1">PSNR <math alttext="\uparrow" class="ltx_Math" display="inline" id="S4.T2.1.1.1.1.1.1.m1.1"><semantics id="S4.T2.1.1.1.1.1.1.m1.1a"><mo id="S4.T2.1.1.1.1.1.1.m1.1.1" stretchy="false" xref="S4.T2.1.1.1.1.1.1.m1.1.1.cmml">↑</mo><annotation-xml encoding="MathML-Content" id="S4.T2.1.1.1.1.1.1.m1.1b"><ci id="S4.T2.1.1.1.1.1.1.m1.1.1.cmml" xref="S4.T2.1.1.1.1.1.1.m1.1.1">↑</ci></annotation-xml><annotation encoding="application/x-tex" id="S4.T2.1.1.1.1.1.1.m1.1c">\uparrow</annotation><annotation encoding="application/x-llamapun" id="S4.T2.1.1.1.1.1.1.m1.1d">↑</annotation></semantics></math></span></td>
<td class="ltx_td ltx_align_center ltx_border_tt" id="S4.T2.2.2.2.2.2" rowspan="2"><span class="ltx_text" id="S4.T2.2.2.2.2.2.1">SSIM <math alttext="\uparrow" class="ltx_Math" display="inline" id="S4.T2.2.2.2.2.2.1.m1.1"><semantics id="S4.T2.2.2.2.2.2.1.m1.1a"><mo id="S4.T2.2.2.2.2.2.1.m1.1.1" stretchy="false" xref="S4.T2.2.2.2.2.2.1.m1.1.1.cmml">↑</mo><annotation-xml encoding="MathML-Content" id="S4.T2.2.2.2.2.2.1.m1.1b"><ci id="S4.T2.2.2.2.2.2.1.m1.1.1.cmml" xref="S4.T2.2.2.2.2.2.1.m1.1.1">↑</ci></annotation-xml><annotation encoding="application/x-tex" id="S4.T2.2.2.2.2.2.1.m1.1c">\uparrow</annotation><annotation encoding="application/x-llamapun" id="S4.T2.2.2.2.2.2.1.m1.1d">↑</annotation></semantics></math></span></td>
<td class="ltx_td ltx_align_center ltx_border_tt" id="S4.T2.3.3.3.3.3" rowspan="2"><span class="ltx_text" id="S4.T2.3.3.3.3.3.1">LPIPS <math alttext="\downarrow" class="ltx_Math" display="inline" id="S4.T2.3.3.3.3.3.1.m1.1"><semantics id="S4.T2.3.3.3.3.3.1.m1.1a"><mo id="S4.T2.3.3.3.3.3.1.m1.1.1" stretchy="false" xref="S4.T2.3.3.3.3.3.1.m1.1.1.cmml">↓</mo><annotation-xml encoding="MathML-Content" id="S4.T2.3.3.3.3.3.1.m1.1b"><ci id="S4.T2.3.3.3.3.3.1.m1.1.1.cmml" xref="S4.T2.3.3.3.3.3.1.m1.1.1">↓</ci></annotation-xml><annotation encoding="application/x-tex" id="S4.T2.3.3.3.3.3.1.m1.1c">\downarrow</annotation><annotation encoding="application/x-llamapun" id="S4.T2.3.3.3.3.3.1.m1.1d">↓</annotation></semantics></math></span></td>
<td class="ltx_td ltx_align_center ltx_border_tt" id="S4.T2.4.4.4.4.4" rowspan="2"><span class="ltx_text" id="S4.T2.4.4.4.4.4.1">FID <math alttext="\downarrow" class="ltx_Math" display="inline" id="S4.T2.4.4.4.4.4.1.m1.1"><semantics id="S4.T2.4.4.4.4.4.1.m1.1a"><mo id="S4.T2.4.4.4.4.4.1.m1.1.1" stretchy="false" xref="S4.T2.4.4.4.4.4.1.m1.1.1.cmml">↓</mo><annotation-xml encoding="MathML-Content" id="S4.T2.4.4.4.4.4.1.m1.1b"><ci id="S4.T2.4.4.4.4.4.1.m1.1.1.cmml" xref="S4.T2.4.4.4.4.4.1.m1.1.1">↓</ci></annotation-xml><annotation encoding="application/x-tex" id="S4.T2.4.4.4.4.4.1.m1.1c">\downarrow</annotation><annotation encoding="application/x-llamapun" id="S4.T2.4.4.4.4.4.1.m1.1d">↓</annotation></semantics></math></span></td>
<td class="ltx_td ltx_align_center ltx_border_tt" colspan="4" id="S4.T2.5.5.5.5.5">TPR@0.1%FPR <math alttext="\uparrow" class="ltx_Math" display="inline" id="S4.T2.5.5.5.5.5.m1.1"><semantics id="S4.T2.5.5.5.5.5.m1.1a"><mo id="S4.T2.5.5.5.5.5.m1.1.1" stretchy="false" xref="S4.T2.5.5.5.5.5.m1.1.1.cmml">↑</mo><annotation-xml encoding="MathML-Content" id="S4.T2.5.5.5.5.5.m1.1b"><ci id="S4.T2.5.5.5.5.5.m1.1.1.cmml" xref="S4.T2.5.5.5.5.5.m1.1.1">↑</ci></annotation-xml><annotation encoding="application/x-tex" id="S4.T2.5.5.5.5.5.m1.1c">\uparrow</annotation><annotation encoding="application/x-llamapun" id="S4.T2.5.5.5.5.5.m1.1d">↑</annotation></semantics></math> (%)</td>
</tr>
<tr class="ltx_tr" id="S4.T2.5.5.5.6">
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.6.1">Distortions</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.6.2">Backbone</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.6.3">Condition</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.6.4">Skip</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.6.5">Pretrained</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.6.6">Finetune</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.6.7">Sto</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.6.8">Det</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.6.9">Pix2Pix</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.6.10">Ultra</td>
</tr>
<tr class="ltx_tr" id="S4.T2.5.5.5.7">
<td class="ltx_td ltx_align_left ltx_border_t" id="S4.T2.5.5.5.7.1">Config A</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.7.2"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.7.2.1">\faTimes</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.7.3" rowspan="3"><span class="ltx_text" id="S4.T2.5.5.5.7.3.1">Simple UNet</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.7.4" rowspan="3"><span class="ltx_text" id="S4.T2.5.5.5.7.4.1">N.A.</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.7.5" rowspan="3"><span class="ltx_text" id="S4.T2.5.5.5.7.5.1">N.A.</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.7.6" rowspan="3"><span class="ltx_text" id="S4.T2.5.5.5.7.6.1">N.A.</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.7.7"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.7.7.1">\faTimes</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.7.8">38.21</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.7.9">0.9828</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.7.10">0.0148</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.7.11">1.69</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.7.12">54.61</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.7.13">66.86</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.7.14">64.24</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.7.15">32.62</td>
</tr>
<tr class="ltx_tr" id="S4.T2.5.5.5.8">
<td class="ltx_td ltx_align_left" id="S4.T2.5.5.5.8.1">Config B</td>
<td class="ltx_td ltx_align_right" id="S4.T2.5.5.5.8.2"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.8.2.1">\faCheck</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.8.3"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.8.3.1">\faTimes</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.8.4">35.85</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.8.5">0.9766</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.8.6">0.0257</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.8.7">2.12</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.8.8">86.85</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.8.9">92.28</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.8.10">80.98</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.8.11">62.14</td>
</tr>
<tr class="ltx_tr" id="S4.T2.5.5.5.9">
<td class="ltx_td ltx_align_left" id="S4.T2.5.5.5.9.1">Config C</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.9.2"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.9.2.1">\faCheck</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.9.3"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.9.3.1">\faCheck</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.9.4">31.24</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.9.5">0.9501</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.9.6">0.0458</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.9.7">4.67</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.9.8">98.59</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.9.9">99.29</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.9.10">96.01</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.9.11">84.60</td>
</tr>
<tr class="ltx_tr" id="S4.T2.5.5.5.10">
<td class="ltx_td ltx_align_left ltx_border_t" id="S4.T2.5.5.5.10.1">Config D</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.10.2"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.10.2.1">\faCheck</span></td>
<td class="ltx_td ltx_align_center ltx_border_bb ltx_border_t" id="S4.T2.5.5.5.10.3" rowspan="5"><span class="ltx_text" id="S4.T2.5.5.5.10.3.1">SDXL-Turbo</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.10.4">ControlNet</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.10.5"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.10.5.1">\faTimes</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.10.6"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.10.6.1">\faCheck</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.10.7"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.10.7.1">\faTimes</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.10.8">32.68</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.10.9">0.9640</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.10.10">0.0298</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.10.11">2.87</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.10.12">90.82</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.10.13">94.89</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.10.14">91.86</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="S4.T2.5.5.5.10.15">70.69</td>
</tr>
<tr class="ltx_tr" id="S4.T2.5.5.5.11">
<td class="ltx_td ltx_align_left" id="S4.T2.5.5.5.11.1">Config E</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.11.2"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.11.2.1">\faCheck</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.11.3"><span class="ltx_text" id="S4.T2.5.5.5.11.3.1" style="color:#CD5555;">Cond. Adaptor</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.11.4"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.11.4.1">\faTimes</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.11.5"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.11.5.1">\faCheck</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.11.6"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.11.6.1">\faTimes</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.11.7">36.76</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.11.8">0.9856</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.11.9">0.0102</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.11.10">0.53</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.11.11">90.86</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.11.12">94.78</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.11.13">92.88</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.11.14">70.68</td>
</tr>
<tr class="ltx_tr" id="S4.T2.5.5.5.12">
<td class="ltx_td ltx_align_left" id="S4.T2.5.5.5.12.1">Config F (VINE-B)</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.12.2"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.12.2.1">\faCheck</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.12.3">Cond. Adaptor</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.12.4"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.12.4.1">\faCheck</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.12.5"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.12.5.1">\faCheck</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.12.6"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.12.6.1">\faTimes</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.12.7"><span class="ltx_text ltx_font_bold" id="S4.T2.5.5.5.12.7.1">40.51</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.12.8"><span class="ltx_text ltx_font_bold" id="S4.T2.5.5.5.12.8.1">0.9954</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.12.9"><span class="ltx_text ltx_font_bold" id="S4.T2.5.5.5.12.9.1">0.0029</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.12.10"><span class="ltx_text ltx_font_bold" id="S4.T2.5.5.5.12.10.1">0.08</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.12.11">91.03</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.12.12">99.25</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.12.13"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T2.5.5.5.12.13.1">96.30</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.12.14">80.90</td>
</tr>
<tr class="ltx_tr" id="S4.T2.5.5.5.13">
<td class="ltx_td ltx_align_left" id="S4.T2.5.5.5.13.1">Config G (VINE-R)</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.13.2"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.13.2.1">\faCheck</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.13.3">Cond. Adaptor</td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.13.4"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.13.4.1">\faCheck</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.13.5"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.13.5.1">\faCheck</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.13.6"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.13.6.1">\faCheck</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.13.7"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T2.5.5.5.13.7.1">37.34</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.13.8"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T2.5.5.5.13.8.1">0.9934</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.13.9"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T2.5.5.5.13.9.1">0.0063</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.13.10"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T2.5.5.5.13.10.1">0.15</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.13.11"><span class="ltx_text ltx_font_bold" id="S4.T2.5.5.5.13.11.1">99.66</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.13.12"><span class="ltx_text ltx_font_bold" id="S4.T2.5.5.5.13.12.1">99.98</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.13.13"><span class="ltx_text ltx_font_bold" id="S4.T2.5.5.5.13.13.1">97.46</span></td>
<td class="ltx_td ltx_align_center" id="S4.T2.5.5.5.13.14"><span class="ltx_text ltx_font_bold" id="S4.T2.5.5.5.13.14.1">86.86</span></td>
</tr>
<tr class="ltx_tr" id="S4.T2.5.5.5.14">
<td class="ltx_td ltx_align_left ltx_border_bb" id="S4.T2.5.5.5.14.1">Config H</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T2.5.5.5.14.2"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.14.2.1">\faCheck</span></td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T2.5.5.5.14.3">Cond. Adaptor</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T2.5.5.5.14.4"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.14.4.1">\faCheck</span></td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T2.5.5.5.14.5"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.14.5.1">\faTimes</span></td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T2.5.5.5.14.6"><span class="ltx_ERROR undefined" id="S4.T2.5.5.5.14.6.1">\faCheck</span></td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T2.5.5.5.14.7">35.18</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T2.5.5.5.14.8">0.9812</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T2.5.5.5.14.9">0.0137</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T2.5.5.5.14.10">1.03</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T2.5.5.5.14.11"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T2.5.5.5.14.11.1">99.67</span></td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T2.5.5.5.14.12"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T2.5.5.5.14.12.1">99.92</span></td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T2.5.5.5.14.13">96.13</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="S4.T2.5.5.5.14.14"><span class="ltx_text ltx_framed ltx_framed_underline" id="S4.T2.5.5.5.14.14.1">84.66</span></td>
</tr>
</table>{{< /table-caption >}}
> 🔼 This ablation study analyzes the effects of different components on the performance of the VINE watermarking method for image regeneration and global editing tasks.  It shows how adding blurring distortions, changing the watermark encoder, incorporating a condition adaptor, using skip connections,  and fine-tuning with Instruct-Pix2Pix affect the True Positive Rate (TPR) at 0.1% False Positive Rate (FPR), peak signal-to-noise ratio (PSNR), structural similarity index (SSIM), learned perceptual image patch similarity (LPIPS), Fréchet inception distance (FID), and other image quality metrics. Each configuration builds upon the previous one, highlighting the incremental contribution of each component.
> <details>
> <summary>read the caption</summary>
> Table 2: Ablation study examining the impact of key components on image regeneration and global editing. Each configuration builds upon the previous one, with changes highlighted in red.
> </details>

{{< table-caption >}}
<table class="ltx_tabular ltx_align_middle" id="A3.T3.14.14.14">
<tr class="ltx_tr" id="A3.T3.6.6.6.6">
<td class="ltx_td ltx_align_left ltx_border_tt" id="A3.T3.6.6.6.6.7">Method</td>
<td class="ltx_td ltx_align_center ltx_border_tt" id="A3.T3.6.6.6.6.8">Resolution</td>
<td class="ltx_td ltx_align_center ltx_border_tt" id="A3.T3.1.1.1.1.1">Capacity <math alttext="\uparrow" class="ltx_Math" display="inline" id="A3.T3.1.1.1.1.1.m1.1"><semantics id="A3.T3.1.1.1.1.1.m1.1a"><mo id="A3.T3.1.1.1.1.1.m1.1.1" stretchy="false" xref="A3.T3.1.1.1.1.1.m1.1.1.cmml">↑</mo><annotation-xml encoding="MathML-Content" id="A3.T3.1.1.1.1.1.m1.1b"><ci id="A3.T3.1.1.1.1.1.m1.1.1.cmml" xref="A3.T3.1.1.1.1.1.m1.1.1">↑</ci></annotation-xml><annotation encoding="application/x-tex" id="A3.T3.1.1.1.1.1.m1.1c">\uparrow</annotation><annotation encoding="application/x-llamapun" id="A3.T3.1.1.1.1.1.m1.1d">↑</annotation></semantics></math>
</td>
<td class="ltx_td ltx_align_center ltx_border_tt" id="A3.T3.2.2.2.2.2">PSNR <math alttext="\uparrow" class="ltx_Math" display="inline" id="A3.T3.2.2.2.2.2.m1.1"><semantics id="A3.T3.2.2.2.2.2.m1.1a"><mo id="A3.T3.2.2.2.2.2.m1.1.1" stretchy="false" xref="A3.T3.2.2.2.2.2.m1.1.1.cmml">↑</mo><annotation-xml encoding="MathML-Content" id="A3.T3.2.2.2.2.2.m1.1b"><ci id="A3.T3.2.2.2.2.2.m1.1.1.cmml" xref="A3.T3.2.2.2.2.2.m1.1.1">↑</ci></annotation-xml><annotation encoding="application/x-tex" id="A3.T3.2.2.2.2.2.m1.1c">\uparrow</annotation><annotation encoding="application/x-llamapun" id="A3.T3.2.2.2.2.2.m1.1d">↑</annotation></semantics></math>
</td>
<td class="ltx_td ltx_align_center ltx_border_tt" id="A3.T3.3.3.3.3.3">SSIM <math alttext="\uparrow" class="ltx_Math" display="inline" id="A3.T3.3.3.3.3.3.m1.1"><semantics id="A3.T3.3.3.3.3.3.m1.1a"><mo id="A3.T3.3.3.3.3.3.m1.1.1" stretchy="false" xref="A3.T3.3.3.3.3.3.m1.1.1.cmml">↑</mo><annotation-xml encoding="MathML-Content" id="A3.T3.3.3.3.3.3.m1.1b"><ci id="A3.T3.3.3.3.3.3.m1.1.1.cmml" xref="A3.T3.3.3.3.3.3.m1.1.1">↑</ci></annotation-xml><annotation encoding="application/x-tex" id="A3.T3.3.3.3.3.3.m1.1c">\uparrow</annotation><annotation encoding="application/x-llamapun" id="A3.T3.3.3.3.3.3.m1.1d">↑</annotation></semantics></math>
</td>
<td class="ltx_td ltx_align_center ltx_border_tt" id="A3.T3.4.4.4.4.4">LPIPS <math alttext="\downarrow" class="ltx_Math" display="inline" id="A3.T3.4.4.4.4.4.m1.1"><semantics id="A3.T3.4.4.4.4.4.m1.1a"><mo id="A3.T3.4.4.4.4.4.m1.1.1" stretchy="false" xref="A3.T3.4.4.4.4.4.m1.1.1.cmml">↓</mo><annotation-xml encoding="MathML-Content" id="A3.T3.4.4.4.4.4.m1.1b"><ci id="A3.T3.4.4.4.4.4.m1.1.1.cmml" xref="A3.T3.4.4.4.4.4.m1.1.1">↓</ci></annotation-xml><annotation encoding="application/x-tex" id="A3.T3.4.4.4.4.4.m1.1c">\downarrow</annotation><annotation encoding="application/x-llamapun" id="A3.T3.4.4.4.4.4.m1.1d">↓</annotation></semantics></math>
</td>
<td class="ltx_td ltx_align_center ltx_border_tt" id="A3.T3.5.5.5.5.5">FID <math alttext="\downarrow" class="ltx_Math" display="inline" id="A3.T3.5.5.5.5.5.m1.1"><semantics id="A3.T3.5.5.5.5.5.m1.1a"><mo id="A3.T3.5.5.5.5.5.m1.1.1" stretchy="false" xref="A3.T3.5.5.5.5.5.m1.1.1.cmml">↓</mo><annotation-xml encoding="MathML-Content" id="A3.T3.5.5.5.5.5.m1.1b"><ci id="A3.T3.5.5.5.5.5.m1.1.1.cmml" xref="A3.T3.5.5.5.5.5.m1.1.1">↓</ci></annotation-xml><annotation encoding="application/x-tex" id="A3.T3.5.5.5.5.5.m1.1c">\downarrow</annotation><annotation encoding="application/x-llamapun" id="A3.T3.5.5.5.5.5.m1.1d">↓</annotation></semantics></math>
</td>
<td class="ltx_td ltx_align_center ltx_border_tt" id="A3.T3.6.6.6.6.6">TPR@0.1%FPR <math alttext="\uparrow" class="ltx_Math" display="inline" id="A3.T3.6.6.6.6.6.m1.1"><semantics id="A3.T3.6.6.6.6.6.m1.1a"><mo id="A3.T3.6.6.6.6.6.m1.1.1" stretchy="false" xref="A3.T3.6.6.6.6.6.m1.1.1.cmml">↑</mo><annotation-xml encoding="MathML-Content" id="A3.T3.6.6.6.6.6.m1.1b"><ci id="A3.T3.6.6.6.6.6.m1.1.1.cmml" xref="A3.T3.6.6.6.6.6.m1.1.1">↑</ci></annotation-xml><annotation encoding="application/x-tex" id="A3.T3.6.6.6.6.6.m1.1c">\uparrow</annotation><annotation encoding="application/x-llamapun" id="A3.T3.6.6.6.6.6.m1.1d">↑</annotation></semantics></math> (%)</td>
</tr>
<tr class="ltx_tr" id="A3.T3.7.7.7.7">
<td class="ltx_td ltx_align_left ltx_border_t" id="A3.T3.7.7.7.7.2">MBRS <cite class="ltx_cite ltx_citemacro_citep">(Jia et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib28" title="">2021</a>)</cite>
</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A3.T3.7.7.7.7.1">128 <math alttext="\times" class="ltx_Math" display="inline" id="A3.T3.7.7.7.7.1.m1.1"><semantics id="A3.T3.7.7.7.7.1.m1.1a"><mo id="A3.T3.7.7.7.7.1.m1.1.1" xref="A3.T3.7.7.7.7.1.m1.1.1.cmml">×</mo><annotation-xml encoding="MathML-Content" id="A3.T3.7.7.7.7.1.m1.1b"><times id="A3.T3.7.7.7.7.1.m1.1.1.cmml" xref="A3.T3.7.7.7.7.1.m1.1.1"></times></annotation-xml><annotation encoding="application/x-tex" id="A3.T3.7.7.7.7.1.m1.1c">\times</annotation><annotation encoding="application/x-llamapun" id="A3.T3.7.7.7.7.1.m1.1d">×</annotation></semantics></math> 128</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A3.T3.7.7.7.7.3">30</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A3.T3.7.7.7.7.4">25.14</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A3.T3.7.7.7.7.5">0.8348</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A3.T3.7.7.7.7.6">0.0821</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A3.T3.7.7.7.7.7">13.51</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A3.T3.7.7.7.7.8">100.0</td>
</tr>
<tr class="ltx_tr" id="A3.T3.8.8.8.8">
<td class="ltx_td ltx_align_left" id="A3.T3.8.8.8.8.2">CIN <cite class="ltx_cite ltx_citemacro_citep">(Ma et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib44" title="">2022</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A3.T3.8.8.8.8.1">128 <math alttext="\times" class="ltx_Math" display="inline" id="A3.T3.8.8.8.8.1.m1.1"><semantics id="A3.T3.8.8.8.8.1.m1.1a"><mo id="A3.T3.8.8.8.8.1.m1.1.1" xref="A3.T3.8.8.8.8.1.m1.1.1.cmml">×</mo><annotation-xml encoding="MathML-Content" id="A3.T3.8.8.8.8.1.m1.1b"><times id="A3.T3.8.8.8.8.1.m1.1.1.cmml" xref="A3.T3.8.8.8.8.1.m1.1.1"></times></annotation-xml><annotation encoding="application/x-tex" id="A3.T3.8.8.8.8.1.m1.1c">\times</annotation><annotation encoding="application/x-llamapun" id="A3.T3.8.8.8.8.1.m1.1d">×</annotation></semantics></math> 128</td>
<td class="ltx_td ltx_align_center" id="A3.T3.8.8.8.8.3">30</td>
<td class="ltx_td ltx_align_center" id="A3.T3.8.8.8.8.4"><span class="ltx_text ltx_font_bold" id="A3.T3.8.8.8.8.4.1">41.70</span></td>
<td class="ltx_td ltx_align_center" id="A3.T3.8.8.8.8.5">0.9812</td>
<td class="ltx_td ltx_align_center" id="A3.T3.8.8.8.8.6"><span class="ltx_text ltx_font_bold" id="A3.T3.8.8.8.8.6.1">0.0011</span></td>
<td class="ltx_td ltx_align_center" id="A3.T3.8.8.8.8.7">2.20</td>
<td class="ltx_td ltx_align_center" id="A3.T3.8.8.8.8.8">100.0</td>
</tr>
<tr class="ltx_tr" id="A3.T3.9.9.9.9">
<td class="ltx_td ltx_align_left" id="A3.T3.9.9.9.9.2">PIMoG <cite class="ltx_cite ltx_citemacro_citep">(Fang et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib18" title="">2022</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A3.T3.9.9.9.9.1">128 <math alttext="\times" class="ltx_Math" display="inline" id="A3.T3.9.9.9.9.1.m1.1"><semantics id="A3.T3.9.9.9.9.1.m1.1a"><mo id="A3.T3.9.9.9.9.1.m1.1.1" xref="A3.T3.9.9.9.9.1.m1.1.1.cmml">×</mo><annotation-xml encoding="MathML-Content" id="A3.T3.9.9.9.9.1.m1.1b"><times id="A3.T3.9.9.9.9.1.m1.1.1.cmml" xref="A3.T3.9.9.9.9.1.m1.1.1"></times></annotation-xml><annotation encoding="application/x-tex" id="A3.T3.9.9.9.9.1.m1.1c">\times</annotation><annotation encoding="application/x-llamapun" id="A3.T3.9.9.9.9.1.m1.1d">×</annotation></semantics></math> 128</td>
<td class="ltx_td ltx_align_center" id="A3.T3.9.9.9.9.3">30</td>
<td class="ltx_td ltx_align_center" id="A3.T3.9.9.9.9.4">37.54</td>
<td class="ltx_td ltx_align_center" id="A3.T3.9.9.9.9.5">0.9814</td>
<td class="ltx_td ltx_align_center" id="A3.T3.9.9.9.9.6">0.0140</td>
<td class="ltx_td ltx_align_center" id="A3.T3.9.9.9.9.7">2.97</td>
<td class="ltx_td ltx_align_center" id="A3.T3.9.9.9.9.8">100.0</td>
</tr>
<tr class="ltx_tr" id="A3.T3.10.10.10.10">
<td class="ltx_td ltx_align_left" id="A3.T3.10.10.10.10.2">SepMark <cite class="ltx_cite ltx_citemacro_citep">(Wu et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib75" title="">2023</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A3.T3.10.10.10.10.1">128 <math alttext="\times" class="ltx_Math" display="inline" id="A3.T3.10.10.10.10.1.m1.1"><semantics id="A3.T3.10.10.10.10.1.m1.1a"><mo id="A3.T3.10.10.10.10.1.m1.1.1" xref="A3.T3.10.10.10.10.1.m1.1.1.cmml">×</mo><annotation-xml encoding="MathML-Content" id="A3.T3.10.10.10.10.1.m1.1b"><times id="A3.T3.10.10.10.10.1.m1.1.1.cmml" xref="A3.T3.10.10.10.10.1.m1.1.1"></times></annotation-xml><annotation encoding="application/x-tex" id="A3.T3.10.10.10.10.1.m1.1c">\times</annotation><annotation encoding="application/x-llamapun" id="A3.T3.10.10.10.10.1.m1.1d">×</annotation></semantics></math> 128</td>
<td class="ltx_td ltx_align_center" id="A3.T3.10.10.10.10.3">30</td>
<td class="ltx_td ltx_align_center" id="A3.T3.10.10.10.10.4">35.50</td>
<td class="ltx_td ltx_align_center" id="A3.T3.10.10.10.10.5">0.9648</td>
<td class="ltx_td ltx_align_center" id="A3.T3.10.10.10.10.6">0.0116</td>
<td class="ltx_td ltx_align_center" id="A3.T3.10.10.10.10.7">2.95</td>
<td class="ltx_td ltx_align_center" id="A3.T3.10.10.10.10.8">100.0</td>
</tr>
<tr class="ltx_tr" id="A3.T3.11.11.11.11">
<td class="ltx_td ltx_align_left" id="A3.T3.11.11.11.11.2">StegaStamp <cite class="ltx_cite ltx_citemacro_citep">(Tancik et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib69" title="">2020</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A3.T3.11.11.11.11.1">400 <math alttext="\times" class="ltx_Math" display="inline" id="A3.T3.11.11.11.11.1.m1.1"><semantics id="A3.T3.11.11.11.11.1.m1.1a"><mo id="A3.T3.11.11.11.11.1.m1.1.1" xref="A3.T3.11.11.11.11.1.m1.1.1.cmml">×</mo><annotation-xml encoding="MathML-Content" id="A3.T3.11.11.11.11.1.m1.1b"><times id="A3.T3.11.11.11.11.1.m1.1.1.cmml" xref="A3.T3.11.11.11.11.1.m1.1.1"></times></annotation-xml><annotation encoding="application/x-tex" id="A3.T3.11.11.11.11.1.m1.1c">\times</annotation><annotation encoding="application/x-llamapun" id="A3.T3.11.11.11.11.1.m1.1d">×</annotation></semantics></math> 400</td>
<td class="ltx_td ltx_align_center" id="A3.T3.11.11.11.11.3">100</td>
<td class="ltx_td ltx_align_center" id="A3.T3.11.11.11.11.4">29.33</td>
<td class="ltx_td ltx_align_center" id="A3.T3.11.11.11.11.5">0.8992</td>
<td class="ltx_td ltx_align_center" id="A3.T3.11.11.11.11.6">0.1018</td>
<td class="ltx_td ltx_align_center" id="A3.T3.11.11.11.11.7">8.29</td>
<td class="ltx_td ltx_align_center" id="A3.T3.11.11.11.11.8">100.0</td>
</tr>
<tr class="ltx_tr" id="A3.T3.12.12.12.12">
<td class="ltx_td ltx_align_left" id="A3.T3.12.12.12.12.2">TrustMark <cite class="ltx_cite ltx_citemacro_citep">(Bui et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib8" title="">2023</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A3.T3.12.12.12.12.1">256 <math alttext="\times" class="ltx_Math" display="inline" id="A3.T3.12.12.12.12.1.m1.1"><semantics id="A3.T3.12.12.12.12.1.m1.1a"><mo id="A3.T3.12.12.12.12.1.m1.1.1" xref="A3.T3.12.12.12.12.1.m1.1.1.cmml">×</mo><annotation-xml encoding="MathML-Content" id="A3.T3.12.12.12.12.1.m1.1b"><times id="A3.T3.12.12.12.12.1.m1.1.1.cmml" xref="A3.T3.12.12.12.12.1.m1.1.1"></times></annotation-xml><annotation encoding="application/x-tex" id="A3.T3.12.12.12.12.1.m1.1c">\times</annotation><annotation encoding="application/x-llamapun" id="A3.T3.12.12.12.12.1.m1.1d">×</annotation></semantics></math> 256</td>
<td class="ltx_td ltx_align_center" id="A3.T3.12.12.12.12.3">100</td>
<td class="ltx_td ltx_align_center" id="A3.T3.12.12.12.12.4"><span class="ltx_text ltx_framed ltx_framed_underline" id="A3.T3.12.12.12.12.4.1">40.94</span></td>
<td class="ltx_td ltx_align_center" id="A3.T3.12.12.12.12.5">0.9819</td>
<td class="ltx_td ltx_align_center" id="A3.T3.12.12.12.12.6"><span class="ltx_text ltx_framed ltx_framed_underline" id="A3.T3.12.12.12.12.6.1">0.0015</span></td>
<td class="ltx_td ltx_align_center" id="A3.T3.12.12.12.12.7">1.04</td>
<td class="ltx_td ltx_align_center" id="A3.T3.12.12.12.12.8">100.0</td>
</tr>
<tr class="ltx_tr" id="A3.T3.13.13.13.13">
<td class="ltx_td ltx_align_left ltx_border_t" id="A3.T3.13.13.13.13.2">VINE-Base</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A3.T3.13.13.13.13.1">256 <math alttext="\times" class="ltx_Math" display="inline" id="A3.T3.13.13.13.13.1.m1.1"><semantics id="A3.T3.13.13.13.13.1.m1.1a"><mo id="A3.T3.13.13.13.13.1.m1.1.1" xref="A3.T3.13.13.13.13.1.m1.1.1.cmml">×</mo><annotation-xml encoding="MathML-Content" id="A3.T3.13.13.13.13.1.m1.1b"><times id="A3.T3.13.13.13.13.1.m1.1.1.cmml" xref="A3.T3.13.13.13.13.1.m1.1.1"></times></annotation-xml><annotation encoding="application/x-tex" id="A3.T3.13.13.13.13.1.m1.1c">\times</annotation><annotation encoding="application/x-llamapun" id="A3.T3.13.13.13.13.1.m1.1d">×</annotation></semantics></math> 256</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A3.T3.13.13.13.13.3">100</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A3.T3.13.13.13.13.4">40.22</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A3.T3.13.13.13.13.5"><span class="ltx_text ltx_font_bold" id="A3.T3.13.13.13.13.5.1">0.9961</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A3.T3.13.13.13.13.6">0.0022</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A3.T3.13.13.13.13.7"><span class="ltx_text ltx_font_bold" id="A3.T3.13.13.13.13.7.1">0.10</span></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A3.T3.13.13.13.13.8">100.0</td>
</tr>
<tr class="ltx_tr" id="A3.T3.14.14.14.14">
<td class="ltx_td ltx_align_left ltx_border_bb" id="A3.T3.14.14.14.14.2">VINE-Robust</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A3.T3.14.14.14.14.1">256 <math alttext="\times" class="ltx_Math" display="inline" id="A3.T3.14.14.14.14.1.m1.1"><semantics id="A3.T3.14.14.14.14.1.m1.1a"><mo id="A3.T3.14.14.14.14.1.m1.1.1" xref="A3.T3.14.14.14.14.1.m1.1.1.cmml">×</mo><annotation-xml encoding="MathML-Content" id="A3.T3.14.14.14.14.1.m1.1b"><times id="A3.T3.14.14.14.14.1.m1.1.1.cmml" xref="A3.T3.14.14.14.14.1.m1.1.1"></times></annotation-xml><annotation encoding="application/x-tex" id="A3.T3.14.14.14.14.1.m1.1c">\times</annotation><annotation encoding="application/x-llamapun" id="A3.T3.14.14.14.14.1.m1.1d">×</annotation></semantics></math> 256</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A3.T3.14.14.14.14.3">100</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A3.T3.14.14.14.14.4">37.07</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A3.T3.14.14.14.14.5"><span class="ltx_text ltx_framed ltx_framed_underline" id="A3.T3.14.14.14.14.5.1">0.9942</span></td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A3.T3.14.14.14.14.6">0.0048</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A3.T3.14.14.14.14.7"><span class="ltx_text ltx_framed ltx_framed_underline" id="A3.T3.14.14.14.14.7.1">0.19</span></td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A3.T3.14.14.14.14.8">100.0</td>
</tr>
</table>{{< /table-caption >}}
> 🔼 Table 3 presents a detailed comparison of different watermarking methods' performance.  It assesses both the quality of the watermarked images and the accuracy of watermark detection under ideal conditions (no image distortions or edits).  Image quality is measured using PSNR, SSIM, LPIPS, and FID.  Detection accuracy is represented by the True Positive Rate at 0.1% False Positive Rate (TPR@0.1%FPR).  The table shows each method's encoding capacity (number of bits embedded), and the best and second-best performance values for each metric are highlighted.  This allows for a comprehensive comparison of the methods' effectiveness in terms of both image quality and robustness before any attacks are applied.
> <details>
> <summary>read the caption</summary>
> Table 3: Comparison of watermarking performance, evaluating both image quality of the watermarked images and detection accuracy under normal conditions (no distortion or editing applied) at the original training resolution. The best value in each column is highlighted in bold, and the second best value is underlined.
> </details>

{{< table-caption >}}
<table class="ltx_tabular ltx_align_middle" id="A6.T4.9.9.9">
<tr class="ltx_tr" id="A6.T4.9.9.9.10">
<td class="ltx_td ltx_align_left ltx_border_tt" id="A6.T4.9.9.9.10.1" rowspan="2"><span class="ltx_text" id="A6.T4.9.9.9.10.1.1">Method</span></td>
<td class="ltx_td ltx_align_center ltx_border_tt" colspan="3" id="A6.T4.9.9.9.10.2">Instruct-Pix2Pix</td>
<td class="ltx_td ltx_align_center ltx_border_tt" colspan="3" id="A6.T4.9.9.9.10.3">UltraEdit</td>
<td class="ltx_td ltx_align_center ltx_border_tt" colspan="3" id="A6.T4.9.9.9.10.4">MagicBrush</td>
</tr>
<tr class="ltx_tr" id="A6.T4.9.9.9.9">
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.1.1.1.1.1"><math alttext="\text{CLIP}_{\text{dir}}\uparrow" class="ltx_Math" display="inline" id="A6.T4.1.1.1.1.1.m1.1"><semantics id="A6.T4.1.1.1.1.1.m1.1a"><mrow id="A6.T4.1.1.1.1.1.m1.1.1" xref="A6.T4.1.1.1.1.1.m1.1.1.cmml"><msub id="A6.T4.1.1.1.1.1.m1.1.1.2" xref="A6.T4.1.1.1.1.1.m1.1.1.2.cmml"><mtext id="A6.T4.1.1.1.1.1.m1.1.1.2.2" xref="A6.T4.1.1.1.1.1.m1.1.1.2.2a.cmml">CLIP</mtext><mtext id="A6.T4.1.1.1.1.1.m1.1.1.2.3" xref="A6.T4.1.1.1.1.1.m1.1.1.2.3a.cmml">dir</mtext></msub><mo id="A6.T4.1.1.1.1.1.m1.1.1.1" stretchy="false" xref="A6.T4.1.1.1.1.1.m1.1.1.1.cmml">↑</mo><mi id="A6.T4.1.1.1.1.1.m1.1.1.3" xref="A6.T4.1.1.1.1.1.m1.1.1.3.cmml"></mi></mrow><annotation-xml encoding="MathML-Content" id="A6.T4.1.1.1.1.1.m1.1b"><apply id="A6.T4.1.1.1.1.1.m1.1.1.cmml" xref="A6.T4.1.1.1.1.1.m1.1.1"><ci id="A6.T4.1.1.1.1.1.m1.1.1.1.cmml" xref="A6.T4.1.1.1.1.1.m1.1.1.1">↑</ci><apply id="A6.T4.1.1.1.1.1.m1.1.1.2.cmml" xref="A6.T4.1.1.1.1.1.m1.1.1.2"><csymbol cd="ambiguous" id="A6.T4.1.1.1.1.1.m1.1.1.2.1.cmml" xref="A6.T4.1.1.1.1.1.m1.1.1.2">subscript</csymbol><ci id="A6.T4.1.1.1.1.1.m1.1.1.2.2a.cmml" xref="A6.T4.1.1.1.1.1.m1.1.1.2.2"><mtext id="A6.T4.1.1.1.1.1.m1.1.1.2.2.cmml" xref="A6.T4.1.1.1.1.1.m1.1.1.2.2">CLIP</mtext></ci><ci id="A6.T4.1.1.1.1.1.m1.1.1.2.3a.cmml" xref="A6.T4.1.1.1.1.1.m1.1.1.2.3"><mtext id="A6.T4.1.1.1.1.1.m1.1.1.2.3.cmml" mathsize="70%" xref="A6.T4.1.1.1.1.1.m1.1.1.2.3">dir</mtext></ci></apply><csymbol cd="latexml" id="A6.T4.1.1.1.1.1.m1.1.1.3.cmml" xref="A6.T4.1.1.1.1.1.m1.1.1.3">absent</csymbol></apply></annotation-xml><annotation encoding="application/x-tex" id="A6.T4.1.1.1.1.1.m1.1c">\text{CLIP}_{\text{dir}}\uparrow</annotation><annotation encoding="application/x-llamapun" id="A6.T4.1.1.1.1.1.m1.1d">CLIP start_POSTSUBSCRIPT dir end_POSTSUBSCRIPT ↑</annotation></semantics></math></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.2.2.2.2.2"><math alttext="\text{CLIP}_{\text{img}}\uparrow" class="ltx_Math" display="inline" id="A6.T4.2.2.2.2.2.m1.1"><semantics id="A6.T4.2.2.2.2.2.m1.1a"><mrow id="A6.T4.2.2.2.2.2.m1.1.1" xref="A6.T4.2.2.2.2.2.m1.1.1.cmml"><msub id="A6.T4.2.2.2.2.2.m1.1.1.2" xref="A6.T4.2.2.2.2.2.m1.1.1.2.cmml"><mtext id="A6.T4.2.2.2.2.2.m1.1.1.2.2" xref="A6.T4.2.2.2.2.2.m1.1.1.2.2a.cmml">CLIP</mtext><mtext id="A6.T4.2.2.2.2.2.m1.1.1.2.3" xref="A6.T4.2.2.2.2.2.m1.1.1.2.3a.cmml">img</mtext></msub><mo id="A6.T4.2.2.2.2.2.m1.1.1.1" stretchy="false" xref="A6.T4.2.2.2.2.2.m1.1.1.1.cmml">↑</mo><mi id="A6.T4.2.2.2.2.2.m1.1.1.3" xref="A6.T4.2.2.2.2.2.m1.1.1.3.cmml"></mi></mrow><annotation-xml encoding="MathML-Content" id="A6.T4.2.2.2.2.2.m1.1b"><apply id="A6.T4.2.2.2.2.2.m1.1.1.cmml" xref="A6.T4.2.2.2.2.2.m1.1.1"><ci id="A6.T4.2.2.2.2.2.m1.1.1.1.cmml" xref="A6.T4.2.2.2.2.2.m1.1.1.1">↑</ci><apply id="A6.T4.2.2.2.2.2.m1.1.1.2.cmml" xref="A6.T4.2.2.2.2.2.m1.1.1.2"><csymbol cd="ambiguous" id="A6.T4.2.2.2.2.2.m1.1.1.2.1.cmml" xref="A6.T4.2.2.2.2.2.m1.1.1.2">subscript</csymbol><ci id="A6.T4.2.2.2.2.2.m1.1.1.2.2a.cmml" xref="A6.T4.2.2.2.2.2.m1.1.1.2.2"><mtext id="A6.T4.2.2.2.2.2.m1.1.1.2.2.cmml" xref="A6.T4.2.2.2.2.2.m1.1.1.2.2">CLIP</mtext></ci><ci id="A6.T4.2.2.2.2.2.m1.1.1.2.3a.cmml" xref="A6.T4.2.2.2.2.2.m1.1.1.2.3"><mtext id="A6.T4.2.2.2.2.2.m1.1.1.2.3.cmml" mathsize="70%" xref="A6.T4.2.2.2.2.2.m1.1.1.2.3">img</mtext></ci></apply><csymbol cd="latexml" id="A6.T4.2.2.2.2.2.m1.1.1.3.cmml" xref="A6.T4.2.2.2.2.2.m1.1.1.3">absent</csymbol></apply></annotation-xml><annotation encoding="application/x-tex" id="A6.T4.2.2.2.2.2.m1.1c">\text{CLIP}_{\text{img}}\uparrow</annotation><annotation encoding="application/x-llamapun" id="A6.T4.2.2.2.2.2.m1.1d">CLIP start_POSTSUBSCRIPT img end_POSTSUBSCRIPT ↑</annotation></semantics></math></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.3.3.3.3.3"><math alttext="\text{CLIP}_{\text{out}}\uparrow" class="ltx_Math" display="inline" id="A6.T4.3.3.3.3.3.m1.1"><semantics id="A6.T4.3.3.3.3.3.m1.1a"><mrow id="A6.T4.3.3.3.3.3.m1.1.1" xref="A6.T4.3.3.3.3.3.m1.1.1.cmml"><msub id="A6.T4.3.3.3.3.3.m1.1.1.2" xref="A6.T4.3.3.3.3.3.m1.1.1.2.cmml"><mtext id="A6.T4.3.3.3.3.3.m1.1.1.2.2" xref="A6.T4.3.3.3.3.3.m1.1.1.2.2a.cmml">CLIP</mtext><mtext id="A6.T4.3.3.3.3.3.m1.1.1.2.3" xref="A6.T4.3.3.3.3.3.m1.1.1.2.3a.cmml">out</mtext></msub><mo id="A6.T4.3.3.3.3.3.m1.1.1.1" stretchy="false" xref="A6.T4.3.3.3.3.3.m1.1.1.1.cmml">↑</mo><mi id="A6.T4.3.3.3.3.3.m1.1.1.3" xref="A6.T4.3.3.3.3.3.m1.1.1.3.cmml"></mi></mrow><annotation-xml encoding="MathML-Content" id="A6.T4.3.3.3.3.3.m1.1b"><apply id="A6.T4.3.3.3.3.3.m1.1.1.cmml" xref="A6.T4.3.3.3.3.3.m1.1.1"><ci id="A6.T4.3.3.3.3.3.m1.1.1.1.cmml" xref="A6.T4.3.3.3.3.3.m1.1.1.1">↑</ci><apply id="A6.T4.3.3.3.3.3.m1.1.1.2.cmml" xref="A6.T4.3.3.3.3.3.m1.1.1.2"><csymbol cd="ambiguous" id="A6.T4.3.3.3.3.3.m1.1.1.2.1.cmml" xref="A6.T4.3.3.3.3.3.m1.1.1.2">subscript</csymbol><ci id="A6.T4.3.3.3.3.3.m1.1.1.2.2a.cmml" xref="A6.T4.3.3.3.3.3.m1.1.1.2.2"><mtext id="A6.T4.3.3.3.3.3.m1.1.1.2.2.cmml" xref="A6.T4.3.3.3.3.3.m1.1.1.2.2">CLIP</mtext></ci><ci id="A6.T4.3.3.3.3.3.m1.1.1.2.3a.cmml" xref="A6.T4.3.3.3.3.3.m1.1.1.2.3"><mtext id="A6.T4.3.3.3.3.3.m1.1.1.2.3.cmml" mathsize="70%" xref="A6.T4.3.3.3.3.3.m1.1.1.2.3">out</mtext></ci></apply><csymbol cd="latexml" id="A6.T4.3.3.3.3.3.m1.1.1.3.cmml" xref="A6.T4.3.3.3.3.3.m1.1.1.3">absent</csymbol></apply></annotation-xml><annotation encoding="application/x-tex" id="A6.T4.3.3.3.3.3.m1.1c">\text{CLIP}_{\text{out}}\uparrow</annotation><annotation encoding="application/x-llamapun" id="A6.T4.3.3.3.3.3.m1.1d">CLIP start_POSTSUBSCRIPT out end_POSTSUBSCRIPT ↑</annotation></semantics></math></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.4.4.4.4.4"><math alttext="\text{CLIP}_{\text{dir}}\uparrow" class="ltx_Math" display="inline" id="A6.T4.4.4.4.4.4.m1.1"><semantics id="A6.T4.4.4.4.4.4.m1.1a"><mrow id="A6.T4.4.4.4.4.4.m1.1.1" xref="A6.T4.4.4.4.4.4.m1.1.1.cmml"><msub id="A6.T4.4.4.4.4.4.m1.1.1.2" xref="A6.T4.4.4.4.4.4.m1.1.1.2.cmml"><mtext id="A6.T4.4.4.4.4.4.m1.1.1.2.2" xref="A6.T4.4.4.4.4.4.m1.1.1.2.2a.cmml">CLIP</mtext><mtext id="A6.T4.4.4.4.4.4.m1.1.1.2.3" xref="A6.T4.4.4.4.4.4.m1.1.1.2.3a.cmml">dir</mtext></msub><mo id="A6.T4.4.4.4.4.4.m1.1.1.1" stretchy="false" xref="A6.T4.4.4.4.4.4.m1.1.1.1.cmml">↑</mo><mi id="A6.T4.4.4.4.4.4.m1.1.1.3" xref="A6.T4.4.4.4.4.4.m1.1.1.3.cmml"></mi></mrow><annotation-xml encoding="MathML-Content" id="A6.T4.4.4.4.4.4.m1.1b"><apply id="A6.T4.4.4.4.4.4.m1.1.1.cmml" xref="A6.T4.4.4.4.4.4.m1.1.1"><ci id="A6.T4.4.4.4.4.4.m1.1.1.1.cmml" xref="A6.T4.4.4.4.4.4.m1.1.1.1">↑</ci><apply id="A6.T4.4.4.4.4.4.m1.1.1.2.cmml" xref="A6.T4.4.4.4.4.4.m1.1.1.2"><csymbol cd="ambiguous" id="A6.T4.4.4.4.4.4.m1.1.1.2.1.cmml" xref="A6.T4.4.4.4.4.4.m1.1.1.2">subscript</csymbol><ci id="A6.T4.4.4.4.4.4.m1.1.1.2.2a.cmml" xref="A6.T4.4.4.4.4.4.m1.1.1.2.2"><mtext id="A6.T4.4.4.4.4.4.m1.1.1.2.2.cmml" xref="A6.T4.4.4.4.4.4.m1.1.1.2.2">CLIP</mtext></ci><ci id="A6.T4.4.4.4.4.4.m1.1.1.2.3a.cmml" xref="A6.T4.4.4.4.4.4.m1.1.1.2.3"><mtext id="A6.T4.4.4.4.4.4.m1.1.1.2.3.cmml" mathsize="70%" xref="A6.T4.4.4.4.4.4.m1.1.1.2.3">dir</mtext></ci></apply><csymbol cd="latexml" id="A6.T4.4.4.4.4.4.m1.1.1.3.cmml" xref="A6.T4.4.4.4.4.4.m1.1.1.3">absent</csymbol></apply></annotation-xml><annotation encoding="application/x-tex" id="A6.T4.4.4.4.4.4.m1.1c">\text{CLIP}_{\text{dir}}\uparrow</annotation><annotation encoding="application/x-llamapun" id="A6.T4.4.4.4.4.4.m1.1d">CLIP start_POSTSUBSCRIPT dir end_POSTSUBSCRIPT ↑</annotation></semantics></math></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.5.5.5.5.5"><math alttext="\text{CLIP}_{\text{img}}\uparrow" class="ltx_Math" display="inline" id="A6.T4.5.5.5.5.5.m1.1"><semantics id="A6.T4.5.5.5.5.5.m1.1a"><mrow id="A6.T4.5.5.5.5.5.m1.1.1" xref="A6.T4.5.5.5.5.5.m1.1.1.cmml"><msub id="A6.T4.5.5.5.5.5.m1.1.1.2" xref="A6.T4.5.5.5.5.5.m1.1.1.2.cmml"><mtext id="A6.T4.5.5.5.5.5.m1.1.1.2.2" xref="A6.T4.5.5.5.5.5.m1.1.1.2.2a.cmml">CLIP</mtext><mtext id="A6.T4.5.5.5.5.5.m1.1.1.2.3" xref="A6.T4.5.5.5.5.5.m1.1.1.2.3a.cmml">img</mtext></msub><mo id="A6.T4.5.5.5.5.5.m1.1.1.1" stretchy="false" xref="A6.T4.5.5.5.5.5.m1.1.1.1.cmml">↑</mo><mi id="A6.T4.5.5.5.5.5.m1.1.1.3" xref="A6.T4.5.5.5.5.5.m1.1.1.3.cmml"></mi></mrow><annotation-xml encoding="MathML-Content" id="A6.T4.5.5.5.5.5.m1.1b"><apply id="A6.T4.5.5.5.5.5.m1.1.1.cmml" xref="A6.T4.5.5.5.5.5.m1.1.1"><ci id="A6.T4.5.5.5.5.5.m1.1.1.1.cmml" xref="A6.T4.5.5.5.5.5.m1.1.1.1">↑</ci><apply id="A6.T4.5.5.5.5.5.m1.1.1.2.cmml" xref="A6.T4.5.5.5.5.5.m1.1.1.2"><csymbol cd="ambiguous" id="A6.T4.5.5.5.5.5.m1.1.1.2.1.cmml" xref="A6.T4.5.5.5.5.5.m1.1.1.2">subscript</csymbol><ci id="A6.T4.5.5.5.5.5.m1.1.1.2.2a.cmml" xref="A6.T4.5.5.5.5.5.m1.1.1.2.2"><mtext id="A6.T4.5.5.5.5.5.m1.1.1.2.2.cmml" xref="A6.T4.5.5.5.5.5.m1.1.1.2.2">CLIP</mtext></ci><ci id="A6.T4.5.5.5.5.5.m1.1.1.2.3a.cmml" xref="A6.T4.5.5.5.5.5.m1.1.1.2.3"><mtext id="A6.T4.5.5.5.5.5.m1.1.1.2.3.cmml" mathsize="70%" xref="A6.T4.5.5.5.5.5.m1.1.1.2.3">img</mtext></ci></apply><csymbol cd="latexml" id="A6.T4.5.5.5.5.5.m1.1.1.3.cmml" xref="A6.T4.5.5.5.5.5.m1.1.1.3">absent</csymbol></apply></annotation-xml><annotation encoding="application/x-tex" id="A6.T4.5.5.5.5.5.m1.1c">\text{CLIP}_{\text{img}}\uparrow</annotation><annotation encoding="application/x-llamapun" id="A6.T4.5.5.5.5.5.m1.1d">CLIP start_POSTSUBSCRIPT img end_POSTSUBSCRIPT ↑</annotation></semantics></math></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.6.6.6.6.6"><math alttext="\text{CLIP}_{\text{out}}\uparrow" class="ltx_Math" display="inline" id="A6.T4.6.6.6.6.6.m1.1"><semantics id="A6.T4.6.6.6.6.6.m1.1a"><mrow id="A6.T4.6.6.6.6.6.m1.1.1" xref="A6.T4.6.6.6.6.6.m1.1.1.cmml"><msub id="A6.T4.6.6.6.6.6.m1.1.1.2" xref="A6.T4.6.6.6.6.6.m1.1.1.2.cmml"><mtext id="A6.T4.6.6.6.6.6.m1.1.1.2.2" xref="A6.T4.6.6.6.6.6.m1.1.1.2.2a.cmml">CLIP</mtext><mtext id="A6.T4.6.6.6.6.6.m1.1.1.2.3" xref="A6.T4.6.6.6.6.6.m1.1.1.2.3a.cmml">out</mtext></msub><mo id="A6.T4.6.6.6.6.6.m1.1.1.1" stretchy="false" xref="A6.T4.6.6.6.6.6.m1.1.1.1.cmml">↑</mo><mi id="A6.T4.6.6.6.6.6.m1.1.1.3" xref="A6.T4.6.6.6.6.6.m1.1.1.3.cmml"></mi></mrow><annotation-xml encoding="MathML-Content" id="A6.T4.6.6.6.6.6.m1.1b"><apply id="A6.T4.6.6.6.6.6.m1.1.1.cmml" xref="A6.T4.6.6.6.6.6.m1.1.1"><ci id="A6.T4.6.6.6.6.6.m1.1.1.1.cmml" xref="A6.T4.6.6.6.6.6.m1.1.1.1">↑</ci><apply id="A6.T4.6.6.6.6.6.m1.1.1.2.cmml" xref="A6.T4.6.6.6.6.6.m1.1.1.2"><csymbol cd="ambiguous" id="A6.T4.6.6.6.6.6.m1.1.1.2.1.cmml" xref="A6.T4.6.6.6.6.6.m1.1.1.2">subscript</csymbol><ci id="A6.T4.6.6.6.6.6.m1.1.1.2.2a.cmml" xref="A6.T4.6.6.6.6.6.m1.1.1.2.2"><mtext id="A6.T4.6.6.6.6.6.m1.1.1.2.2.cmml" xref="A6.T4.6.6.6.6.6.m1.1.1.2.2">CLIP</mtext></ci><ci id="A6.T4.6.6.6.6.6.m1.1.1.2.3a.cmml" xref="A6.T4.6.6.6.6.6.m1.1.1.2.3"><mtext id="A6.T4.6.6.6.6.6.m1.1.1.2.3.cmml" mathsize="70%" xref="A6.T4.6.6.6.6.6.m1.1.1.2.3">out</mtext></ci></apply><csymbol cd="latexml" id="A6.T4.6.6.6.6.6.m1.1.1.3.cmml" xref="A6.T4.6.6.6.6.6.m1.1.1.3">absent</csymbol></apply></annotation-xml><annotation encoding="application/x-tex" id="A6.T4.6.6.6.6.6.m1.1c">\text{CLIP}_{\text{out}}\uparrow</annotation><annotation encoding="application/x-llamapun" id="A6.T4.6.6.6.6.6.m1.1d">CLIP start_POSTSUBSCRIPT out end_POSTSUBSCRIPT ↑</annotation></semantics></math></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.7.7.7.7.7"><math alttext="\text{CLIP}_{\text{dir}}\uparrow" class="ltx_Math" display="inline" id="A6.T4.7.7.7.7.7.m1.1"><semantics id="A6.T4.7.7.7.7.7.m1.1a"><mrow id="A6.T4.7.7.7.7.7.m1.1.1" xref="A6.T4.7.7.7.7.7.m1.1.1.cmml"><msub id="A6.T4.7.7.7.7.7.m1.1.1.2" xref="A6.T4.7.7.7.7.7.m1.1.1.2.cmml"><mtext id="A6.T4.7.7.7.7.7.m1.1.1.2.2" xref="A6.T4.7.7.7.7.7.m1.1.1.2.2a.cmml">CLIP</mtext><mtext id="A6.T4.7.7.7.7.7.m1.1.1.2.3" xref="A6.T4.7.7.7.7.7.m1.1.1.2.3a.cmml">dir</mtext></msub><mo id="A6.T4.7.7.7.7.7.m1.1.1.1" stretchy="false" xref="A6.T4.7.7.7.7.7.m1.1.1.1.cmml">↑</mo><mi id="A6.T4.7.7.7.7.7.m1.1.1.3" xref="A6.T4.7.7.7.7.7.m1.1.1.3.cmml"></mi></mrow><annotation-xml encoding="MathML-Content" id="A6.T4.7.7.7.7.7.m1.1b"><apply id="A6.T4.7.7.7.7.7.m1.1.1.cmml" xref="A6.T4.7.7.7.7.7.m1.1.1"><ci id="A6.T4.7.7.7.7.7.m1.1.1.1.cmml" xref="A6.T4.7.7.7.7.7.m1.1.1.1">↑</ci><apply id="A6.T4.7.7.7.7.7.m1.1.1.2.cmml" xref="A6.T4.7.7.7.7.7.m1.1.1.2"><csymbol cd="ambiguous" id="A6.T4.7.7.7.7.7.m1.1.1.2.1.cmml" xref="A6.T4.7.7.7.7.7.m1.1.1.2">subscript</csymbol><ci id="A6.T4.7.7.7.7.7.m1.1.1.2.2a.cmml" xref="A6.T4.7.7.7.7.7.m1.1.1.2.2"><mtext id="A6.T4.7.7.7.7.7.m1.1.1.2.2.cmml" xref="A6.T4.7.7.7.7.7.m1.1.1.2.2">CLIP</mtext></ci><ci id="A6.T4.7.7.7.7.7.m1.1.1.2.3a.cmml" xref="A6.T4.7.7.7.7.7.m1.1.1.2.3"><mtext id="A6.T4.7.7.7.7.7.m1.1.1.2.3.cmml" mathsize="70%" xref="A6.T4.7.7.7.7.7.m1.1.1.2.3">dir</mtext></ci></apply><csymbol cd="latexml" id="A6.T4.7.7.7.7.7.m1.1.1.3.cmml" xref="A6.T4.7.7.7.7.7.m1.1.1.3">absent</csymbol></apply></annotation-xml><annotation encoding="application/x-tex" id="A6.T4.7.7.7.7.7.m1.1c">\text{CLIP}_{\text{dir}}\uparrow</annotation><annotation encoding="application/x-llamapun" id="A6.T4.7.7.7.7.7.m1.1d">CLIP start_POSTSUBSCRIPT dir end_POSTSUBSCRIPT ↑</annotation></semantics></math></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.8.8.8.8.8"><math alttext="\text{CLIP}_{\text{img}}\uparrow" class="ltx_Math" display="inline" id="A6.T4.8.8.8.8.8.m1.1"><semantics id="A6.T4.8.8.8.8.8.m1.1a"><mrow id="A6.T4.8.8.8.8.8.m1.1.1" xref="A6.T4.8.8.8.8.8.m1.1.1.cmml"><msub id="A6.T4.8.8.8.8.8.m1.1.1.2" xref="A6.T4.8.8.8.8.8.m1.1.1.2.cmml"><mtext id="A6.T4.8.8.8.8.8.m1.1.1.2.2" xref="A6.T4.8.8.8.8.8.m1.1.1.2.2a.cmml">CLIP</mtext><mtext id="A6.T4.8.8.8.8.8.m1.1.1.2.3" xref="A6.T4.8.8.8.8.8.m1.1.1.2.3a.cmml">img</mtext></msub><mo id="A6.T4.8.8.8.8.8.m1.1.1.1" stretchy="false" xref="A6.T4.8.8.8.8.8.m1.1.1.1.cmml">↑</mo><mi id="A6.T4.8.8.8.8.8.m1.1.1.3" xref="A6.T4.8.8.8.8.8.m1.1.1.3.cmml"></mi></mrow><annotation-xml encoding="MathML-Content" id="A6.T4.8.8.8.8.8.m1.1b"><apply id="A6.T4.8.8.8.8.8.m1.1.1.cmml" xref="A6.T4.8.8.8.8.8.m1.1.1"><ci id="A6.T4.8.8.8.8.8.m1.1.1.1.cmml" xref="A6.T4.8.8.8.8.8.m1.1.1.1">↑</ci><apply id="A6.T4.8.8.8.8.8.m1.1.1.2.cmml" xref="A6.T4.8.8.8.8.8.m1.1.1.2"><csymbol cd="ambiguous" id="A6.T4.8.8.8.8.8.m1.1.1.2.1.cmml" xref="A6.T4.8.8.8.8.8.m1.1.1.2">subscript</csymbol><ci id="A6.T4.8.8.8.8.8.m1.1.1.2.2a.cmml" xref="A6.T4.8.8.8.8.8.m1.1.1.2.2"><mtext id="A6.T4.8.8.8.8.8.m1.1.1.2.2.cmml" xref="A6.T4.8.8.8.8.8.m1.1.1.2.2">CLIP</mtext></ci><ci id="A6.T4.8.8.8.8.8.m1.1.1.2.3a.cmml" xref="A6.T4.8.8.8.8.8.m1.1.1.2.3"><mtext id="A6.T4.8.8.8.8.8.m1.1.1.2.3.cmml" mathsize="70%" xref="A6.T4.8.8.8.8.8.m1.1.1.2.3">img</mtext></ci></apply><csymbol cd="latexml" id="A6.T4.8.8.8.8.8.m1.1.1.3.cmml" xref="A6.T4.8.8.8.8.8.m1.1.1.3">absent</csymbol></apply></annotation-xml><annotation encoding="application/x-tex" id="A6.T4.8.8.8.8.8.m1.1c">\text{CLIP}_{\text{img}}\uparrow</annotation><annotation encoding="application/x-llamapun" id="A6.T4.8.8.8.8.8.m1.1d">CLIP start_POSTSUBSCRIPT img end_POSTSUBSCRIPT ↑</annotation></semantics></math></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.9.9.9.9.9"><math alttext="\text{CLIP}_{\text{out}}\uparrow" class="ltx_Math" display="inline" id="A6.T4.9.9.9.9.9.m1.1"><semantics id="A6.T4.9.9.9.9.9.m1.1a"><mrow id="A6.T4.9.9.9.9.9.m1.1.1" xref="A6.T4.9.9.9.9.9.m1.1.1.cmml"><msub id="A6.T4.9.9.9.9.9.m1.1.1.2" xref="A6.T4.9.9.9.9.9.m1.1.1.2.cmml"><mtext id="A6.T4.9.9.9.9.9.m1.1.1.2.2" xref="A6.T4.9.9.9.9.9.m1.1.1.2.2a.cmml">CLIP</mtext><mtext id="A6.T4.9.9.9.9.9.m1.1.1.2.3" xref="A6.T4.9.9.9.9.9.m1.1.1.2.3a.cmml">out</mtext></msub><mo id="A6.T4.9.9.9.9.9.m1.1.1.1" stretchy="false" xref="A6.T4.9.9.9.9.9.m1.1.1.1.cmml">↑</mo><mi id="A6.T4.9.9.9.9.9.m1.1.1.3" xref="A6.T4.9.9.9.9.9.m1.1.1.3.cmml"></mi></mrow><annotation-xml encoding="MathML-Content" id="A6.T4.9.9.9.9.9.m1.1b"><apply id="A6.T4.9.9.9.9.9.m1.1.1.cmml" xref="A6.T4.9.9.9.9.9.m1.1.1"><ci id="A6.T4.9.9.9.9.9.m1.1.1.1.cmml" xref="A6.T4.9.9.9.9.9.m1.1.1.1">↑</ci><apply id="A6.T4.9.9.9.9.9.m1.1.1.2.cmml" xref="A6.T4.9.9.9.9.9.m1.1.1.2"><csymbol cd="ambiguous" id="A6.T4.9.9.9.9.9.m1.1.1.2.1.cmml" xref="A6.T4.9.9.9.9.9.m1.1.1.2">subscript</csymbol><ci id="A6.T4.9.9.9.9.9.m1.1.1.2.2a.cmml" xref="A6.T4.9.9.9.9.9.m1.1.1.2.2"><mtext id="A6.T4.9.9.9.9.9.m1.1.1.2.2.cmml" xref="A6.T4.9.9.9.9.9.m1.1.1.2.2">CLIP</mtext></ci><ci id="A6.T4.9.9.9.9.9.m1.1.1.2.3a.cmml" xref="A6.T4.9.9.9.9.9.m1.1.1.2.3"><mtext id="A6.T4.9.9.9.9.9.m1.1.1.2.3.cmml" mathsize="70%" xref="A6.T4.9.9.9.9.9.m1.1.1.2.3">out</mtext></ci></apply><csymbol cd="latexml" id="A6.T4.9.9.9.9.9.m1.1.1.3.cmml" xref="A6.T4.9.9.9.9.9.m1.1.1.3">absent</csymbol></apply></annotation-xml><annotation encoding="application/x-tex" id="A6.T4.9.9.9.9.9.m1.1c">\text{CLIP}_{\text{out}}\uparrow</annotation><annotation encoding="application/x-llamapun" id="A6.T4.9.9.9.9.9.m1.1d">CLIP start_POSTSUBSCRIPT out end_POSTSUBSCRIPT ↑</annotation></semantics></math></td>
</tr>
<tr class="ltx_tr" id="A6.T4.9.9.9.11">
<td class="ltx_td ltx_align_left ltx_border_t" id="A6.T4.9.9.9.11.1">Unwatermarked Image</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.9.9.9.11.2">0.2693</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.9.9.9.11.3">0.7283</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.9.9.9.11.4">0.2732</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.9.9.9.11.5">0.3230</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.9.9.9.11.6">0.7268</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.9.9.9.11.7">0.3008</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.9.9.9.11.8">0.3025</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.9.9.9.11.9">0.7913</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.9.9.9.11.10">0.2930</td>
</tr>
<tr class="ltx_tr" id="A6.T4.9.9.9.12">
<td class="ltx_td ltx_align_left ltx_border_t" id="A6.T4.9.9.9.12.1">MBRS <cite class="ltx_cite ltx_citemacro_citep">(Jia et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib28" title="">2021</a>)</cite>
</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.9.9.9.12.2">0.2494</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.9.9.9.12.3">0.7385</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.9.9.9.12.4">0.2733</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.9.9.9.12.5">0.2919</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.9.9.9.12.6">0.6654</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.9.9.9.12.7">0.2891</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.9.9.9.12.8">0.2857</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.9.9.9.12.9">0.7816</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T4.9.9.9.12.10">0.2929</td>
</tr>
<tr class="ltx_tr" id="A6.T4.9.9.9.13">
<td class="ltx_td ltx_align_left" id="A6.T4.9.9.9.13.1">CIN <cite class="ltx_cite ltx_citemacro_citep">(Ma et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib44" title="">2022</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.13.2">0.2625</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.13.3">0.7232</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.13.4">0.2729</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.13.5">0.3152</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.13.6">0.7111</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.13.7">0.3010</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.13.8">0.2949</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.13.9">0.7841</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.13.10">0.2928</td>
</tr>
<tr class="ltx_tr" id="A6.T4.9.9.9.14">
<td class="ltx_td ltx_align_left" id="A6.T4.9.9.9.14.1">PIMoG <cite class="ltx_cite ltx_citemacro_citep">(Fang et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib18" title="">2022</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.14.2">0.2518</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.14.3">0.7021</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.14.4">0.2746</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.14.5">0.3010</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.14.6">0.6940</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.14.7">0.3024</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.14.8">0.2815</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.14.9">0.7662</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.14.10">0.2962</td>
</tr>
<tr class="ltx_tr" id="A6.T4.9.9.9.15">
<td class="ltx_td ltx_align_left" id="A6.T4.9.9.9.15.1">RivaGAN <cite class="ltx_cite ltx_citemacro_citep">(Zhang et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib86" title="">2019</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.15.2">0.2647</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.15.3">0.7317</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.15.4">0.2721</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.15.5">0.3168</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.15.6">0.7133</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.15.7">0.3003</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.15.8">0.3020</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.15.9">0.7948</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.15.10">0.2930</td>
</tr>
<tr class="ltx_tr" id="A6.T4.9.9.9.16">
<td class="ltx_td ltx_align_left" id="A6.T4.9.9.9.16.1">SepMark <cite class="ltx_cite ltx_citemacro_citep">(Wu et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib75" title="">2023</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.16.2">0.2659</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.16.3">0.7292</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.16.4">0.2743</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.16.5">0.3145</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.16.6">0.7181</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.16.7">0.3002</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.16.8">0.2975</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.16.9">0.7891</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.16.10">0.2936</td>
</tr>
<tr class="ltx_tr" id="A6.T4.9.9.9.17">
<td class="ltx_td ltx_align_left" id="A6.T4.9.9.9.17.1">DWTDCT <cite class="ltx_cite ltx_citemacro_citep">(Al-Haj, <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib1" title="">2007</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.17.2">0.2644</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.17.3">0.7317</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.17.4">0.2734</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.17.5">0.3189</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.17.6">0.7250</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.17.7">0.3009</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.17.8">0.2959</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.17.9">0.7942</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.17.10">0.2934</td>
</tr>
<tr class="ltx_tr" id="A6.T4.9.9.9.18">
<td class="ltx_td ltx_align_left" id="A6.T4.9.9.9.18.1">DWTDCTSVD <cite class="ltx_cite ltx_citemacro_citep">(Navas et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib50" title="">2008</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.18.2">0.2581</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.18.3">0.7220</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.18.4">0.2751</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.18.5">0.3115</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.18.6">0.7118</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.18.7">0.3004</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.18.8">0.2869</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.18.9">0.7793</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.18.10">0.2939</td>
</tr>
<tr class="ltx_tr" id="A6.T4.9.9.9.19">
<td class="ltx_td ltx_align_left" id="A6.T4.9.9.9.19.1">SSL <cite class="ltx_cite ltx_citemacro_citep">(Fernandez et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib20" title="">2022</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.19.2">0.2583</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.19.3">0.7218</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.19.4">0.2752</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.19.5">0.3093</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.19.6">0.7065</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.19.7">0.3019</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.19.8">0.2896</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.19.9">0.7780</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.19.10">0.2944</td>
</tr>
<tr class="ltx_tr" id="A6.T4.9.9.9.20">
<td class="ltx_td ltx_align_left" id="A6.T4.9.9.9.20.1">StegaStamp <cite class="ltx_cite ltx_citemacro_citep">(Tancik et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib69" title="">2020</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.20.2">0.2436</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.20.3">0.6826</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.20.4">0.2697</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.20.5">0.2904</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.20.6">0.6886</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.20.7">0.3007</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.20.8">0.2663</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.20.9">0.7512</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.20.10">0.2944</td>
</tr>
<tr class="ltx_tr" id="A6.T4.9.9.9.21">
<td class="ltx_td ltx_align_left" id="A6.T4.9.9.9.21.1">TrustMark <cite class="ltx_cite ltx_citemacro_citep">(Bui et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib8" title="">2023</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.21.2">0.2634</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.21.3">0.7181</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.21.4">0.2729</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.21.5">0.3172</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.21.6">0.7146</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.21.7">0.2994</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.21.8">0.2943</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.21.9">0.7853</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.21.10">0.2936</td>
</tr>
<tr class="ltx_tr" id="A6.T4.9.9.9.22">
<td class="ltx_td ltx_align_left" id="A6.T4.9.9.9.22.1">EditGuard <cite class="ltx_cite ltx_citemacro_citep">(Zhang et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib90" title="">2024d</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.22.2">0.2722</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.22.3">0.7045</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.22.4">0.2722</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.22.5">0.3155</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.22.6">0.7170</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.22.7">0.3021</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.22.8">0.2882</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.22.9">0.7708</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.22.10">0.2940</td>
</tr>
<tr class="ltx_tr" id="A6.T4.9.9.9.23">
<td class="ltx_td ltx_align_left" id="A6.T4.9.9.9.23.1">VINE-Base</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.23.2">0.2743</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.23.3">0.7260</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.23.4">0.2743</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.23.5">0.3186</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.23.6">0.7189</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.23.7">0.2996</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.23.8">0.2977</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.23.9">0.7889</td>
<td class="ltx_td ltx_align_center" id="A6.T4.9.9.9.23.10">0.2931</td>
</tr>
<tr class="ltx_tr" id="A6.T4.9.9.9.24">
<td class="ltx_td ltx_align_left ltx_border_bb" id="A6.T4.9.9.9.24.1">VINE-Robust</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A6.T4.9.9.9.24.2">0.2624</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A6.T4.9.9.9.24.3">0.7248</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A6.T4.9.9.9.24.4">0.2715</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A6.T4.9.9.9.24.5">0.3176</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A6.T4.9.9.9.24.6">0.7183</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A6.T4.9.9.9.24.7">0.3001</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A6.T4.9.9.9.24.8">0.2981</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A6.T4.9.9.9.24.9">0.7953</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A6.T4.9.9.9.24.10">0.2940</td>
</tr>
</table>{{< /table-caption >}}
> 🔼 This table presents a comparative analysis of the editing quality achieved by various global image editing methods (Instruct-Pix2Pix, UltraEdit, and MagicBrush).  The impact of different watermarking techniques on the effectiveness of these editing methods is also evaluated.  For each editing method, the table displays the quality metrics CLIPdir (alignment of edits with prompts), CLIPimg (content preservation), and CLIPout (alignment of edited image to target caption). A control condition using an unwatermarked image is included for comparison.  The analysis is conducted using a consistent image guidance scale of 1.5 and a text guidance scale of 7 for all watermarking and editing methods.
> <details>
> <summary>read the caption</summary>
> Table 4: Comparison of editing quality for different global editing methods and the effect of different watermarks on image editing outcomes. All models use an image guidance scale of 1.5 and a text guidance scale of 7.
> </details>

{{< table-caption >}}
<table class="ltx_tabular ltx_align_middle" id="A6.T5.6.6.6">
<tr class="ltx_tr" id="A6.T5.6.6.6.7">
<td class="ltx_td ltx_align_left ltx_border_tt" id="A6.T5.6.6.6.7.1" rowspan="2"><span class="ltx_text" id="A6.T5.6.6.6.7.1.1">Method</span></td>
<td class="ltx_td ltx_align_center ltx_border_tt" colspan="3" id="A6.T5.6.6.6.7.2">ControlNet-Inpainting</td>
<td class="ltx_td ltx_align_center ltx_border_tt" colspan="3" id="A6.T5.6.6.6.7.3">UltraEdit</td>
</tr>
<tr class="ltx_tr" id="A6.T5.6.6.6.6">
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T5.1.1.1.1.1"><math alttext="\text{CLIP}_{\text{dir}}\uparrow" class="ltx_Math" display="inline" id="A6.T5.1.1.1.1.1.m1.1"><semantics id="A6.T5.1.1.1.1.1.m1.1a"><mrow id="A6.T5.1.1.1.1.1.m1.1.1" xref="A6.T5.1.1.1.1.1.m1.1.1.cmml"><msub id="A6.T5.1.1.1.1.1.m1.1.1.2" xref="A6.T5.1.1.1.1.1.m1.1.1.2.cmml"><mtext id="A6.T5.1.1.1.1.1.m1.1.1.2.2" xref="A6.T5.1.1.1.1.1.m1.1.1.2.2a.cmml">CLIP</mtext><mtext id="A6.T5.1.1.1.1.1.m1.1.1.2.3" xref="A6.T5.1.1.1.1.1.m1.1.1.2.3a.cmml">dir</mtext></msub><mo id="A6.T5.1.1.1.1.1.m1.1.1.1" stretchy="false" xref="A6.T5.1.1.1.1.1.m1.1.1.1.cmml">↑</mo><mi id="A6.T5.1.1.1.1.1.m1.1.1.3" xref="A6.T5.1.1.1.1.1.m1.1.1.3.cmml"></mi></mrow><annotation-xml encoding="MathML-Content" id="A6.T5.1.1.1.1.1.m1.1b"><apply id="A6.T5.1.1.1.1.1.m1.1.1.cmml" xref="A6.T5.1.1.1.1.1.m1.1.1"><ci id="A6.T5.1.1.1.1.1.m1.1.1.1.cmml" xref="A6.T5.1.1.1.1.1.m1.1.1.1">↑</ci><apply id="A6.T5.1.1.1.1.1.m1.1.1.2.cmml" xref="A6.T5.1.1.1.1.1.m1.1.1.2"><csymbol cd="ambiguous" id="A6.T5.1.1.1.1.1.m1.1.1.2.1.cmml" xref="A6.T5.1.1.1.1.1.m1.1.1.2">subscript</csymbol><ci id="A6.T5.1.1.1.1.1.m1.1.1.2.2a.cmml" xref="A6.T5.1.1.1.1.1.m1.1.1.2.2"><mtext id="A6.T5.1.1.1.1.1.m1.1.1.2.2.cmml" xref="A6.T5.1.1.1.1.1.m1.1.1.2.2">CLIP</mtext></ci><ci id="A6.T5.1.1.1.1.1.m1.1.1.2.3a.cmml" xref="A6.T5.1.1.1.1.1.m1.1.1.2.3"><mtext id="A6.T5.1.1.1.1.1.m1.1.1.2.3.cmml" mathsize="70%" xref="A6.T5.1.1.1.1.1.m1.1.1.2.3">dir</mtext></ci></apply><csymbol cd="latexml" id="A6.T5.1.1.1.1.1.m1.1.1.3.cmml" xref="A6.T5.1.1.1.1.1.m1.1.1.3">absent</csymbol></apply></annotation-xml><annotation encoding="application/x-tex" id="A6.T5.1.1.1.1.1.m1.1c">\text{CLIP}_{\text{dir}}\uparrow</annotation><annotation encoding="application/x-llamapun" id="A6.T5.1.1.1.1.1.m1.1d">CLIP start_POSTSUBSCRIPT dir end_POSTSUBSCRIPT ↑</annotation></semantics></math></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T5.2.2.2.2.2"><math alttext="\text{CLIP}_{\text{img}}\uparrow" class="ltx_Math" display="inline" id="A6.T5.2.2.2.2.2.m1.1"><semantics id="A6.T5.2.2.2.2.2.m1.1a"><mrow id="A6.T5.2.2.2.2.2.m1.1.1" xref="A6.T5.2.2.2.2.2.m1.1.1.cmml"><msub id="A6.T5.2.2.2.2.2.m1.1.1.2" xref="A6.T5.2.2.2.2.2.m1.1.1.2.cmml"><mtext id="A6.T5.2.2.2.2.2.m1.1.1.2.2" xref="A6.T5.2.2.2.2.2.m1.1.1.2.2a.cmml">CLIP</mtext><mtext id="A6.T5.2.2.2.2.2.m1.1.1.2.3" xref="A6.T5.2.2.2.2.2.m1.1.1.2.3a.cmml">img</mtext></msub><mo id="A6.T5.2.2.2.2.2.m1.1.1.1" stretchy="false" xref="A6.T5.2.2.2.2.2.m1.1.1.1.cmml">↑</mo><mi id="A6.T5.2.2.2.2.2.m1.1.1.3" xref="A6.T5.2.2.2.2.2.m1.1.1.3.cmml"></mi></mrow><annotation-xml encoding="MathML-Content" id="A6.T5.2.2.2.2.2.m1.1b"><apply id="A6.T5.2.2.2.2.2.m1.1.1.cmml" xref="A6.T5.2.2.2.2.2.m1.1.1"><ci id="A6.T5.2.2.2.2.2.m1.1.1.1.cmml" xref="A6.T5.2.2.2.2.2.m1.1.1.1">↑</ci><apply id="A6.T5.2.2.2.2.2.m1.1.1.2.cmml" xref="A6.T5.2.2.2.2.2.m1.1.1.2"><csymbol cd="ambiguous" id="A6.T5.2.2.2.2.2.m1.1.1.2.1.cmml" xref="A6.T5.2.2.2.2.2.m1.1.1.2">subscript</csymbol><ci id="A6.T5.2.2.2.2.2.m1.1.1.2.2a.cmml" xref="A6.T5.2.2.2.2.2.m1.1.1.2.2"><mtext id="A6.T5.2.2.2.2.2.m1.1.1.2.2.cmml" xref="A6.T5.2.2.2.2.2.m1.1.1.2.2">CLIP</mtext></ci><ci id="A6.T5.2.2.2.2.2.m1.1.1.2.3a.cmml" xref="A6.T5.2.2.2.2.2.m1.1.1.2.3"><mtext id="A6.T5.2.2.2.2.2.m1.1.1.2.3.cmml" mathsize="70%" xref="A6.T5.2.2.2.2.2.m1.1.1.2.3">img</mtext></ci></apply><csymbol cd="latexml" id="A6.T5.2.2.2.2.2.m1.1.1.3.cmml" xref="A6.T5.2.2.2.2.2.m1.1.1.3">absent</csymbol></apply></annotation-xml><annotation encoding="application/x-tex" id="A6.T5.2.2.2.2.2.m1.1c">\text{CLIP}_{\text{img}}\uparrow</annotation><annotation encoding="application/x-llamapun" id="A6.T5.2.2.2.2.2.m1.1d">CLIP start_POSTSUBSCRIPT img end_POSTSUBSCRIPT ↑</annotation></semantics></math></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T5.3.3.3.3.3"><math alttext="\text{CLIP}_{\text{out}}\uparrow" class="ltx_Math" display="inline" id="A6.T5.3.3.3.3.3.m1.1"><semantics id="A6.T5.3.3.3.3.3.m1.1a"><mrow id="A6.T5.3.3.3.3.3.m1.1.1" xref="A6.T5.3.3.3.3.3.m1.1.1.cmml"><msub id="A6.T5.3.3.3.3.3.m1.1.1.2" xref="A6.T5.3.3.3.3.3.m1.1.1.2.cmml"><mtext id="A6.T5.3.3.3.3.3.m1.1.1.2.2" xref="A6.T5.3.3.3.3.3.m1.1.1.2.2a.cmml">CLIP</mtext><mtext id="A6.T5.3.3.3.3.3.m1.1.1.2.3" xref="A6.T5.3.3.3.3.3.m1.1.1.2.3a.cmml">out</mtext></msub><mo id="A6.T5.3.3.3.3.3.m1.1.1.1" stretchy="false" xref="A6.T5.3.3.3.3.3.m1.1.1.1.cmml">↑</mo><mi id="A6.T5.3.3.3.3.3.m1.1.1.3" xref="A6.T5.3.3.3.3.3.m1.1.1.3.cmml"></mi></mrow><annotation-xml encoding="MathML-Content" id="A6.T5.3.3.3.3.3.m1.1b"><apply id="A6.T5.3.3.3.3.3.m1.1.1.cmml" xref="A6.T5.3.3.3.3.3.m1.1.1"><ci id="A6.T5.3.3.3.3.3.m1.1.1.1.cmml" xref="A6.T5.3.3.3.3.3.m1.1.1.1">↑</ci><apply id="A6.T5.3.3.3.3.3.m1.1.1.2.cmml" xref="A6.T5.3.3.3.3.3.m1.1.1.2"><csymbol cd="ambiguous" id="A6.T5.3.3.3.3.3.m1.1.1.2.1.cmml" xref="A6.T5.3.3.3.3.3.m1.1.1.2">subscript</csymbol><ci id="A6.T5.3.3.3.3.3.m1.1.1.2.2a.cmml" xref="A6.T5.3.3.3.3.3.m1.1.1.2.2"><mtext id="A6.T5.3.3.3.3.3.m1.1.1.2.2.cmml" xref="A6.T5.3.3.3.3.3.m1.1.1.2.2">CLIP</mtext></ci><ci id="A6.T5.3.3.3.3.3.m1.1.1.2.3a.cmml" xref="A6.T5.3.3.3.3.3.m1.1.1.2.3"><mtext id="A6.T5.3.3.3.3.3.m1.1.1.2.3.cmml" mathsize="70%" xref="A6.T5.3.3.3.3.3.m1.1.1.2.3">out</mtext></ci></apply><csymbol cd="latexml" id="A6.T5.3.3.3.3.3.m1.1.1.3.cmml" xref="A6.T5.3.3.3.3.3.m1.1.1.3">absent</csymbol></apply></annotation-xml><annotation encoding="application/x-tex" id="A6.T5.3.3.3.3.3.m1.1c">\text{CLIP}_{\text{out}}\uparrow</annotation><annotation encoding="application/x-llamapun" id="A6.T5.3.3.3.3.3.m1.1d">CLIP start_POSTSUBSCRIPT out end_POSTSUBSCRIPT ↑</annotation></semantics></math></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T5.4.4.4.4.4"><math alttext="\text{CLIP}_{\text{dir}}\uparrow" class="ltx_Math" display="inline" id="A6.T5.4.4.4.4.4.m1.1"><semantics id="A6.T5.4.4.4.4.4.m1.1a"><mrow id="A6.T5.4.4.4.4.4.m1.1.1" xref="A6.T5.4.4.4.4.4.m1.1.1.cmml"><msub id="A6.T5.4.4.4.4.4.m1.1.1.2" xref="A6.T5.4.4.4.4.4.m1.1.1.2.cmml"><mtext id="A6.T5.4.4.4.4.4.m1.1.1.2.2" xref="A6.T5.4.4.4.4.4.m1.1.1.2.2a.cmml">CLIP</mtext><mtext id="A6.T5.4.4.4.4.4.m1.1.1.2.3" xref="A6.T5.4.4.4.4.4.m1.1.1.2.3a.cmml">dir</mtext></msub><mo id="A6.T5.4.4.4.4.4.m1.1.1.1" stretchy="false" xref="A6.T5.4.4.4.4.4.m1.1.1.1.cmml">↑</mo><mi id="A6.T5.4.4.4.4.4.m1.1.1.3" xref="A6.T5.4.4.4.4.4.m1.1.1.3.cmml"></mi></mrow><annotation-xml encoding="MathML-Content" id="A6.T5.4.4.4.4.4.m1.1b"><apply id="A6.T5.4.4.4.4.4.m1.1.1.cmml" xref="A6.T5.4.4.4.4.4.m1.1.1"><ci id="A6.T5.4.4.4.4.4.m1.1.1.1.cmml" xref="A6.T5.4.4.4.4.4.m1.1.1.1">↑</ci><apply id="A6.T5.4.4.4.4.4.m1.1.1.2.cmml" xref="A6.T5.4.4.4.4.4.m1.1.1.2"><csymbol cd="ambiguous" id="A6.T5.4.4.4.4.4.m1.1.1.2.1.cmml" xref="A6.T5.4.4.4.4.4.m1.1.1.2">subscript</csymbol><ci id="A6.T5.4.4.4.4.4.m1.1.1.2.2a.cmml" xref="A6.T5.4.4.4.4.4.m1.1.1.2.2"><mtext id="A6.T5.4.4.4.4.4.m1.1.1.2.2.cmml" xref="A6.T5.4.4.4.4.4.m1.1.1.2.2">CLIP</mtext></ci><ci id="A6.T5.4.4.4.4.4.m1.1.1.2.3a.cmml" xref="A6.T5.4.4.4.4.4.m1.1.1.2.3"><mtext id="A6.T5.4.4.4.4.4.m1.1.1.2.3.cmml" mathsize="70%" xref="A6.T5.4.4.4.4.4.m1.1.1.2.3">dir</mtext></ci></apply><csymbol cd="latexml" id="A6.T5.4.4.4.4.4.m1.1.1.3.cmml" xref="A6.T5.4.4.4.4.4.m1.1.1.3">absent</csymbol></apply></annotation-xml><annotation encoding="application/x-tex" id="A6.T5.4.4.4.4.4.m1.1c">\text{CLIP}_{\text{dir}}\uparrow</annotation><annotation encoding="application/x-llamapun" id="A6.T5.4.4.4.4.4.m1.1d">CLIP start_POSTSUBSCRIPT dir end_POSTSUBSCRIPT ↑</annotation></semantics></math></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T5.5.5.5.5.5"><math alttext="\text{CLIP}_{\text{img}}\uparrow" class="ltx_Math" display="inline" id="A6.T5.5.5.5.5.5.m1.1"><semantics id="A6.T5.5.5.5.5.5.m1.1a"><mrow id="A6.T5.5.5.5.5.5.m1.1.1" xref="A6.T5.5.5.5.5.5.m1.1.1.cmml"><msub id="A6.T5.5.5.5.5.5.m1.1.1.2" xref="A6.T5.5.5.5.5.5.m1.1.1.2.cmml"><mtext id="A6.T5.5.5.5.5.5.m1.1.1.2.2" xref="A6.T5.5.5.5.5.5.m1.1.1.2.2a.cmml">CLIP</mtext><mtext id="A6.T5.5.5.5.5.5.m1.1.1.2.3" xref="A6.T5.5.5.5.5.5.m1.1.1.2.3a.cmml">img</mtext></msub><mo id="A6.T5.5.5.5.5.5.m1.1.1.1" stretchy="false" xref="A6.T5.5.5.5.5.5.m1.1.1.1.cmml">↑</mo><mi id="A6.T5.5.5.5.5.5.m1.1.1.3" xref="A6.T5.5.5.5.5.5.m1.1.1.3.cmml"></mi></mrow><annotation-xml encoding="MathML-Content" id="A6.T5.5.5.5.5.5.m1.1b"><apply id="A6.T5.5.5.5.5.5.m1.1.1.cmml" xref="A6.T5.5.5.5.5.5.m1.1.1"><ci id="A6.T5.5.5.5.5.5.m1.1.1.1.cmml" xref="A6.T5.5.5.5.5.5.m1.1.1.1">↑</ci><apply id="A6.T5.5.5.5.5.5.m1.1.1.2.cmml" xref="A6.T5.5.5.5.5.5.m1.1.1.2"><csymbol cd="ambiguous" id="A6.T5.5.5.5.5.5.m1.1.1.2.1.cmml" xref="A6.T5.5.5.5.5.5.m1.1.1.2">subscript</csymbol><ci id="A6.T5.5.5.5.5.5.m1.1.1.2.2a.cmml" xref="A6.T5.5.5.5.5.5.m1.1.1.2.2"><mtext id="A6.T5.5.5.5.5.5.m1.1.1.2.2.cmml" xref="A6.T5.5.5.5.5.5.m1.1.1.2.2">CLIP</mtext></ci><ci id="A6.T5.5.5.5.5.5.m1.1.1.2.3a.cmml" xref="A6.T5.5.5.5.5.5.m1.1.1.2.3"><mtext id="A6.T5.5.5.5.5.5.m1.1.1.2.3.cmml" mathsize="70%" xref="A6.T5.5.5.5.5.5.m1.1.1.2.3">img</mtext></ci></apply><csymbol cd="latexml" id="A6.T5.5.5.5.5.5.m1.1.1.3.cmml" xref="A6.T5.5.5.5.5.5.m1.1.1.3">absent</csymbol></apply></annotation-xml><annotation encoding="application/x-tex" id="A6.T5.5.5.5.5.5.m1.1c">\text{CLIP}_{\text{img}}\uparrow</annotation><annotation encoding="application/x-llamapun" id="A6.T5.5.5.5.5.5.m1.1d">CLIP start_POSTSUBSCRIPT img end_POSTSUBSCRIPT ↑</annotation></semantics></math></td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T5.6.6.6.6.6"><math alttext="\text{CLIP}_{\text{out}}\uparrow" class="ltx_Math" display="inline" id="A6.T5.6.6.6.6.6.m1.1"><semantics id="A6.T5.6.6.6.6.6.m1.1a"><mrow id="A6.T5.6.6.6.6.6.m1.1.1" xref="A6.T5.6.6.6.6.6.m1.1.1.cmml"><msub id="A6.T5.6.6.6.6.6.m1.1.1.2" xref="A6.T5.6.6.6.6.6.m1.1.1.2.cmml"><mtext id="A6.T5.6.6.6.6.6.m1.1.1.2.2" xref="A6.T5.6.6.6.6.6.m1.1.1.2.2a.cmml">CLIP</mtext><mtext id="A6.T5.6.6.6.6.6.m1.1.1.2.3" xref="A6.T5.6.6.6.6.6.m1.1.1.2.3a.cmml">out</mtext></msub><mo id="A6.T5.6.6.6.6.6.m1.1.1.1" stretchy="false" xref="A6.T5.6.6.6.6.6.m1.1.1.1.cmml">↑</mo><mi id="A6.T5.6.6.6.6.6.m1.1.1.3" xref="A6.T5.6.6.6.6.6.m1.1.1.3.cmml"></mi></mrow><annotation-xml encoding="MathML-Content" id="A6.T5.6.6.6.6.6.m1.1b"><apply id="A6.T5.6.6.6.6.6.m1.1.1.cmml" xref="A6.T5.6.6.6.6.6.m1.1.1"><ci id="A6.T5.6.6.6.6.6.m1.1.1.1.cmml" xref="A6.T5.6.6.6.6.6.m1.1.1.1">↑</ci><apply id="A6.T5.6.6.6.6.6.m1.1.1.2.cmml" xref="A6.T5.6.6.6.6.6.m1.1.1.2"><csymbol cd="ambiguous" id="A6.T5.6.6.6.6.6.m1.1.1.2.1.cmml" xref="A6.T5.6.6.6.6.6.m1.1.1.2">subscript</csymbol><ci id="A6.T5.6.6.6.6.6.m1.1.1.2.2a.cmml" xref="A6.T5.6.6.6.6.6.m1.1.1.2.2"><mtext id="A6.T5.6.6.6.6.6.m1.1.1.2.2.cmml" xref="A6.T5.6.6.6.6.6.m1.1.1.2.2">CLIP</mtext></ci><ci id="A6.T5.6.6.6.6.6.m1.1.1.2.3a.cmml" xref="A6.T5.6.6.6.6.6.m1.1.1.2.3"><mtext id="A6.T5.6.6.6.6.6.m1.1.1.2.3.cmml" mathsize="70%" xref="A6.T5.6.6.6.6.6.m1.1.1.2.3">out</mtext></ci></apply><csymbol cd="latexml" id="A6.T5.6.6.6.6.6.m1.1.1.3.cmml" xref="A6.T5.6.6.6.6.6.m1.1.1.3">absent</csymbol></apply></annotation-xml><annotation encoding="application/x-tex" id="A6.T5.6.6.6.6.6.m1.1c">\text{CLIP}_{\text{out}}\uparrow</annotation><annotation encoding="application/x-llamapun" id="A6.T5.6.6.6.6.6.m1.1d">CLIP start_POSTSUBSCRIPT out end_POSTSUBSCRIPT ↑</annotation></semantics></math></td>
</tr>
<tr class="ltx_tr" id="A6.T5.6.6.6.8">
<td class="ltx_td ltx_align_left ltx_border_t" id="A6.T5.6.6.6.8.1">Unwatermarked Image</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T5.6.6.6.8.2">0.1983</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T5.6.6.6.8.3">0.7076</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T5.6.6.6.8.4">0.2589</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T5.6.6.6.8.5">0.2778</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T5.6.6.6.8.6">0.7519</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T5.6.6.6.8.7">0.2917</td>
</tr>
<tr class="ltx_tr" id="A6.T5.6.6.6.9">
<td class="ltx_td ltx_align_left ltx_border_t" id="A6.T5.6.6.6.9.1">MBRS <cite class="ltx_cite ltx_citemacro_citep">(Jia et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib28" title="">2021</a>)</cite>
</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T5.6.6.6.9.2">0.1846</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T5.6.6.6.9.3">0.7058</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T5.6.6.6.9.4">0.2588</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T5.6.6.6.9.5">0.2657</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T5.6.6.6.9.6">0.7175</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A6.T5.6.6.6.9.7">0.2913</td>
</tr>
<tr class="ltx_tr" id="A6.T5.6.6.6.10">
<td class="ltx_td ltx_align_left" id="A6.T5.6.6.6.10.1">CIN <cite class="ltx_cite ltx_citemacro_citep">(Ma et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib44" title="">2022</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.10.2">0.1966</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.10.3">0.7042</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.10.4">0.2613</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.10.5">0.2745</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.10.6">0.7389</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.10.7">0.2922</td>
</tr>
<tr class="ltx_tr" id="A6.T5.6.6.6.11">
<td class="ltx_td ltx_align_left" id="A6.T5.6.6.6.11.1">PIMoG <cite class="ltx_cite ltx_citemacro_citep">(Fang et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib18" title="">2022</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.11.2">0.1828</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.11.3">0.6909</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.11.4">0.2600</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.11.5">0.2578</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.11.6">0.7371</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.11.7">0.2920</td>
</tr>
<tr class="ltx_tr" id="A6.T5.6.6.6.12">
<td class="ltx_td ltx_align_left" id="A6.T5.6.6.6.12.1">RivaGAN <cite class="ltx_cite ltx_citemacro_citep">(Zhang et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib86" title="">2019</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.12.2">0.1975</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.12.3">0.7117</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.12.4">0.2612</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.12.5">0.2748</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.12.6">0.7469</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.12.7">0.2937</td>
</tr>
<tr class="ltx_tr" id="A6.T5.6.6.6.13">
<td class="ltx_td ltx_align_left" id="A6.T5.6.6.6.13.1">SepMark <cite class="ltx_cite ltx_citemacro_citep">(Wu et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib75" title="">2023</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.13.2">0.1932</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.13.3">0.7126</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.13.4">0.2582</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.13.5">0.2716</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.13.6">0.7588</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.13.7">0.2921</td>
</tr>
<tr class="ltx_tr" id="A6.T5.6.6.6.14">
<td class="ltx_td ltx_align_left" id="A6.T5.6.6.6.14.1">DWTDCT <cite class="ltx_cite ltx_citemacro_citep">(Al-Haj, <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib1" title="">2007</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.14.2">0.1982</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.14.3">0.7197</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.14.4">0.2602</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.14.5">0.2776</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.14.6">0.7558</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.14.7">0.2924</td>
</tr>
<tr class="ltx_tr" id="A6.T5.6.6.6.15">
<td class="ltx_td ltx_align_left" id="A6.T5.6.6.6.15.1">DWTDCTSVD <cite class="ltx_cite ltx_citemacro_citep">(Navas et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib50" title="">2008</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.15.2">0.1922</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.15.3">0.6995</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.15.4">0.2608</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.15.5">0.2705</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.15.6">0.7469</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.15.7">0.2940</td>
</tr>
<tr class="ltx_tr" id="A6.T5.6.6.6.16">
<td class="ltx_td ltx_align_left" id="A6.T5.6.6.6.16.1">SSL <cite class="ltx_cite ltx_citemacro_citep">(Fernandez et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib20" title="">2022</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.16.2">0.1911</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.16.3">0.6995</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.16.4">0.2604</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.16.5">0.2677</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.16.6">0.7380</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.16.7">0.2940</td>
</tr>
<tr class="ltx_tr" id="A6.T5.6.6.6.17">
<td class="ltx_td ltx_align_left" id="A6.T5.6.6.6.17.1">StegaStamp <cite class="ltx_cite ltx_citemacro_citep">(Tancik et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib69" title="">2020</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.17.2">0.1752</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.17.3">0.6684</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.17.4">0.2606</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.17.5">0.2439</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.17.6">0.7246</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.17.7">0.2919</td>
</tr>
<tr class="ltx_tr" id="A6.T5.6.6.6.18">
<td class="ltx_td ltx_align_left" id="A6.T5.6.6.6.18.1">TrustMark <cite class="ltx_cite ltx_citemacro_citep">(Bui et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib8" title="">2023</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.18.2">0.1959</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.18.3">0.7001</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.18.4">0.2594</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.18.5">0.2728</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.18.6">0.7451</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.18.7">0.2919</td>
</tr>
<tr class="ltx_tr" id="A6.T5.6.6.6.19">
<td class="ltx_td ltx_align_left" id="A6.T5.6.6.6.19.1">EditGuard <cite class="ltx_cite ltx_citemacro_citep">(Zhang et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib90" title="">2024d</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.19.2">0.1921</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.19.3">0.6944</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.19.4">0.2606</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.19.5">0.2696</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.19.6">0.7392</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.19.7">0.2923</td>
</tr>
<tr class="ltx_tr" id="A6.T5.6.6.6.20">
<td class="ltx_td ltx_align_left" id="A6.T5.6.6.6.20.1">VINE-Base</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.20.2">0.1953</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.20.3">0.7023</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.20.4">0.2591</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.20.5">0.2726</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.20.6">0.7494</td>
<td class="ltx_td ltx_align_center" id="A6.T5.6.6.6.20.7">0.2906</td>
</tr>
<tr class="ltx_tr" id="A6.T5.6.6.6.21">
<td class="ltx_td ltx_align_left ltx_border_bb" id="A6.T5.6.6.6.21.1">VINE-Robust</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A6.T5.6.6.6.21.2">0.1951</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A6.T5.6.6.6.21.3">0.7030</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A6.T5.6.6.6.21.4">0.2591</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A6.T5.6.6.6.21.5">0.2710</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A6.T5.6.6.6.21.6">0.7475</td>
<td class="ltx_td ltx_align_center ltx_border_bb" id="A6.T5.6.6.6.21.7">0.2909</td>
</tr>
</table>{{< /table-caption >}}
> 🔼 This table presents a quantitative analysis of the image editing quality using different watermarking methods.  Specifically, it evaluates local editing performance using ControlNet-Inpainting and UltraEdit, considering three metrics: CLIPdir (correspondence between edits and prompts), CLIPimg (content preservation), and CLIPout (alignment of edited image with target caption).  The results are shown for unwatermarked images and images watermarked with eleven different watermarking methods.  All editing models used a consistent image guidance scale of 1.5 and text guidance scale of 7.
> <details>
> <summary>read the caption</summary>
> Table 5: Comparison of editing quality for different local editing methods and the effect of different watermarks on image editing outcomes. All models use an image guidance scale of 1.5 and a text guidance scale of 7.
> </details>

{{< table-caption >}}
<table class="ltx_tabular ltx_align_middle" id="A7.T6.1.1">
<tr class="ltx_tr" id="A7.T6.1.1.1">
<td class="ltx_td ltx_align_left ltx_border_tt" id="A7.T6.1.1.1.1">Method</td>
<td class="ltx_td ltx_align_center ltx_border_tt" id="A7.T6.1.1.1.2">Running Time per Image (s)</td>
<td class="ltx_td ltx_align_center ltx_border_tt" id="A7.T6.1.1.1.3">GPU Memory Usage (MB)</td>
</tr>
<tr class="ltx_tr" id="A7.T6.1.1.2">
<td class="ltx_td ltx_align_left ltx_border_t" id="A7.T6.1.1.2.1">MBRS <cite class="ltx_cite ltx_citemacro_citep">(Jia et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib28" title="">2021</a>)</cite>
</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A7.T6.1.1.2.2">0.0053</td>
<td class="ltx_td ltx_align_center ltx_border_t" id="A7.T6.1.1.2.3">938</td>
</tr>
<tr class="ltx_tr" id="A7.T6.1.1.3">
<td class="ltx_td ltx_align_left" id="A7.T6.1.1.3.1">CIN <cite class="ltx_cite ltx_citemacro_citep">(Ma et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib44" title="">2022</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.3.2">0.0741</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.3.3">2944</td>
</tr>
<tr class="ltx_tr" id="A7.T6.1.1.4">
<td class="ltx_td ltx_align_left" id="A7.T6.1.1.4.1">PIMoG <cite class="ltx_cite ltx_citemacro_citep">(Fang et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib18" title="">2022</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.4.2">0.0212</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.4.3">878</td>
</tr>
<tr class="ltx_tr" id="A7.T6.1.1.5">
<td class="ltx_td ltx_align_left" id="A7.T6.1.1.5.1">RivaGAN <cite class="ltx_cite ltx_citemacro_citep">(Zhang et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib86" title="">2019</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.5.2">-</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.5.3">-</td>
</tr>
<tr class="ltx_tr" id="A7.T6.1.1.6">
<td class="ltx_td ltx_align_left" id="A7.T6.1.1.6.1">SepMark <cite class="ltx_cite ltx_citemacro_citep">(Wu et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib75" title="">2023</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.6.2">0.0109</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.6.3">928</td>
</tr>
<tr class="ltx_tr" id="A7.T6.1.1.7">
<td class="ltx_td ltx_align_left" id="A7.T6.1.1.7.1">DWTDCT <cite class="ltx_cite ltx_citemacro_citep">(Al-Haj, <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib1" title="">2007</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.7.2">-</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.7.3">-</td>
</tr>
<tr class="ltx_tr" id="A7.T6.1.1.8">
<td class="ltx_td ltx_align_left" id="A7.T6.1.1.8.1">DWTDCTSVD <cite class="ltx_cite ltx_citemacro_citep">(Navas et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib50" title="">2008</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.8.2">-</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.8.3">-</td>
</tr>
<tr class="ltx_tr" id="A7.T6.1.1.9">
<td class="ltx_td ltx_align_left" id="A7.T6.1.1.9.1">SSL <cite class="ltx_cite ltx_citemacro_citep">(Fernandez et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib20" title="">2022</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.9.2">2.1938</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.9.3">1072</td>
</tr>
<tr class="ltx_tr" id="A7.T6.1.1.10">
<td class="ltx_td ltx_align_left" id="A7.T6.1.1.10.1">StegaStamp <cite class="ltx_cite ltx_citemacro_citep">(Tancik et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib69" title="">2020</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.10.2">0.0672</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.10.3">1984</td>
</tr>
<tr class="ltx_tr" id="A7.T6.1.1.11">
<td class="ltx_td ltx_align_left" id="A7.T6.1.1.11.1">TrustMark <cite class="ltx_cite ltx_citemacro_citep">(Bui et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib8" title="">2023</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.11.2">0.0705</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.11.3">648</td>
</tr>
<tr class="ltx_tr" id="A7.T6.1.1.12">
<td class="ltx_td ltx_align_left" id="A7.T6.1.1.12.1">EditGuard <cite class="ltx_cite ltx_citemacro_citep">(Zhang et al., <a class="ltx_ref" href="https://arxiv.org/html/2410.18775v1#bib.bib90" title="">2024d</a>)</cite>
</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.12.2">0.2423</td>
<td class="ltx_td ltx_align_center" id="A7.T6.1.1.12.3">1638</td>
</tr>
<tr class="ltx_tr" id="A7.T6.1.1.13">
<td class="ltx_td ltx_align_left ltx_border_bb ltx_border_t" id="A7.T6.1.1.13.1">VINE</td>
<td class="ltx_td ltx_align_center ltx_border_bb ltx_border_t" id="A7.T6.1.1.13.2">0.0795</td>
<td class="ltx_td ltx_align_center ltx_border_bb ltx_border_t" id="A7.T6.1.1.13.3">4982</td>
</tr>
</table>{{< /table-caption >}}
> 🔼 This table presents a performance comparison of various watermarking methods in terms of processing time per image and GPU memory consumption. The metrics were obtained by averaging the results from 1000 images. Note that DWTDCT, DWTDCTSVD, and RivaGAN are excluded from this comparison because their implementations are designed for CPU-only use.
> <details>
> <summary>read the caption</summary>
> Table 6: Comparison of watermarking methods based on running time per single image and GPU memory usage. The results are averaged over 1,000 images. Since the implementations we employed for DWTDCT, DWTDCTSVD, and RivaGAN support CPUs exclusively, they have been omitted from the comparison.
> </details>

</details>




### Full paper

{{< gallery >}}
<img src="paper_images/1.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
<img src="paper_images/2.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
<img src="paper_images/3.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
<img src="paper_images/4.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
<img src="paper_images/5.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
<img src="paper_images/6.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
<img src="paper_images/7.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
<img src="paper_images/8.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
<img src="paper_images/9.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
<img src="paper_images/10.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
<img src="paper_images/11.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
<img src="paper_images/12.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
<img src="paper_images/13.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
<img src="paper_images/14.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
<img src="paper_images/15.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
<img src="paper_images/16.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
<img src="paper_images/17.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
<img src="paper_images/18.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
<img src="paper_images/19.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
<img src="paper_images/20.png" class="grid-w50 md:grid-w33 xl:grid-w25" />
{{< /gallery >}}
