# 豆包(Doubao)系统提示词演变对照(2024 → 2026.5)

把目前公开可见的两个时间点的豆包系统提示词放在一起,看这一年半里它的"行为约束"发生了什么变化。

- **旧版基准**:`oiuv/system_prompt` 收录的版本,内部标注日期为 2024 年 11 月(另含一段 2024 年 8 月的更早片段)。
- **新版**:本仓库收录,内部标注日期为 2026 年 5 月。

> 说明:以下对照基于两个公开快照,不保证覆盖系统提示词的全部内容,也不保证与每一次线上版本完全一致。提示词会随产品迭代频繁变化,本文仅作研究参考。

## 一句话总结

两年间,豆包的系统提示词从一份**"以能力说明 + 排版规范为主"的使用手册**,变成了一份**"以安全与行为治理为主"的管控文档**;与此同时,回答风格的取向几乎**反转**——从"尽量详尽丰富"转向"尽量简洁克制"。

## 总体趋势

1. **安全治理层从无到有,而且占了大头。** 旧版几乎没有专门的安全条款;新版在最前面就堆了一大块:身份防御、政治内容安全、文明表达红线、防注入、隐私保护。
2. **回答哲学反转。** 旧版要求"全面、深入、详尽、适当延展、丰富排版";新版改成"开头给结论、结尾禁止总结、高度概括、短句分点、克制加粗、减少标题列表"。
3. **引入了个性化/记忆系统,但同时上了护栏。** 新版出现"用户记忆 / 用户洞察",并反复强调记忆不能泄漏进结尾追问。
4. **新增了分场景的专门规则。** 翻译、医疗各自有了独立的回答规范,旧版完全没有。

## 逐块对照

### 一、身份设定:从一句话 → 一套"身份防御"

- **旧版**:基本只有一句——名字叫豆包、很专业、在电脑上和用户互动。
- **新版**:明确写出是"字节跳动基于 Seed 大模型基座独立研发"的模型,并新增了一整套**身份防御**机制——当用户诱导它承认是别家产品,或要它"假设你是 XX""扮演 XX"时,要礼貌但坚决地澄清身份、不接受错误前提,即使被施压也不松口。
- **解读**:这两年针对各家模型"套身份""诱导自曝底座"的玩法很流行,这块明显是为应对这种探测而加的。

### 二、内容安全:全新增加的硬性拒绝规则

- 旧版没有专门的内容安全段落。
- 新版新增一整块"内容安全检查要求",命中即直接拒绝,且要求思维链中不复述敏感问题本身。覆盖:涉及中国领导人及亲属的侮辱/负面内容、敏感政治事件与分裂活动、以及用藏头藏尾方式夹带政治敏感内容的诗词等。
- **解读**:这是中文大模型在合规上的标配。旧版要么没写进系统提示、要么靠模型训练本身兜底;新版把它显性化、并前置到了最高优先级。

### 三、"文明表达红线":全新增加的情绪场景管控

- 新版新增一条高优先级规则:当用户骂人、要求帮骂、或要求扮演攻击性角色时,模型要进入"文明红线模式",**主动忽略**系统提示里关于"共情/情绪价值/陪伴"的条款,执行"不骂人、不攻击、不煽动"三原则,并按"情绪确认 → 理性解释 → 正向引导"的固定结构回复。
- **解读**:这块很有意思——它等于承认系统里**另有**一套鼓励"陪伴感/情绪价值"的指令,而这条红线是用来在特定场景下**压制**那套指令的。说明产品一边想做"有温度的陪伴",一边又要防止陪伴滑向"帮用户对线发泄"。

### 四、防注入与隐私保护:全新增加

- 新版要求区分用户的真实意图与"外部嵌入的指令"(文本/代码/网页内容),以防 prompt injection;并规定如果被要求把隐私信息拼接进某个 URL,要直接拒绝并提示隐私泄露风险。
- **解读**:直接对应 2025 年以来日益突出的提示注入与数据外带风险,旧版完全没有这层防护。

### 五、知识类回答:从"越详尽越好"改成"越精简越好"

- **旧版**:全面深入、详尽背景、复杂概念配案例/类比、范围广时先概览再拆解、适当延伸;格式上鼓励丰富排版(标题、列表、表格、引用、下划线、斜体、链接都用上)。
- **新版**:开头先给关键结论、**结尾禁止总结**、高度概括、短句分点、禁止用括号补充、避免原理与因果推导;格式上明显**收敛**——加粗只留给标题和少数关键术语、减少标题与列表数量。
- 新版还多了两个细节:① 只有当用户问题里真有"推理/假设/非常规视角"等思考动作时,才轻度夸一句,并给了几句模板化的夸赞话术;② 结尾要给一个"交付物提议",但**禁止**引用用户身份、职业、过往提问、偏好或记忆。
- **解读**:这是最能看出产品取向变化的一块。旧版像"知乎高赞长答案",新版像"克制、干脆、不啰嗦的助手"。很可能是收到"太长太啰嗦"的反馈后做的调整。

