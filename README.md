
<p align="center">
<a href=""><img src="https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fpro.statics.techuangyi.com%2F2018%2F06%2F21%2Fzt7NJjTG5r8PsHyY5SS3aw6b.jpg%3Fx-oss-process%3Dimage%2Fresize%2Cm_lfit%2Cw_1366%2Ch_0&refer=http%3A%2F%2Fpro.statics.techuangyi.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1650599174&t=cc22a495c7d6574cad47c1060626ef46" align="middle" width = "600"></a>
</p>

<a href=""><img src="https://img.shields.io/badge/python-3.8+-aff.svg"></a> <a href="https://www.ssymmetry.com/"><img src="https://img.shields.io/badge/Inc-SuperSymmetry%20Technologies-blue"></a> <a href=""><img src="https://img.shields.io/badge/OS-Linux-green"></a>

## 一、简介
论文链接：https://arxiv.org/abs/2302.09432

评测基准网站：https://bbt.ssymmetry.com/index.html

预训练语言模型（PLM），如 BERT 和 T5，通过在大规模语料库上的自监督预训练极大的提升了各种自然语言处理任务的平均表现。随着中国金融行业的不断发展以及数字化进程的推进，越来越多的NLP任务需求亟待解决。各类金融机构，如政府、银行、投资机构、互联网金融公司等，都需要可以落地的NLP能力。为了提升中文金融NLP领域的整体水平，一些公司已经先行研究并发布了一些中文金融预训练语言模型，例如FinBERT和Mengzi-BERT-base-fin。然而，这些模型都是基于BERT-base模型训练的，架构种类单一且落时，参数数量（约1.1亿）已经落后于当前的技术水平，且存在语料库规模较小的问题，无法满足不断丰富的领域NLP能力需求。因此，中文金融领域迫切需要先进架构的、大参数量的PLM。除此之外，金融行业的NLP任务需求主要集中在信息抽取等方面，要求模型具有较高的实体知识理解和记忆能力。研究表明，预训练语言模型具有一定的实体知识理解和记忆能力，但是还存在一定的不足。因此，很多研究通过知识增强的预训练方法来提高PLM对实体知识的理解和记忆能力。

研究表明，预训练语料库的规模与多样性对PLM的性能和泛化能力具有关键作用。因此，要更好的训练PLM，首要任务是搜集大规模多样性的语料库。然而，目前中文金融领域缺乏大规模多样性开源语料库，已有的中文金融领域模型大多基于小规模的私有语料库，这严重限制了中文金融PLM能力的提升，因此，中文金融领域迫切需要一个大规模多样性的开源语料库。

在PLM的架构，参数规模和语料库之外，促使PLM取得大幅改进和快速迭代的一个关键外部驱动力是评测基准的普遍使用。这些基准使用单一分数来统一评估多种任务中模型的平均性能，从而实现了预训练语言模型之间的正面、直接和全面地的比较，给研究人员提供了统一的预训练语言模型评价标准。例如，现有英文PLM的通用评测基准是GLUE和SuperGLUE，中文PLM的通用评测基准是CLUE，几乎所有PLM都会参与对应基准的评测，以更好的对比其他模型的性能。然而，现有的语言评估基准大多在通用领域，中文金融领域没有公开可用的评测基准。这导致中文金融领域现有的预训练语言模型在不同的任务集合上进行评测，难以相互比较，阻碍了中文金融领域PLM性能的快速提升。因此，中文金融领域迫切地需要一个自然语言处理评测基准。

