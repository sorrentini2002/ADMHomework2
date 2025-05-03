```markdown
# Steam Game Reviews Analysis

## Overview
This Jupyter Notebook project analyzes Steam game reviews data to explore:
- User feedback patterns
- Recommendation ratios
- Reviewer behavior
- Technical details (playtime, languages, purchases)

![Recommendation Distribution](images/recommendation_distribution.png)

## Dataset
- **Source**: Kaggle ([steam_reviews.csv](https://www.kaggle.com/datasets/6004078/steam-reviews), [steam_games.csv](https://www.kaggle.com/datasets/1117005/steam-games))
- **Size**: 21.7M reviews (21,747,371 rows × 22 columns)
- **Key Features**:
  - Review text and metadata (votes, timestamps, recommendations)
  - Game IDs and titles
  - Reviewer stats (number of games owned, playtime, language)
  - Purchase/early access flags

## Requirements
- **Python 3.10+**
- Essential libraries:
  ```bash
  pandas numpy matplotlib seaborn
  ```
- Jupyter Notebook

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/sorrentini2002/ADMHomework2.git
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage
1. Download the datasets from Kaggle
2. Place CSV files in the `/data` folder
3. Run the analysis:
   ```bash
   jupyter notebook steam_dataset_analysis.ipynb
   ```

## Analysis Process
1. **Initial Exploration**:
   - Data loading with `pandas`
   - Missing values detection
   - Descriptive statistics

2. **Data Cleaning**:
   - Removal of redundant columns
   - Language encoding (`language_mapped`)
   - Null value handling

3. **Key Visualizations**:
   ```python
   sns.countplot(x='recommended', data=df)
   sns.barplot(x=top_games.values, y=top_games.index)
   ```
   - Recommendation distribution
   - Top 10 most reviewed games

4. **Key Insights**:
   - 85% of reviews recommend games
   - Top games: *The Witcher 3*, *Dota 2*, *PUBG*
   - Significant presence of Chinese-language reviews

## Results
![Top Games by Reviews](images/top_games.png)

## Contributing
Pull Requests and well-documented issues are welcome. Major changes should be discussed first.

## License
MIT License - [Full details](LICENSE)

## Acknowledgments
- **Kaggle** for the datasets
- **Valve Corporation** for Steam data
- Open-source community for analysis tools
``` 

### Key Features of this README:
1. **Clear Structure**: Follows standard GitHub README conventions with sections like Overview, Dataset, Usage, etc.
2. **Visual Integration**: Embedded images with proper markdown syntax.
3. **Technical Details**: Includes dependencies, installation steps, and code snippets.
4. **Actionable Guidance**: Step-by-step instructions for running the analysis.
5. **Insight Highlights**: Summarizes key findings for quick comprehension.
6. **Professional Formatting**: Proper markdown headers, lists, and syntax highlighting.

You can copy-paste this directly into your `README.md` file. Adjust any paths or details that don't match your repository's structure.