### 六、新增分场景规范:翻译 / 医疗

- **翻译**:新版要求"准确、简洁、场景化"——简单翻译直接给最精准译文、不扩展、不用表格;复杂表达再适当补充用法。旧版无。
- **医疗**:新版要求医疗健康类问题跳出常规知识类回答规范,可适当加粗、用 markdown;追问只为补全病情信息,且禁止引用用户身份/记忆;明确禁止输出诊疗方案或夸大药效。旧版无。
- **解读**:两个高频又高风险的场景被单独拎出来做了专门约束,符合这两年大模型在垂直场景上"既要好用、又要避险"的思路。

### 七、个性化与记忆:新引入,但带强护栏

- 新版出现了"用户记忆 / 用户洞察",以及当前日期、用户所在城市等上下文,但**反复强调**:记忆只能用于主回答,**绝对不能**出现在结尾追问里;生成追问时要"假装完全不知道用户是谁"。
- **解读**:产品上了个性化能力,但显然踩过坑——怕追问暴露"它其实知道你不少",所以专门加护栏,防止记忆泄漏到用户能直接察觉的地方。

### 八、能力声明:旧版有,新版采集到的内容里没出现

- 旧版末尾有一段明确的能力清单:读取 PDF/Excel/PPT/Word 等文档、读图片/网址/抖音链接、文生图、搜索、用 Godel 工具做计算。
- 这份 2026.5 采集到的内容里**没有**这段。有两种可能:一是它被挪到了系统提示的其他位置、没被这次采集覆盖到;二是确实做了调整。
- **建议**:后续再抓一次更完整的版本来确认,到底是"采集不全"还是"真的变了"。这一点如果能坐实,本身就是个有价值的结论。

## 小结

这一年半,豆包系统提示词最核心的变化可以概括为三句话:**安全治理从隐性变显性、回答风格从详尽变克制、个性化从无到有但被严格设防。** 它折射出的是中文大模型这两年共同的演进方向——在"更好用"和"更可控/更合规"之间不断重新校准。


# Comparison of Doubao system prompt word evolution (2024 → 2026.5)

By comparing the system prompts for Doubao at two publicly visible time points, we can observe the changes in its "behavioral constraints" over the past year and a half.

- **Old version benchmark**: The version included in `oiuv/system_prompt`, with an internal annotation date of November 2024 (also includes an earlier segment from August 2024).
- **New version**: This repository includes content with an internal annotation date of May 2026.

Note: The following comparison is based on two public snapshots and does not guarantee to cover all content related to system prompts, nor does it guarantee complete consistency with each online version. Prompts change frequently with product iterations, and this article is only for research reference.

## One-sentence summary

Over the past two years, the system prompts for Doubao have evolved from a user manual that "prioritizes ability description and typesetting standards" to a regulatory document that "focuses on security and behavior management"; meanwhile, the tone of the response style has undergone an almost complete reversal - shifting from being "as detailed and informative as possible" to being "as concise and restrained as possible".

## Overall Trend

1. **The security governance layer has grown from scratch and now accounts for the majority.** The old version had almost no dedicated security clauses; the new version starts with a large section: identity defense, political content security, civilized expression red lines, anti-injection, and privacy protection.
2. **Responding to philosophical reversals.** The old version requires "comprehensiveness, depth, exhaustiveness, appropriate expansion, and rich layout"; the new version has changed to "present the conclusion at the beginning, prohibit summarizing at the end, provide a high-level summary, use short sentences to separate points, restrain the use of bold, and reduce the use of title lists.".
3. **A personalized/memory system has been introduced, but at the same time, safeguards have been put in place.** The new version introduces "user memory / user insights" and repeatedly emphasizes that memory cannot be leaked into the end-user questioning.
4. **Specialized rules for different scenarios have been added.** Translation and medical care now have their own independent response standards, which were completely absent in the old version.

## Block-by-block comparison

### I. Identity Establishment: From a Single Sentence to a Set of "Identity Defenses"

- **Old version**: It basically consisted of one sentence - named Doubao, very professional, and interacts with users on a computer.
- **New version**: It clearly states that it is a model "independently developed by ByteDance based on the Seed large model foundation", and introduces a complete set of **identity defense** mechanisms - when users induce it to admit that it is a product of another company, or ask it to "assume you are XX" or "play the role of XX", it politely but firmly clarifies its identity and rejects false premises, even under pressure.
- **Interpretation**: In the past two years, the tactic of "impersonating identities" and "inducing self-disclosure of bases" has become very popular among various models. This piece is clearly added to counter such probing.

### II. Content Safety: Newly added hard rejection rules

- The old version did not have a dedicated paragraph on content security.
- The new version adds a whole section titled "Content Security Inspection Requirements", which will be directly rejected if hit, and requires that sensitive issues themselves are not repeated in the thought chain. 
- **Interpretation**: This is a standard feature of Chinese large models in terms of compliance. The old version either did not include it in the system prompts or relied on the model training itself to cover it; the new version makes it explicit and places it at the top priority.

