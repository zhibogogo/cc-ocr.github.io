---
title: "从像素到整页文档：快测测你的大模型识字能力!"
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


读写能力是人类独有的能力，是高等级智能的特征，因此也成为了多模态大模型追求类人智能时必须具备的能力之一。 多模态大模型的发展迅速，在文档理解方面的进步一样让人惊叹。雀跃之余，当我们深入到更多物理世界场景中时，我们发现挑战依然存在。如何衡量大模型多大程度上可以处理好结构丰富的和需要精细感知的富文本图片呢？这是值得探讨和思索的问题。当前领域缺乏一个全面的数据集来有效衡量多模态大模型这方面的能力。传统的OCR数据集通常局限于狭窄的场景和特定任务上。为此，我们制作了**CC-OCR**，一个涵盖多种情景、多种任务和多挑战的综合OCR评测集。**CC-OCR**包括四个以OCR为中心的赛道：多场景文字识别、多语言文字识别、文档解析和关键信息提取。此外，我们评估了九个突出的多模态大模型，并揭示了这些模型的优势和弱点，特别是在文本定位、多方向准确度和重复输出幻觉方面。**CC-OCR**旨在全面评估多模态大模型在以OCR为中心的任务上的读写能力，推动多模态大模型的发展。



# 榜单
{{< figure src="https://img.alicdn.com/imgextra/i2/O1CN01B3N8lf1jfrPii5EoI_!!6000000004576-2-tps-4082-2113.png#center" width="100%">}}

Gemini-1.5-Pro， Qwen2-VL-72B 和 GPT4o在榜单中位列前三甲. Gemini-1.5-Pro 在多场景文字识别、多语言文字识别和文档解析三个赛道上斩获第一。Qwen2-VL-72B 在信息抽取赛道荣获桂冠，在多场景文字识别和文档解析赛道暂居次席，让我们期待下个版本的表现。



# 评测集介绍

**CC-OCR**评测集是一个专门为评测多模态大模型OCR能力而制作的数据集。数据集的来源中，不仅借鉴了已公开的专项任务数据，也精心地收集了应用场景中有代表性数据。**CC-OCR**涵盖了一系列OCR的核心任务，同时，也注重真实场景下的困难和挑战。这些核心任务包括：多场景文字识别、多语言文字识别、文档解析、表格解析、公式解析、固定实体信息抽取和开放词表信息抽取。任务覆盖了图像文字和图像文档领域大部分所有感知层的任务。这也是本数据背后的理念之一，即，感知层的绝对准确是多模态认知的基石。**CC-OCR**覆盖了39个子数据集，共有7058张精标的图像数据，其中41%来自应用场景，首次对外披露，这意味着本评测集可以更好衡量大模型零样本识别能力。

{{< figure src="https://img.alicdn.com/imgextra/i3/O1CN01Z4W4qP1ULVZvX3MPh_!!6000000002501-2-tps-4035-2080.png#center" width="90%">}}

**CC-OCR**评测集的亮点如下:

1. **四大OCR核心任务**: 多场景文字识别，多语言文字识别，复杂文档解析，以及视觉信息抽取；
2. **细粒度视觉挑战**: 复杂排版，多方向文字，尺度变化大，自然场景光影噪声，手写，以及多样字体；
3. **精细的多元素标注**: 对于OCR, 不仅标注了文本内容还有位置信息。 对于解析，文档和表格分别使用了LaTeX和HTML格式。对于抽取，采用了JSON格式。



# Demo Cases

在下面的例子中，我们展示了一些**CC-OCR**评测集的样本，同时每张图下面还附上了我们在评测中使用的prompt，以及该场景下表现好的模型的输出结果。
{{< fullwidth class="example-container" >}}
{{< example data="cases/ocr1.json" hide=false next=true >}}
{{< example data="cases/ocr2.json" hide=true next=true >}}
{{< example data="cases/ocr3.json" hide=true next=true >}}
{{< example data="cases/ocr4.json" hide=true next=true >}}
{{< example data="cases/ocr5.json" hide=true next=true >}}
{{< example data="cases/ocr6.json" hide=true next=true >}}
{{< example data="cases/ocr7.json" hide=true next=true >}}
{{< /fullwidth >}}