为了解决上述问题。我们的主要工作汇总如下：

  - 1.目前最大规模的中文金融领域开源语料库BBT-FinCorpus。预训练语料库的规模与多样性对PLM的性能和泛化能力具有重要作用，所以为了更好的训练PLM，首先需要搜集大规模多样性的语料库。然而，目前中文金融领域缺乏大规模多样性开源语料库，已有的中文金融领域模型多数基于小规模的私有语料库，严重限制了中文金融PLM的能力提升。为此，我们构建了BBT-FinCorpus，一个包含有从四种异质性来源获取的约300GB文本的大规模多样性语料库。针对如何确定语料库的覆盖范围和语料来源集合的问题，我们首先搜集了中文互联网上可获取的所有中文金融NLP任务数据集，并根据其文本来源分布来确定所需要爬取的文本来源集合。在确认好需要爬取的文本来源集合之后，我们使用基于代理的分布式爬虫技术实现大规模爬取网页上的文本。
  
  - 2.目前最大规模的中文金融领域知识增强型预训练语言模型BBT-FinT5。PLM的架构与参数量对其性能有重要影响。现有的中文金融领域PLM都基于较为原始的BERT模型架构，参数量也相对较小，不能满足日益丰富的领域NLP需求。因此，我们基于T5模型架构构建了一个拥有十亿参数量的目前最大规模的中文金融领域预训练语言模型BBT-FinT5。为了在有限的硬件算力条件下，尽可能高效地利用好硬件算力，我们使用DeepSpeed加速框架对预训练过程进行效率优化。此外，我们还针对T5模型设计了独特的知识增强预训练方法，通过实验证明了该方法的有效性。
  
  - 3.首个中文金融领域自然语言处理评测基准CFLEB。现有的自然语言处理评估基准多是通用领域的，没有公开可用的中文金融领域评测基准。这导致中文金融领域现有的预训练语言模型在不同的任务集合上进行评测，难以相互比较，阻碍了中文金融领域PLM性能的快速提升。为此，我们首先构建了首个中文金融领域自然语言处理评测基准CFLEB，包含六种不同的任务，涵盖对PLM理解与生成能力的评估。针对评测基准任务的选择及其选择标准问题，我们认为领域评测基准应当着重强调任务的实用性，以更好的反映学术界改进PLM对现实世界的帮助。为此，我们首先邀请金融领域专家对所有可获取的中文金融任务进行了实用性评价，筛选出具有较高实用性评分的任务。之后，我们综合任务数据集的开源情况确定了六个任务数据集作为最终的评测基准。该评测基准的早期版本命名为FinCUGE，包含八个任务，该版本目前已舍弃。
  
## 二 、大规模中文金融领域语料库BBT-FinCorpus
我们经过爬取、清洗和转化得到了大规模中文金融领域语料库 BBT-FinCorpus，包含以下四种语料：
公司公告 在过去二十年中由中国所有上市公司发布的公司公告。原始数据为 PDF 格式，总大小约为 2TB。使用 PDF 解析器将 PDF 文件转换为文我们件，转换后的文件的总大小为 105GB。示例如图

<div align=center><img src="http://125.74.158.86:2336/image/1.jpg" align="middle" width = "600"></div>

研究报告 由券商、投行等投资机构发布的针对宏观经济、板块、行业和个股的研究报告，分析研究对象的现状并展望其未来发展趋势。原始数据为PDF格式，总大小约为1TB。经转化后的文我们件总量约11GB。示例如图

<div align=center><img src="http://125.74.158.86:2336/image/2.jpg" align="middle" width = "600"></div>

财经新闻 从新浪财经，腾讯财经，凤凰财经，36Kr 和虎嗅等网站爬取的过去五年内的财经新闻。经清洗后的文我们件总量约 20GB。示例如图

<div align=center><img src="http://125.74.158.86:2336/image/3.jpg" align="middle" width = "600"></div>

社交媒体 股吧和雪球网过去二十年内的所有股民和博主发表的帖子。经清洗后的文本总量约 120GB。示例如图

<div align=center><img src="http://125.74.158.86:2336/image/4.jpg" align="middle" width = "600"></div>

目前开源了该语料库的base版和large版，分别包含每种语料各4GB和16GB，如需使用，请发送邮件至model@ssymmetry.com 标题为BBT-FinCorpus-{base or large}申请，内容中说明身份、所属机构和用途

## 三 、大规模中文金融领域预训练语言模型BBT-FinT5