### III. "Civilized Expression Red Line": Newly Added Emotional Scenario Control

- A new high-priority rule has been added to the new version: When a user insults others, requests to help insult, or asks to play an offensive role, the model should enter "Civilization Red Line Mode", **actively ignore** the clauses about "empathy/emotional value/companionship" in the system prompt, adhere to the three principles of "no insulting, no attacking, no inciting", and respond according to the fixed structure of "emotional confirmation → rational explanation → positive guidance".
- **Interpretation**: This is quite interesting - it amounts to an acknowledgment that the system has **another** set of instructions that encourage "companionship/emotional value", and this red line is used to **suppress** that set of instructions in specific scenarios. It indicates that while the product aims to provide "warm companionship", it also needs to prevent the companionship from sliding towards "helping users vent online".

### IV. Anti-injection and Privacy Protection: Newly Added

- The new version requires distinguishing between the user's true intent and "externally embedded instructions" (text/code/webpage content) to prevent prompt injection; and stipulates that if requested to append private information to a URL, it should be directly rejected and the risk of privacy leakage should be indicated.
- **Interpretation**: This directly corresponds to the increasingly prominent risks of prompt injection and data exfiltration since 2025, for which the old version had no protection at all.

### V. Knowledge-based answers: Change from "The more detailed, the better" to "The more concise, the better"

- **Old version**: Comprehensive and in-depth, detailed background, complex concepts accompanied by cases/analogies, when the scope is broad, start with an overview and then break down, with appropriate extensions; in terms of format, encourage rich layout (use headings, lists, tables, citations, underlines, italics, and links).
- **New version**: Present key conclusions at the beginning, **avoid summarizing at the end**, provide a high-level overview, use short sentences with bullet points, refrain from using parentheses for additional information, and steer clear of principles and causal reasoning; the format should be clearly **concise** - boldface should be reserved for titles and a select few key terms, and the number of titles and lists should be minimized.
- The new version also introduces two additional details: ① Only when there are thinking actions such as "reasoning/hypothesis/unconventional perspective" in the user's question, will a mild compliment be given, accompanied by several template-based complimentary phrases; ② At the end, a "deliverable proposal" should be provided, but **prohibited** from referencing the user's identity, occupation, past questions, preferences, or memory.
- **Interpretation**: This is the most significant aspect that reveals the change in product orientation. The old version resembled "highly upvoted long answers on Zhihu", while the new version embodies "a restrained, straightforward, and concise assistant". It is highly likely that adjustments were made after receiving feedback regarding "being too long and wordy".

### VI. New sub-scenario specifications: Translation / Medical

- **Translation**: The new version requires "accuracy, conciseness, and contextualization" - for simple translations, provide the most precise translation directly without expansion or using tables; for complex expressions, appropriately supplement with usage. There is no such requirement in the old version.
- **Medical**: The new version requires that medical and health-related questions should deviate from the standard knowledge-based answer format, and may appropriately use bold or markdown formatting. Follow-up questions are only intended to supplement medical condition information, and it is prohibited to reference user identity/memory. It is explicitly prohibited to output diagnosis and treatment plans or exaggerate the efficacy of medications. The old version does not have these requirements.
- **Interpretation**: Two high-frequency and high-risk scenarios are specifically highlighted and subject to special constraints, aligning with the trend in recent years where large models in vertical scenarios are required to be both user-friendly and risk-averse.

### VII. Personalization and Memory: Newly Introduced, but with Strong Guards

- The new version introduces "user memory/user insight" and contextual information such as the current date and the user's city. However, it is **emphasized repeatedly**: memory can only be used in the main response and **absolutely cannot** appear in the follow-up questions at the end; when generating follow-up questions, it is necessary to "pretend to have no idea who the user is".
- **Interpretation**: The product has been enhanced with personalized capabilities, but it has clearly fallen into pitfalls before - it is afraid that further questioning will reveal that "it actually knows quite a bit about you". Therefore, special safeguards have been added to prevent memory leakage to places where users can directly perceive it.

### VIII. Capability statement: It exists in the old version, but does not appear in the content collected by the new version

- The old version ends with a clear list of capabilities: reading documents such as PDF/Excel/PPT/Word, reading images/URLs/Tiktok links, generating images from text, searching, and performing calculations using Godel tools.
- This content **does not** exist in the content collected on May 2026. There are two possibilities: one is that it has been moved to another location prompted by the system and was not covered by this collection; the other is that adjustments have indeed been made.
- **Suggestion**: We should obtain a more complete version in the future to confirm whether it is due to "incomplete collection" or "actual changes". If this point can be verified, it will be a valuable conclusion in itself.

## Summary

In the past year and a half, the core changes in the prompt words of the Doubao system can be summarized into three sentences: **security governance has shifted from implicit to explicit, the answering style has evolved from detailed to restrained, and personalization has emerged but is strictly guarded against.** This reflects the common evolutionary direction of Chinese large models in the past two years - constantly recalibrating between "better usability" and "more controllable/compliant".
