# Elections Data Analysis and Visualization

This project is focused on analyzing and visualizing 2024 Lok Sabha election results data. The main components of the project include a Jupyter Notebook for data analysis and visualization, a Power BI report, and a CSV file containing the election results.

## Project Structure

- `Data_AnaVis.ipynb`: Jupyter Notebook for data analysis and visualization.
- `Election_Report.pbix`: Power BI report for interactive data visualization.
- `election_results_2024.csv`: CSV file containing the election results data.

## Requirements

To run the Jupyter Notebook, you need to have the following Python packages installed:

- pandas
- matplotlib
- seaborn

You can install the required packages using the following command:

```sh
pip install pandas matplotlib seaborn
```

## Data Analysis and Visualization

The Jupyter Notebook `Data_AnaVis.ipynb` contains the code for analyzing and visualizing the election results data. The main steps include:

1. Grouping the data by party/alliance and summing the margin of victory.
2. Sorting the parties by margin in descending order.
3. Plotting a pie chart to visualize the margin of victory share by party/alliance.

### Example Code

```python
# Group by Party/Alliance and sum the margin of victory
party_margin_share = data.groupby('Leading Party')['Margin'].sum().reset_index()

# Sorted parties by margin (largest first)
party_margin_share = party_margin_share.sort_values(by='Margin', ascending=False)

# Defined figure size
plt.figure(figsize=(10, 8))

# Plot pie chart
wedges, texts, autotexts = plt.pie(
    party_margin_share['Margin'],
    labels=None,  # Hide direct labels
    autopct='%1.1f%%',  # Show percentage
    colors=sns.color_palette('muted'),
    startangle=140,
    wedgeprops={'edgecolor': 'black'}
)

# Adding a legend 
plt.legend(wedges, party_margin_share['Leading Party'], title="Parties", bbox_to_anchor=(1, 1))

# Title
plt.title('Margin of Victory Share by Party/Alliance', fontsize=14)

# Show plot
plt.show()
```

## Power BI Report

The `Election_Report.pbix` file is a Power BI report that provides interactive visualizations of the election results data. You can open this file using Power BI Desktop to explore the data further.

## Data Source

The `election_results_2024.csv` file contains the election results data used in this project. Make sure this file is in the same directory as the Jupyter Notebook when running the analysis.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Acknowledgements

- The data used in this project is fictional and for demonstration purposes only.
- The visualizations are created using Matplotlib and Seaborn libraries.
