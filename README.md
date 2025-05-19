# AI Content Safety Analysis

**Project Overview**

This project explores the patterns and challenges in AI content moderation by analyzing the Aegis AI Content Safety Dataset, a collection of approximately 11,000 human-LLM conversations annotated for various harmful content categories. Through data merging, multi-dimensional analysis, and visualization, the project reveals insights into the types of harmful content that arise in LLM interactions, how these risks are distributed, and the technical challenges of effective content moderation.

**Tools & Packages Used**

- Python and pandas for data processing and analysis
- Matplotlib and Seaborn for exploratory data visualization
- Adobe Illustrator for creating visualization designs
- ai2html for generating responsive SVG visualizations
- HTML/CSS for web presentation

**Data Collection & Processing**

**Datasets**
The analysis centered on two key datasets: the Aegis AI Content Safety Dataset(https://huggingface.co/datasets/nvidia/Aegis-AI-Content-Safety-Dataset-2.0), which contains annotated conversations between humans and the Mistral-7B language model, and Anthropic's Helpful and Harmless (HH-RLHF) dataset (https://huggingface.co/datasets/Anthropic/hh-rlhf/viewer?views%5B%5D=train), which provided the original human prompts. The Aegis dataset builds upon Anthropic's work by using its prompts but generating new responses with Mistral-7B and adding comprehensive safety annotations. I further supplemented these with a large-scale content moderation test set, merging these disparate sources and taxonomies to create a unified classification system.

**Further Analysis**
Using pivot tables and cross-tabulation techniques, I extracted complex relationships between risk categories, creating a co-occurrence matrix to identify patterns of overlapping harms. This revealed that while most conversations contain a single risk (9,042), a significant number (1,485) contain multiple overlapping risks, adding complexity to moderation efforts.


**Visualizations**

- Most Common Content Risks Chart: A horizontal bar chart showing the distribution of risk categories across the dataset, revealing that "Other Risks" accounts for nearly half of all flagged content.
- Risk Source Distribution Chart: A grouped bar chart comparing the origin of harmful content (user vs. LLM) across different risk categories, showing that responsibility varies significantly by risk type.
- Multi-Risk Complexity Chart: A vertical bar chart displaying the number of conversations containing different numbers of risk categories, illustrating the complexity challenge in content moderation.
- Ambiguous Content Pie Chart: A pie chart highlighting the proportion of ambiguous vs. categorized risks, emphasizing the significant challenge posed by content that doesn't fit established taxonomies.

**Key Findings**

Nearly half (46%) of all flagged content falls into the ambiguous "Other Risks" category, highlighting significant gaps in current content moderation taxonomies
Both users and AI models contribute to unsafe interactions, with the model sometimes generating harmful content independently
While most flagged conversations (86%) involve only one risk category, a significant minority (14%) contain multiple overlapping risks
Content moderation challenges stem from ambiguity, shared responsibility, and the complexity of multiple co-occurring risks

**Implementation**

All visualizations were created as responsive SVGs using ai2html to ensure proper display across desktop and mobile devices. I developed separate landscape and portrait versions of each chart to optimize the user experience on different screen sizes.

**Limitations**

- The dataset contains conversations with a specific model (Mistral-7B) and may not represent behavior across all LLMs
- The annotations reflect judgments from a limited pool of U.S.-based annotators and may not capture cultural nuances across global contexts
- The "Other Risks" category lacks detailed sub-categorization, limiting deeper analysis of these ambiguous harms
- The large 'contentmoderation_testset', while comprehensive, introduces potential sampling biases
