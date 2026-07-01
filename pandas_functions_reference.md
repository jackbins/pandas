# Pandas Functions Reference — Purpose & Problem Solved

Organized by category. Format: `function()` → what problem it solves / when you use it.

---

## 1. Reading & Writing Data (I/O)

| Function | Purpose |
|---|---|
| `pd.read_csv()` | Load CSV file into DataFrame |
| `pd.read_excel()` | Load Excel sheet into DataFrame |
| `pd.read_json()` | Load JSON into DataFrame |
| `pd.read_sql()` | Load data from SQL database via query |
| `pd.read_html()` | Scrape tables directly from a webpage |
| `pd.read_parquet()` | Load columnar Parquet file (fast, compressed) |
| `pd.read_pickle()` | Load a serialized Python object (DataFrame) |
| `pd.read_clipboard()` | Load data copied to clipboard (quick testing) |
| `df.to_csv()` | Export DataFrame to CSV |
| `df.to_excel()` | Export DataFrame to Excel |
| `df.to_json()` | Export DataFrame to JSON |
| `df.to_sql()` | Write DataFrame into a SQL table |
| `df.to_parquet()` | Export to Parquet format |
| `df.to_pickle()` | Serialize DataFrame to disk |
| `df.to_dict()` | Convert DataFrame to Python dictionary |
| `df.to_numpy()` | Convert DataFrame to NumPy array |
| `df.to_markdown()` | Convert DataFrame to markdown table (for reports) |
| `df.to_html()` | Convert DataFrame to HTML table |

---

## 2. Inspecting Data (First Look at Dataset)

| Function | Purpose |
|---|---|
| `df.head()` | View first N rows — quick sanity check |
| `df.tail()` | View last N rows |
| `df.sample()` | Random sample of rows — check for bias/patterns |
| `df.info()` | See dtypes, non-null counts, memory usage |
| `df.describe()` | Summary stats (mean, std, min, max, quartiles) |
| `df.shape` | Get (rows, columns) count |
| `df.columns` | List column names |
| `df.index` | Inspect row index |
| `df.dtypes` | Check data type of each column |
| `df.memory_usage()` | See memory consumed per column — optimize large data |
| `df.axes` | Get row and column labels together |
| `df.ndim` | Number of dimensions (1 = Series, 2 = DataFrame) |
| `df.size` | Total number of elements |
| `df.empty` | Check if DataFrame has no data |
| `df.nunique()` | Count unique values per column — detect categorical vs continuous |
| `df.value_counts()` | Frequency count of unique values — find imbalance/most common category |

---

## 3. Selecting & Indexing (Getting the Right Slice of Data)

| Function | Purpose |
|---|---|
| `df.loc[]` | Select rows/columns by label — precise filtering |
| `df.iloc[]` | Select rows/columns by integer position |
| `df.at[]` | Fast scalar access by label |
| `df.iat[]` | Fast scalar access by position |
| `df.filter()` | Select columns/rows matching a pattern or list |
| `df.query()` | Filter rows using a readable expression string |
| `df.isin()` | Check membership — filter rows where value is in a list |
| `df.where()` | Keep values meeting condition, replace rest with NaN |
| `df.mask()` | Opposite of `where()` — replace values meeting condition |
| `df.select_dtypes()` | Select only columns of a certain dtype (e.g. numeric only) |
| `df.xs()` | Cross-section selection from MultiIndex |
| `df.get()` | Safely get a column, with default if missing |
| `df.pop()` | Remove and return a column |
| `df.take()` | Select rows/columns by integer positions along an axis |

---

## 4. Handling Missing Data (Data Cleaning)

| Function | Purpose |
|---|---|
| `df.isna()` / `df.isnull()` | Detect missing values — find where data is incomplete |
| `df.notna()` / `df.notnull()` | Detect non-missing values |
| `df.dropna()` | Remove rows/columns with missing values |
| `df.fillna()` | Fill missing values with a value, mean, or method |
| `df.interpolate()` | Fill missing values using interpolation (e.g., linear trend) |
| `df.ffill()` | Forward-fill missing values (carry last valid value forward) |
| `df.bfill()` | Backward-fill missing values |
| `df.replace()` | Replace specific values (e.g., placeholder "?" → NaN) |
| `df.combine_first()` | Fill missing values in one DataFrame using another as backup |

---

## 5. Data Cleaning & Transformation

