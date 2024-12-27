---
title: "From Pixels to Pages: Evaluating the Reading Powers of Large Models！"
date: 2024-12-06T18:40:04+08:00
weight: 1
# aliases: ["/first"]
# tags: ["Research"]
# draft: true
# comments: false
# description: "Desc Text."
# disable_share: false
# hide_meta: false
# hide_summary: false # to hide summary in list
# hide_footer: false
math: true
# search_hidden: false # to hide from search page
show_reading_time: true
show_bread_crumbs: true
show_post_nav_links: false # the prev/next after the content
show_code_copy_buttons: true
show_word_count: true
# use_hugo_toc: true
# show_toc: true
# toc_open: true # default expand all
# cover:
#     image: "path"
#     # can also paste direct link from external site
#     # ex. https://i.ibb.co/K0HVPBd/paper-mod-profilemode.png
#     alt: "<alt text>"
#     caption: "<text>"
#     relative: true # To use relative path for cover image, used in hugo Page-bundles
#     responsive_images: true
#     hidden: false
# header:
#   background: "" # background css value
#   background_image: ""
#   gradient: false
#   blur: false
---


{{< button href="https://code.alibaba-inc.com/DamoAGI/CC-OCR" label="GITHUB" external=true >}}
{{< button href="https://huggingface.co/Qwen" label="HUGGING FACE" external=true >}}
{{< button href="https://www.modelscope.cn/datasets/Qwen/CC-OCR/summary" label="MODELSCOPE" external=true >}}
{{< button href="https://arxiv.org/abs/2412.02210" label="Paper" external=true >}}

The ability to read and write is a unique trait of humans and a hallmark of advanced intelligence. That's why it's becoming one of the essential skills that Large Multimodal Models ( LMMs ) must possess as they strive for human-like intelligence. LMMs have demonstrated impressive performance
in recognizing document images with natural language instructions. However, as we dive deeper into more real-world scenarios, we find that challenges still remain. How do we measure to what extent large models can effectively handle complex and richly detailed images that require fine perception? This is definitely a question worth exploring and pondering.

The current landscape lacks a comprehensive benchmark to effectively measure the literate capabilities of LMMs. Existing benchmarks are often limited by narrow scenarios and specified tasks. To this end, we introduce **CC-OCR**, a comprehensive benchmark that possesses a diverse range of scenarios, tasks, and challenges. **CC-OCR** comprises four OCR-centric tracks: multi-scene text reading, multilingual text reading, document parsing, and key information extraction. We evaluate nine prominent LMMs and reveal both the strengths and weaknesses of these models, particularly in text grounding, multi-orientation, and hallucination of repetition. **CC-OCR** aims to comprehensively evaluate the capabilities of LMMs on OCR-centered tasks, driving advancement in LMMs. 



# Leaderborad
{{< figure src="https://img.alicdn.com/imgextra/i2/O1CN01B3N8lf1jfrPii5EoI_!!6000000004576-2-tps-4082-2113.png#center" width="100%">}}

Gemini-1.5-Pro and Qwen2-VL-72B are the two top-performing models. Gemini-1.5-Pro achieves first in the multi-scene OCR, multilingual OCR, and document parsing tracks, while Qwen2-VL-72B takes first place in the KIE track and second place in the multi-scene OCR and document parsing tracks.



# Benchmark Introduction

The **CC-OCR** benchmark is specifically designed to evaluate the OCR capabilities of multimodal large models. It draws from publicly available specialized task data, as well as carefully curated representative data from various real-world application scenarios. **CC-OCR** includes a range of core OCR tasks while also focusing on the challenges and difficulties that arise in applications. The benchmark covers most key perception tasks in the fields of image text and image documents. One of the philosophy behind this work is that high accuracy in perception is the foundation of multimodal cognition. **CC-OCR** comprises four OCR-centric tracks: multi-scene text reading, multilingual text reading, formula recognition, document parsing, table parsing, and key information extraction. It includes 39 subsets with 7,058 full annotated images, of which 41% are sourced from real applications, being released for the first time. This means that the benchmark can better assess the zero-shot recognition capabilities of large models.

{{< figure src="https://img.alicdn.com/imgextra/i3/O1CN01Z4W4qP1ULVZvX3MPh_!!6000000002501-2-tps-4035-2080.png#center" width="90%">}}

The main features of **CC-OCR** include:

1. **Four OCR-centric Tasks**: Multi-Scene Text Reading, Multilingual Text Reading, Document Parsing, and Visual Information Extraction;
2. **Fine-grained visual challenges**: Multi-orientation, multi-scale, wild-scene noise, and various text fonts;
3. **Well annotated**: For OCR, both textual labels and positional boxes are annotated. For Parsing, LaTeX and HTML formats are applicable for documents and tables respectively. For KIE, JSON format is adopted.



# Demo Cases

In the following, we show the challenged examples of **CC-OCR**, along side with the prompt we used in the evaluation and the responses of top players.
{{< fullwidth class="example-container" >}}
{{< example data="cases/ocr1.json" hide=false next=true >}}
{{< example data="cases/ocr2.json" hide=true next=true >}}
{{< example data="cases/ocr3.json" hide=true next=true >}}
{{< example data="cases/ocr4.json" hide=true next=true >}}
{{< example data="cases/ocr5.json" hide=true next=true >}}
{{< example data="cases/ocr6.json" hide=true next=true >}}
{{< example data="cases/ocr7.json" hide=true next=true >}}
{{< /fullwidth >}}

