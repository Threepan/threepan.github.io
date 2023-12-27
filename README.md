# Threepan-WebSite
 





*由AI生成的图片(原图)
 
*由anythingV5官方模型生成的(使用Stable Diffution Webui控制)

前言
介于当今国内普通群众对于AI并不了解，也没有意识到这是多么重大的事情，故推出此教程。本教程的目的是为了让读者更好的了解、使用AI，从而为2024疯狂AI年、未来做准备。在现在这个时代，数据体量、质量即为最重要的，深度学习极度依赖于此。故本教程可以看作众多教程的集合，同时可能大部分皆引用自他人的文章和论文，出处均会标注。
如需软件本体、引用内容原网页请找Threepan。如需全合集，请确定您的电脑是否至少有1T储存空间。
                                                         ————Threepan
正文
发展历史：
人工智能这个概念自从20世纪人类开启计算机时代后经常被反复提及，在许多电影里也经常出现，比如《终结者》《复仇者联盟》。到了近代，众多关于深度学习的论文被提出，为LLM,diffution扩散模型的出现打下了基础。
AIGC(Artificial Intelligence Generated Content)这个概念，可以毫不夸张地称之为本年度在人工智能领域内圈内乃至圈外最为火爆的一个话题。对于一般大众而言，AIGC的热议热潮，应当溯源至去年年底2022年，即Stable Diffusion的开源公布，以及随之而来的一系列借助Stable Diffusion为基础的工作。
这些成果使得人工智能绘画领域呈现出前所未有的高品质创作与创意，而开源工具Stable Diffusion WebUI和ComfyUI与商业化产品Midjourney的问世，则大幅降低了普罗大众使用此类工具的门槛。
从技术角度来看，AI绘画热潮的兴起要归功于扩散模型的引入。
生成纪元
打基础”的2020秋-2021年秋：
扩散模型：
扩散模型的概念早在2015年于国际机器学习会议（ICML）上就提出了理论构想，但其初现并未引起广泛的关注。
到了2020年6月，加州大学伯克利分校的一篇题为DDPM去噪扩散概率模型的NeurIPS论文，在更加庞大的数据集上展现出与当时最优的生成对抗网络（GAN）模型相媲美的性能，研究人员方才逐渐领悟到扩散模型在内容创作领域所蕴藏的威力与前景。
连续扩散模型：
回到2020年的十月，斯坦福大学的研究人员Jiaming Song提出了DDIM（Diffusion Denoising Implicit Model），在提升了DDPM采样效率的基础上，仅用50步就能达到1000步采样的效果。DDIM不仅实现了高效率的采样方法，其作为确定性的采样方法还为后续的研究开创了一种类似于GAN Invesion的方法，用于实现各种真实图像的编辑与生成。
值得一提的是，DDIM的第一作者Jiaming Song与Yang Song出自同一研究组，而Yang Song则在同一时间段内推动了扩散模型一体两面的另一面，也即Score-based的研究。有趣的是，这两种不同的研究角度也在Yang Song本人在2021年的2月份放出的ICLR一篇论文中得以统一。
接着，来到2021年的二月，OpenAI发布了“Improved Diffusion”：这篇论文提出了后来被广泛采用的Cosine Noise Schedule，Importance sampling，以及Stride Sampling加速采样等技术。
继之而来的，是2021年五月OpenAI所发布的“Classifier Guidance”（亦被称为Guided Diffusion）。这篇论文提出了一项重要的策略，即通过基于分类器的引导来指导扩散模型生成图像。借助其他多项改进，扩散模型首次成功击败了生成领域的巨头“GAN”，同时也为OpenAI的DALLE-2（一个图像和文本生成模型）的发布奠定了基础。
而后，来到2021年的十二月，DDPM的一作发布了“Classifier Free Guidance”：对“Classifier Guidance”进行了改进，使得扩散模型的引导过程仅需使用扩散模型本身，而不再需要依赖分类器进行实现。这一创新极大地丰富了扩散模型的应用范围与灵活性。