| Function | Purpose |
|---|---|
| `df.drop()` | Remove specific rows or columns |
| `df.drop_duplicates()` | Remove duplicate rows — ensure data uniqueness |
| `df.duplicated()` | Flag duplicate rows for inspection |
| `df.rename()` | Rename columns/index for clarity |
| `df.astype()` | Convert column data type (e.g., string → int) |
| `df.apply()` | Apply a custom function across rows/columns |
| `df.applymap()` | Apply a function to every individual cell |
| `df.map()` | Apply a function/dict mapping to a Series (element-wise substitution) |
| `df.pipe()` | Chain custom functions cleanly in a pipeline |
| `df.assign()` | Add new computed columns without mutating original |
| `df.clip()` | Cap values within a min/max range — handle outliers |
| `df.round()` | Round numeric values to N decimals |
| `df.abs()` | Get absolute value — remove negative signs |
| `df.eval()` | Evaluate a string expression to create/modify columns efficiently |
| `df.reset_index()` | Reset row index to default integers |
| `df.set_index()` | Set a column as the new index |
| `df.reindex()` | Conform data to a new index (align datasets) |
| `df.rename_axis()` | Rename the index/column axis label |
| `df.convert_dtypes()` | Auto-convert columns to best possible dtypes |

---

## 6. Sorting & Ranking

| Function | Purpose |
|---|---|
| `df.sort_values()` | Sort rows by column value(s) — find top/bottom performers |
| `df.sort_index()` | Sort rows/columns by index label |
| `df.rank()` | Assign rank to values — useful in scoring/leaderboard problems |
| `df.nlargest()` | Get top N rows by column value |
| `df.nsmallest()` | Get bottom N rows by column value |

---

## 7. Aggregation & Statistics (Summarizing Data)

| Function | Purpose |
|---|---|
| `df.sum()` | Total of values — e.g., total sales |
| `df.mean()` | Average value — central tendency |
| `df.median()` | Middle value — robust to outliers vs mean |
| `df.mode()` | Most frequent value |
| `df.std()` | Standard deviation — measure of spread/volatility |
| `df.var()` | Variance — spread of data |
| `df.min()` / `df.max()` | Smallest/largest value |
| `df.count()` | Count of non-null values |
| `df.corr()` | Correlation between variables — check if two vars move together (positive/negative/none) |
| `df.cov()` | Covariance between variables — direction of joint variability |
| `df.skew()` | Skewness — check if distribution is asymmetric |
| `df.kurt()` | Kurtosis — check "peakedness"/tail heaviness of distribution |
| `df.quantile()` | Get value at a given percentile — e.g., 90th percentile salary |
| `df.cumsum()` | Running total — useful for cumulative sales/growth |
| `df.cumprod()` | Running product |
| `df.cummax()` / `df.cummin()` | Running max/min — track record highs/lows over time |
| `df.diff()` | Difference between consecutive rows — measure change/growth |
| `df.pct_change()` | Percent change between rows — growth rate, returns |
| `df.agg()` | Apply multiple aggregation functions at once |
| `df.aggregate()` | Same as `.agg()` — flexible multi-stat summary |
| `df.describe()` | Full statistical summary in one call |

---

## 8. Grouping & Pivoting (Segmented Analysis)

| Function | Purpose |
|---|---|
| `df.groupby()` | Split data into groups (e.g., by category) for group-wise analysis |
| `df.pivot_table()` | Summarize data into a cross-tab style table (like Excel pivot) |
| `df.pivot()` | Reshape long data into wide format (no aggregation) |
| `df.melt()` | Reshape wide data into long format — "unpivot" |
| `df.crosstab()` | Frequency table between two categorical variables |
| `df.stack()` | Pivot columns into rows (compress columns into index) |
| `df.unstack()` | Pivot rows into columns (opposite of stack) |
| `df.transform()` | Apply a function but keep original shape — e.g., group-wise normalization |
| `df.filter()` (on groupby) | Keep/discard whole groups based on a condition |
| `df.explode()` | Expand list-like column values into separate rows |

---

## 9. Merging, Joining & Combining Datasets

