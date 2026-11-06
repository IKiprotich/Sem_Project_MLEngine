# Smart Watering ML Engine

ICS 3202: Artificial Intelligence | CAT 2

[Open in Colab](https://colab.research.google.com/drive/1Ppl-6UwBnXyo3S8B1qhQTr_FNjNf3I7L) · [View the notebook](DecisionTree_Base.ipynb)

## Run

Open `DecisionTree_Base.ipynb` in Colab, select **Runtime > Run all**, then save. The notebook includes a verified Nairobi ERA5 weather snapshot for 2015–2025, so no weather API download is needed.

## Model and results

The target is `water_today`: **1 = water, 0 = wait**. Weather is real; the 20 plants and watering labels are simulated.

The main model is a deliberately limited, class-balanced Decision Tree with maximum depth 2. It is a teaching baseline, not the best-performing model.

| Evaluation | Base-tree accuracy |
|---|---:|
| Stratified random 20% test set | 65.1% |
| Later years: 2023–2025 | 65.0% |

Its random-test precision is **32.3%**, recall **91.6%**, and F1 **0.478**. It produces many false alarms. The notebook retains the stronger tuned tree, other classifiers and simple baselines for comparison. These scores measure agreement with simulated labels and do not establish field performance.

## Presentation

- **Ian:** data and cleaning.
- **Devyan:** labels and exploration.
- **Alfred:** training and results.

The final cells export the Python model, JSON tree, rules, comparison scores and parity cases. Kotlin integration and field validation remain pending.

Sources: [Open-Meteo](https://open-meteo.com/en/docs/historical-weather-api), [FAO-56](https://www.fao.org/4/X0490E/X0490E00.htm), [WUCOLS](https://ucanr.edu/sites/WUCOLS/) and [scikit-learn](https://scikit-learn.org/stable/).