我们使用与T5-v1.1模型相同的模型架构和预训练任务，在BBT-FinCorpus上预训练得到了约有两亿参数的BBT-FinT5-base和约有十亿参数的BBT-FinT5-large，可在github仓库中的Model文件夹获得。目前我们正在训练120亿参数的类GPT模型。我们使用的预训练加速方法和知识增强预训练方法如下。

3.1 预训练加速
DeepSpeed是一个基于ZeRO(https://doi.org/10.48550/arxiv.1910.02054)提出的内存优化与训练加速方法实现的开源深度学习加速库。我们使用了DeepSpeed实现的优化器状态并行和梯度并行对预训练过程进行加速。

特别地，针对训练过程中FP16半精度浮点格式出现梯度溢出的问题，我们发现应用BFLOAT16半精度浮点格式进行优化可以有效解决这一问题，而无需反复调节梯度放缩系数等超参数。在深度神经网络的训练中，用于表示网络中每一个参数的浮点数的值范围（即指数范围）要比其尾数精度对训练的稳定性和效果更加重要，因此，BFLOAT16格式使用与FP32格式一样的八位指数位来记录与FP32格式一样大的的指数范围，作为代价，其尾数位比FP16少3个。广泛的实验证明，这一取舍使得BFLOAT16格式具有与FP16格式一样的较高速度和较低内存占用的同时，具有与FP32格式相近的训练稳定性和效果。
3.2 基于三元组遮蔽的知识增强预训练方法

我们首先使用远程监督算法获取知识图谱CN-DBPedia中某个三元组对应的语句。具体而言，给定百科中的文档，首先在知识图谱中找到候选三元组：三元组的头实体或尾实体包含在文档的标题中。然后从候选三元组中选择头实体和尾实体在文档中的同一句子中被提及的三元组，并假定该句子包含了该三元组描述的关系信息。

之后，对于一个句子及其包含的三元组，将三元组拼接在句子之前。对于三元组部分，我们随机选择其中的一元进行遮蔽，对于句子部分，随机选择其中15\%的随机长度span进行遮蔽。最后，将遮蔽好的三元组与句子输入模型并要求模型预测，如图所示。模型将学习根据三元组中没有被遮蔽的两个元和部分遮蔽的句子填补三元组中被遮蔽的元，这一过程使得模型需要更好的理解和记忆与实体有关的知识。

<div align=center><img src="http://125.74.158.86:2336/image/5.png" align="middle" width = "600"></div>

### 四 、中文金融自然语言处理评测基准
CFLEB最终包含的六项任务如下，其中有两项语言生成任务和四项语言理解任务：

### （1）FinNA 
- 金融新闻摘要数据集。输入一段金融新闻，需要模型生成一句话摘要，评价指标为Rouge。其中训练集包含24000条数据，验证集包含3000条数据，测试集包含3000条数据。示例数据如下。
    - 输入：
    ``` json
    {"text":"天宇股份公告，预计 2021 年半年度归属于上公司股东的净利润 1.7 亿元-2.3 亿元，同比下降39.68%-55.41%。公司主营产品沙坦类原料药受低端市场激烈竞争影响，原料药销售价格较去年同期下降..."}
    ```
    - 输出：'天宇股份: 半年度净利润预降 40%-55%。'
    ***

### （2）FinQA 
- 金融新闻公告事件问答数据集。由DuEE-fin数据集转化得到。输入一段金融新闻或公告，和一个与文本中发生的事件有关的问题，需要模型根据文本生成问题答案。问题的范围包含文本中包含的事件类型，以及某个事件对应的发生时间和人物等要素；答案为问题对应的文本中的事件类型或事件要素的列表。评价指标为F1-Score。其中训练集包含16000条数据，验证集包含2000条数据，测试集包含2000条数据。示例数据如下
    - 输入：
    ``` json
    {"text":"新城悦服务股份回购事件对应的每股交易价格是什么? 新城悦“自救”: 1064 万港元回购公司 190万股股份 7月8 日，新城悦服务 (01755.hk) 发布公告称，公司于今日回购 190 万股普通股票，占据现有已发行股份的 0.23171%。回购股份每股付出价格区间为 5.30 港元至 5.83 港元，付出总额为1064 万港元。..."}
    ```
    - 输出：'5.30 港元至 5.83 港元'
    ***
 
 ### （3）FinNL 
- 金融新闻分类数据集。对于给出的金融新闻，需要模型将其多标签分类到可能的十五种类别，类别包括公司、行业、大盘、中国、外国、国际、经济、政策、政治、期货、债券、房地产、外汇、虚拟货币、新冠、能源和其它。评价指标为F1-Score。其中训练集包含8000条数据，验证集包含1000条数据，测试集包含1000条数据，示例如表
    - 输入：
    ``` json
    {"text":"[市场评论: 投资者已消化 CPI 高预期美债仍受追捧] 10 年期美国国债的抛售正在停止，这表明投资者已经消化了周三 CPI 为 7.1% 的预期。若这一数据符合预期，那么国债利率将比通胀率低5.34%，与过去一个月左右的水平一致。..."}
    ```
    - 输出：'外国，债券'
    ***
 
 ### （4）FinRE
- 金融新闻关系抽取数据集。对于给出的金融新闻和头实体-尾实体对，需要模型分类实体对的关系到包含空关系的44种关系类别，包含拥有、持股、竞争、收购、交易、合作、减持等财经金融领域的特有关系类别。评价指标为F1-Score。其中训练集包含7454条数据，验证集包含1489条数据，测试集包含3727条数据，示例如表
    - 输入：
    ``` json
    {"text":"东方航空 AH 股临时停牌传将与上航合并，东方航空，上航"}
    ```
    - 输出：'合并'
    ***
  
  ### （5）FinFE
- 金融社交媒体文本情绪分类数据集。对于给出的金融社交媒体文本，需要模型分类该文本的情绪为消极-中性-积极三种类别，评价指标为准确率。其中训练集包含8000条数据，验证集包含1000条数据，测试集包含1000条数据。示例如表
    - 输入：
    ``` json
    {"text":"3.29 增发价是原始股，你们知道吗? 最少要涨十福"}
    ```
    - 输出：'积极'
    
  ### （6）FinNSP
- 金融负面消息及其主体判定数据集。对于给出的金融新闻或社交媒体文本及其中包含的实体，需要模型判断该文本中是否包含有针对某个实体的负面消息，并指出负面消息的主体是哪个实体，评价指标为F1-Score。其中训练集包含4800条数据，验证集包含600条数据，测试集包含600条数据。
    - 输入：
    ``` json
    {"text":"今年 4 月，重庆市反诈骗中心民警发现一条疑似诈骗线索:一家名为北银创投的公司涉嫌网络贷款诈骗犯罪，北银创投"}
    ```
    - 输出：'是，北银创投'
    ***

此外，CFLEB的早期版本FinCUGE曾包含FinCQA和FinESE两个任务，现版本已移除。

我们参考CLUE和CUGE的做法，将任务按能力需求不同汇总为多个排行榜，以便研究者可以从不同的角度观察参与评测的模型的能力排行。CFLEB的各排行榜如下：
（1）总排行榜：包含全部的六个任务，从文本摘要，文本问答，文本分类，关系抽取，情绪分析等多个维度全面评测模型在金融自然语言理解与生成任务上的能力。
（2）理解能力排行榜：包含FinNL，FinRE，FinFE和FinNSP四个语言理解类任务。从文本分类，关系抽取，情绪分析等多个维度全面评测模型在金融自然语言理解任务上的能力。
（3）生成能力排行榜：包含FinNA和FinQA两个语言生成类任务。从文本摘要，文本问答等维度评测模型在金融自然语言生成任务上的能力。



### 汇总
<div align=center><img src="http://125.74.158.86:2336/image/6.png" align="middle" ></div>

### 创新点罗列
- 知识增强
    1. 微软，创始人，比尔盖茨[SEP]比尔盖茨于19XX年创建了微软公司
    2. 随机mask三元组中的一元或两元

<p align="center">
<a href="https://www.ssymmetry.com/"><img src="http://112.80.242.54:2333/picture/20220620-144534.png" align="middle" width = "600"></a>
</p>