| Function | Purpose |
|---|---|
| `pd.merge()` | SQL-style join of two DataFrames on key column(s) |
| `df.join()` | Join DataFrames on index (simpler alternative to merge) |
| `pd.concat()` | Stack/append DataFrames vertically or horizontally |
| `df.append()` *(deprecated, use concat)* | Add rows from another DataFrame |
| `df.combine()` | Combine two DataFrames element-wise using a function |
| `df.update()` | Update values in-place using another DataFrame |
| `pd.merge_asof()` | Merge on nearest key — useful for time-series matching |
| `pd.merge_ordered()` | Merge with optional fill/interpolation, preserves order |

---

## 10. Date & Time Handling

| Function | Purpose |
|---|---|
| `pd.to_datetime()` | Convert string/column to datetime type — enables time analysis |
| `pd.date_range()` | Generate a sequence of dates — build time index |
| `df.dt.year` / `.month` / `.day` | Extract date components — seasonal analysis |
| `df.dt.dayofweek` | Get weekday — analyze weekday vs weekend patterns |
| `df.resample()` | Aggregate time series by time period (e.g., daily → monthly) |
| `df.asfreq()` | Convert time series to a specified frequency |
| `df.shift()` | Shift values forward/backward — create lag features, compare periods |
| `df.tshift()` *(deprecated)* | Shift time index |
| `df.rolling()` | Rolling window calculations — moving average, smoothing trends |
| `df.expanding()` | Expanding window calculations — cumulative stats over time |
| `df.ewm()` | Exponentially weighted calculations — trend smoothing giving more weight to recent data |
| `df.between_time()` | Filter rows within a specific time-of-day range |
| `df.at_time()` | Select rows at a specific time |
| `df.tz_localize()` | Assign a timezone to naive datetime data |
| `df.tz_convert()` | Convert datetime to another timezone |

---

## 11. String Operations (`.str` accessor — Text Data Cleaning)

| Function | Purpose |
|---|---|
| `df.str.lower()` / `.upper()` | Normalize text case — fix inconsistent casing |
| `df.str.strip()` | Remove leading/trailing whitespace |
| `df.str.replace()` | Replace substring/pattern — clean text data |
| `df.str.contains()` | Check if string contains pattern — filter text rows |
| `df.str.startswith()` / `.endswith()` | Pattern matching at start/end of string |
| `df.str.split()` | Split string into list/columns — parse compound fields |
| `df.str.extract()` | Extract regex pattern into new column(s) |
| `df.str.len()` | Get string length — detect anomalies in text length |
| `df.str.cat()` | Concatenate strings — combine columns into one |
| `df.str.get_dummies()` | One-hot encode delimited string categories |
| `df.str.pad()` | Pad strings to fixed width |
| `df.str.zfill()` | Zero-pad numbers stored as strings (e.g., zip codes) |
| `df.str.findall()` | Find all regex matches in a string |
| `df.str.slice()` | Extract substring by position |

---

## 12. Categorical Data

| Function | Purpose |
|---|---|
| `pd.Categorical()` | Create a categorical variable — memory efficient, ordered categories |
| `df.astype('category')` | Convert column to category dtype |
| `df.cat.codes` | Get integer codes behind categories — needed for ML models |
| `df.cat.categories` | List defined categories |
| `df.cat.rename_categories()` | Rename category labels |
| `pd.cut()` | Bin continuous data into discrete intervals — e.g., age → age groups |
| `pd.qcut()` | Bin data into quantile-based intervals — equal-sized groups |
| `pd.get_dummies()` | One-hot encode categorical variables for ML models |
| `pd.factorize()` | Convert categorical values into numeric codes |

---

## 13. Reshaping & Combining Structure

| Function | Purpose |
|---|---|
| `df.T` | Transpose rows and columns |
| `df.swapaxes()` | Swap axes of the DataFrame |
| `df.swaplevel()` | Swap levels in a MultiIndex |
| `df.droplevel()` | Remove a level from MultiIndex |
| `df.reorder_levels()` | Reorder MultiIndex levels |
| `pd.wide_to_long()` | Reshape wide-format data into long format |
| `df.squeeze()` | Convert single-column/row DataFrame into a Series |

---

## 14. Comparison & Boolean Logic

| Function | Purpose |
|---|---|
| `df.equals()` | Check if two DataFrames are exactly equal |
| `df.eq()` / `.ne()` | Element-wise equal / not equal comparison |
| `df.gt()` / `.lt()` / `.ge()` / `.le()` | Element-wise greater/less-than comparisons |
| `df.all()` | Check if all values are True — validation checks |
| `df.any()` | Check if any value is True — flag presence of a condition |
| `np.where()` (used with pandas) | Conditional value assignment — create flag/label columns |

