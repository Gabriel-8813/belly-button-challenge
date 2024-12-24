# belly-button-challenge
challenge 14
# Data Retrieval

The application fetches data from a remote JSON file hosted at the provided URL. This data contains details about various samples, including sample names, metadata, and sample values.

# Initialization

The init() function is executed on page load. Here is a step-by-step breakdown of its functionality:
1. Data Loading: It uses d3.json to load the data.
2. Dropdown Population: The names from the data are extracted and used to populate a dropdown menu (#selDataset), allowing users to select different samples.
3. Default Sample: The first sample in the list is selected by default, triggering the display of charts and metadata by calling the buildCharts() and buildMetadata() functions.

# Event Handling

The optionChanged(newSample) function is invoked whenever a new sample is selected from the dropdown:

 - It fetches and displays the relevant charts and metadata for the selected sample using the same methods as during initialization.

## Metadata Display

The buildMetadata(sample) function is responsible for:
1. Metadata Filtering: It filters the metadata based on the selected sample ID.
2. Displaying Metadata: It clears previous metadata and appends new data to the panel (#sample-metadata) in a readable format.

# Chart Generation

The buildCharts(sample) function creates visualizations for the selected sample:
1. Data Processing: It retrieves and processes sample-specific data, including OTU IDs, labels, and values.
2. Bubble Chart: A bubble chart is constructed using Plotly that visualizes sample_values versus otu_ids, with the size of the bubbles representing the sample values.
3. Bar Chart: A horizontal bar chart is created to display the top 10 most abundant bacterial cultures, mapping the sample values to the OTU IDs, with appropriate labels.

### Visualization Libraries

D3.js: Used for manipulating documents based on data, enabling dynamic updates of the dropdown and metadata.
Plotly.js: Used for rendering the visualizations (bubble and bar charts) interactively in the dashboard.