*copy from “Stable Diffusion一周年：这份扩散模型编年简史值得拥有”(https://zhuanlan.zhihu.com/p/651613931)
离散型扩散模型：
在离散型扩散模型领域，在同一时间，也涌现出了一系列对后续工作具有很大影响的工作，例如：
•	于2021年2月发布的论文Multinomial Diffusion可谓是最早探索离散扩散模型的研究之一。该论文探讨了离散扩散模型的形式与应用。
•	于2021年7月发布的D3PM几乎可以被视为后续所有离散扩散模型研究的理论基础。这份论文内容之丰富，以至于其中附录的每一个章节都足以构成一篇完整的论文。
•	于2021年7月发布的Insertion and Deletion Diffusion提出了一种非常有趣的加噪方法，但尽管创新，却似乎未在学术界引起太大的震动。
•	于2021年8月发布的ImageBART将离散扩散模型应用于大规模图像生成，然而遗憾的是，它仍然采用自回归模型的方式。
这些离散型扩散模型的探索为图像生成领域带来了新的思路与方法，虽然在某些方面取得了进展，但也有待进一步的发展和完善。
“百花齐放”的2021秋-2022年春：
时间进入2021年秋，正逢ICLR和CVPR投稿。在本次CVPR中，我们迎来了“Stable Diffusion”的前身“Latent Diffusion”，还有那些为离散Diffusion做大做强的“VQ Diffusion”和“Unleashing Transformers”，以及离散进行到底的“MaskGIT”等一系列杰出的工作。
然而，要真正让这些扩散模型在学术界和工业界广泛传播以至于产生出圈的影响力，这个规模还不够，人们还需等待。与此同时，本次ICLR会议也见证了扩散模型理论上的一个重要里程碑，这是中国研究者为之付出巨大努力的成果。来自浙江大学的“PNDM”和清华朱军团队的“Analytic-DPM”，荣获了ICLR 2022最佳论文奖项，将扩散模型的采样加速推向极致。Google团队为大家带来了基于训练的快速采样器“GGDM”和“Progressive Distillation”等创新工作。
除了这些，还有一项非常具有启发性的工作《Label-Efficient Semantic Segmentation with Diffusion Models》，揭示了扩散模型的潜在空间蕴藏着的丰富语义信息。这或许将启发了后续一系列基于使用扩散模型作为backbone以及利用注意力机制的图像编辑技术以及扩散模型在感知领域的应用。
在这个时间节点，扩散模型逐渐走入人们的视野，各大公众平台纷纷推出涉及它的文章，然而事实却是，这类模型仍然主要停留在研究领域，尤其是在做图像生成的圈子里。
主流的深度学习研究人员或许仍然沉浸在Vision Transformer所带来的短暂火热中，他们不知道的是，一场针对扩散模型的军备竞赛即将如同腥风血雨般到来。

“大步迈向大模型时代”：2022春-2022年秋：
2022年的上半年，我们迎来了扩散模型的第一个出圈震撼。四月，来自OpenAI的DALLE-2横空出世，通过利用扩散模型以及海量数据，DALLE-2呈现出了前所未有的理解和创造能力。
一系列超现实主义作品通过OpenAI的开放API涌现而出，文生图模型也开始在社交平台上引起热烈讨论。
 
△图像截取自DALLE-2
虽然在这个节点，非研究人员熟知的可能还是文生图模型而非背后的扩散模型支柱。不过没关系，DALLE-2的出圈一定程度上引起了更多研究人员对于扩散模型的关注度。
事实上，一场针对扩散模型的军备竞赛已然在NeurIPS 2022进行热身！
在本次会议投稿周期：
•	DALLE-2开放的不到一个月，来自谷歌的Imagen放出，取代DALLE-2成为了最先进的文生图模型。（荣获NeurIPS 2022 best paper）
•	针对扩散模型设计方案的讨论以及改进的edm（荣获NeurIPS 2022 best paper）。
•	Stable Diffusion的基石Laion-5B发布(荣获NeurIPS 2022 best paper）。
•	一系列探索扩散模型扩散形式的探索，Bit-Diffusion、Variational-Diffusion、Cold-Diffusion、Soft-Diffusion、Non-uniform Diffusion、Retrieval-Augmented Diffusion。
•	快速采样的进一步发展：DPM-Solver、DFNO等。
•	更多的应用：做3D生成的DreamFusion（荣获ICLR 2023 Best Paper），做视频生成的Video Diffusion，做图像重建的DDRM等。
在这一阶段，扩散模型本身的理论和设计边界被极大地探索与扩宽，为下半年爆发性出现的下游应用进一步奠定了基础。
 
△图片截取自DreamFusion
后生成纪元
“军备竞赛启动”：2022秋-2023年春
Diffusion Model+Anything！(扩散模型+任何东西！)
2022年的下半年注定是扩散模型发展最为迅猛和关键的半年。在经过前一年的不懈探索后，扩散模型的理论研究逐渐平稳，研究的方向逐步转向了大规模的应用实践。在这半年，在这段时间里，我们见证了众多领域的突破性应用，包括但不限于：
•	Image Restoration的爆发应用：Equilibrium Diffusion、Shadow Diffusion、DDNM、Rain Diffusion。
•	Image Perception的初步尝试：DiffusionDet、Pix2Seq-D、DiffusionInst、MAGE、Peekaboo、ODISE、DDPS、DDP。
•	文本生成领域的探索：Diffusion-LM、Diffusion-Seq、DDCap、UniD3。
•	3D生成上的进一步探索：Render3D、Magic3D、Point-E、MeshDiffusion。
•	视频生成的进一步探索：Latent Video Diffusion、Video Fusion
•	医学图像上的探索：MedSegDiff。
•	图像编辑上的探索：
•	1）Text-driven（文本驱动）：Prompt-to-prompt、Imagic、InstructPix2Pix、Textual Inversion。
•	2）Subject-driven（对象驱动）：Dreambooth、Paint by Example。
•	Stable Diffusion release
•	1）2022-8-22：initial release（初始版本）
2）2022-12-7：v2.1 release（v2.1发布）
大规模的应用尝试是这一阶段的主旋律，而随着Stable Diffusion的开放，文生图模型再度出圈，扩散模型逐渐被大众所熟知，而后续一系列基于Stable Diffusion的工作也将如雨后春笋般到来。
这些工作涵盖了图像编辑、更为强大的3D生成等领域，将图像生成再度推进，使其更加贴近人类需求。
 
△图片截取自Stable Diffusion v2
“手慢无”：2023春-至今
可控图像生成与编辑是这一阶段的主旋律，这催生了非常非常多的工作，在这个阶段，几乎每天都有新的论文和Demo放出，论文轰炸之快，瞠目结舌。
 
 
△图片截取自Stable Diffusion 2
总的来说，这一阶段的2D图像的工作主要集中在（包括但不限于）：
1、Controllable Image Generation（可控的图像生成）
广义上，可控生成包括了下面描述的许多子问题。在这里，我们主要将其限定在如何在文生图的基础加入额外的如语义分割图，深度图做引导的图像生成，这通常也被称之为Grounded Generation、Layout-driven Generation等。
典型的工作包括GLIGEN、ControlNet和T2I Adapter。其中最为火爆的当属ControlNet，它的出现加上基于Lora的定制化，使得扩散模型成为了绘画圈和动漫圈的一个重磅炸弹。
 
△图片来自ControlNet
2、Subject|Concept–driven/Exemplar-based Image Editing（对象（概念）驱动的/基于示例的图像编辑）
Subject-driven Image Generation这个任务指的是，希望生成的图像包含给定的物体，比如说给一张一只狗的照片，我们希望生成包含这只狗的其他照片。
这个方向最出名的工作当属DreamBooth，它荣获CVPR 2023的best paper Honorable Mention，与此同时，也是火热的Lora定制化的基础算法。除此之外，后续还有一系列工作：
•	如防止模型生成某些 concept，例如裸体，敏感照片的Erasing Concepts from Diffusion Models
•	在一张图片中同时生成编码多个concept的FastComposer、Mix of Show、Cone2、SVDiff
•	在一张图片中插入新物体的（带Grounding信息）的DreamEdit、Anydoor
 
△图片截取自Anydoor
3、Text-driven Image Editing（文本驱动的图像编辑）
基于文本的图像编辑也是一个重要的研究方向。对于这个任务，我们的需求通常是给定一个生成好的图文对，我们编辑文字，再通过一些方法，能够对已经生成的图像进行编辑。例如把“一只狗”换成“一只猫”或者强化某些词的权重等。典型的工作包括：
•	前一个阶段就已经出现的Prompt-to-prompt、Imagic、InstructPix2Pix、Textual Inversion。
•	这个阶段的新工作pix2pix-zero、SEGA、MastCtrl。
 
△图片来自InstructPix2Pix
4、Image Inpainting/Outpainting（图像修复/扩展）
Inpainting通常是指将某一块区域的物体移除或者替换成其他物体，outpainting则是希望将图像外围进行补全。扩散模型的出现也极大改善了这类任务的性能，一些典型工作包括Repaint、SmartBrush等。
 
△图片来自SmartBrush
5、Style Transfer（风格迁移）
也有一些工作利用扩散模型做风格迁移，如StyleDrop和BLIP-Diffusion。
 
△图片来自StyleDrop
6、Point-based Interactive Image Editing（基于点的交互式图像编辑）
最近特别火热的DragGAN也带火了交互式图形编辑，Diffusion方向follow的工作有DragDiffusion、DragonDiffusion以及FreeDrag。
 
△图片来自DragGAN
这一阶段诞生了非常非常多很有意思的工作，但从使用的技术上基本可以总结为：
Attention Control（即通过修改注意力实现编辑，图文对齐等目的，例如Prompt2Prompt，Attend and Excite等）；
Layer Injection（即通过插入一些层实现额外的输入控制，例如ControlNet）；
Finetue（通过Test-time或Training time的Finetune实现，例如DreamBooth和InstructPix2Pix）；
Textual Inversion（通过修改text embedding）等。
下一步是什么？
截止到2023年8月，扩散模型距离DDPM发表已经过去了2年10个月，距离Stable DIffusion发布也过去了1年。
这一年来的高速发展诞生了数不胜数的爆款。基于扩散模型的生成式工具，包括但不限于图像生成，音乐生成，视频生成，3D资产生成，骨骼动作生成等，也逐步走入了设计师以及大众的工作流，并切切实实地改善着广大打工人的工作效率。
尽管如此，当前的诸多工具仍不完美，不管是在学术上的研究还是工程上的落地上仍然具有很多改进的空间。
典型的议题包括但不限于，如何让生成的图像更加符合文本？如何改进模型使得不需要黑魔法般的Prompt也能生成高质量的图片？如何做更加可控的生成，实现个性化物体的加入，指定风格，指定位置？如何对不满意的生成结果进行编辑同时保持前后高度的一致性？如何进一步改善生成式模型对硬件的需求？等。
这里提到的许多议题在现有工作中可能均有涉及，但这些议题的Stable Diffusion时刻可能仍未到来。
过去的一年是激动人心的，ChatGPT和Stable Diffusion的发布为人类迈向通用人工智能（AGI）迈出了重要的一步，而接下来迎接我们的仍将是令人期待和兴奋的后GPT时代。
尽管当前全球面临着诸如经济下行，区域冲突，去全球化等的发展难题，尽管黄仁勋把家里所有煤气灶都交出来也解决不了计算资源短缺的问题，但幸运的是，在这个星球上，我们仍然有着无数出色的研究人员在默默耕耘，在朝着实现AGI的理想奋斗。
或许在不远的将来，AGI真的能成为有生之年，谁知道呢？
“The Best Way to Predict the Future is to Create it.”——P.Drucker&A.Lincoln.
（“预测未来的最好方法是创造它”——P.德鲁克和A.林肯。）

*发展历史第二段到本段上方，皆copy from “Stable Diffusion一周年：这份扩散模型编年简史值得拥有”(https://zhuanlan.zhihu.com/p/651613931)