---

## 15. Correlation, Similarity & Statistical Relationships

| Function | Purpose |
|---|---|
| `df.corr()` | Measure linear correlation between numeric variables (positive/negative/none) |
| `df.corrwith()` | Correlate one DataFrame's columns against another Series/DataFrame |
| `df.cov()` | Covariance matrix — joint variability direction |
| `pd.crosstab(..., normalize=True)` | Relationship between two categorical variables, as proportions |
| `df.autocorr()` | Correlation of a time series with a lagged version of itself |

---

## 16. Window & Rolling Statistics (Trend Analysis)

| Function | Purpose |
|---|---|
| `df.rolling().mean()` | Moving average — smooth out short-term fluctuations |
| `df.rolling().std()` | Rolling volatility/variability |
| `df.rolling().sum()` | Rolling total — e.g., trailing 7-day sales |
| `df.expanding().mean()` | Cumulative average over time |
| `df.ewm().mean()` | Exponential moving average — trend with recency bias |

---

## 17. Plotting (Quick Visualization, via `.plot`)

| Function | Purpose |
|---|---|
| `df.plot()` | Quick line plot — visualize trend |
| `df.plot.bar()` | Bar chart — compare categories |
| `df.plot.hist()` | Histogram — see distribution shape |
| `df.plot.box()` | Box plot — see spread/outliers |
| `df.plot.scatter()` | Scatter plot — visualize relationship between two variables |
| `df.plot.pie()` | Pie chart — proportion breakdown |
| `df.hist()` | Histogram for all numeric columns at once |
| `df.boxplot()` | Box plot summary of numeric columns |

---

## 18. Memory & Performance Optimization

| Function | Purpose |
|---|---|
| `df.memory_usage(deep=True)` | Accurately measure memory footprint including objects |
| `pd.eval()` | Fast evaluation of expressions on large data |
| `df.eval()` | In-DataFrame fast expression evaluation |
| `df.copy()` | Create independent copy — avoid unwanted mutation of original data |
| `df.convert_dtypes()` | Downcast/optimize dtypes automatically |
| `pd.to_numeric()` | Convert column to numeric type, coercing errors — clean "dirty" numeric columns |

---

## 19. Iteration (Use Sparingly — Slow, but Sometimes Needed)

| Function | Purpose |
|---|---|
| `df.iterrows()` | Loop through DataFrame row by row (as Series) |
| `df.itertuples()` | Loop through rows as lightweight named tuples (faster than iterrows) |
| `df.items()` | Loop through DataFrame column by column |

---

## 20. Miscellaneous Utility

| Function | Purpose |
|---|---|
| `pd.concat()` | Combine multiple DataFrames/Series |
| `pd.Series()` | Create a 1D labeled array |
| `pd.DataFrame()` | Create a 2D labeled data structure |
| `pd.isnull()` / `pd.notnull()` | Module-level null checks |
| `pd.set_option()` | Change display settings (e.g., max rows/columns shown) |
| `pd.options.display.max_rows` | Control how many rows are displayed |
| `df.style` | Apply conditional formatting for visual reports |
| `df.equals()` | Validate two datasets are identical (data integrity checks) |
| `df.duplicated().sum()` | Quick count of duplicate rows |
| `df.T.drop_duplicates().T` | Remove duplicate columns |

---

### Quick Mental Model

- **Load/Save data** → I/O functions (`read_*`, `to_*`)
- **Look at data** → `head`, `info`, `describe`, `shape`
- **Clean data** → `dropna`, `fillna`, `duplicated`, `astype`, `replace`
- **Filter/select** → `loc`, `iloc`, `query`, `isin`
- **Summarize** → `sum`, `mean`, `groupby`, `agg`, `pivot_table`
- **Find relationships** → `corr`, `cov`, `crosstab`
- **Reshape** → `melt`, `pivot`, `stack`/`unstack`, `merge`, `concat`
- **Time analysis** → `to_datetime`, `resample`, `rolling`, `shift`
- **Text cleanup** → `.str.*` methods
- **Prep for ML** → `get_dummies`, `cut`/`qcut`, `astype('category')`

This covers the functions that show up in ~95%+ of real-world pandas data analysis work, from raw/rare edge-case utilities (`merge_asof`, `combine_first`, `wide_to_long`) to the everyday core (`groupby`, `merge`, `corr`, `fillna`).
