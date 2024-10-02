# Matplotlib Properties Guide (Beginner to Intermediate)

## 1. Figure and Axes

### Figure
- `figsize`: Set the size of the figure (width, height) in inches
- `dpi`: Set the resolution of the figure
- `facecolor`: Set the background color of the figure

```python
fig = plt.figure(figsize=(10, 6), dpi=100, facecolor='lightgray')
```

### Axes
- `add_subplot()`: Add a subplot to the figure
- `set_xlabel()`, `set_ylabel()`: Set labels for x and y axes
- `set_title()`: Set the title of the plot
- `set_xlim()`, `set_ylim()`: Set the limits of x and y axes

```python
ax = fig.add_subplot(111)
ax.set_xlabel('X-axis')
ax.set_ylabel('Y-axis')
ax.set_title('My Plot')
ax.set_xlim(0, 10)
ax.set_ylim(-1, 1)
```

## 2. Basic Plotting

### Line Plots
- `plot()`: Create a line plot
  - `color`: Set line color
  - `linestyle`: Set line style ('-', '--', ':', '-.')
  - `linewidth`: Set line width
  - `marker`: Set marker style ('o', 's', '^', etc.)
  - `markersize`: Set marker size

```python
x = np.linspace(0, 10, 100)
y = np.sin(x)
plt.plot(x, y, color='blue', linestyle='--', linewidth=2, marker='o', markersize=5)
```

### Scatter Plots
- `scatter()`: Create a scatter plot
  - `s`: Set marker size
  - `c`: Set marker color (can be an array for color mapping)
  - `alpha`: Set transparency

```python
x = np.random.rand(50)
y = np.random.rand(50)
plt.scatter(x, y, s=100, c=y, alpha=0.5, cmap='viridis')
```

## 3. Customization

### Colors
- Named colors: 'red', 'blue', 'green', etc.
- Hex codes: '#FF0000' (red), '#00FF00' (green), etc.
- RGB tuples: (1, 0, 0) for red, (0, 1, 0) for green, etc.

### Text Properties
- `fontsize`: Set font size
- `fontweight`: Set font weight ('normal', 'bold', etc.)
- `fontstyle`: Set font style ('normal', 'italic')
- `fontfamily`: Set font family

```python
plt.title('My Title', fontsize=16, fontweight='bold', fontstyle='italic')
```

### Legend
- `legend()`: Add a legend to the plot
  - `loc`: Set legend location ('best', 'upper left', 'lower right', etc.)
  - `fontsize`: Set legend font size
  - `frameon`: Show/hide legend frame

```python
plt.plot(x, y, label='sin(x)')
plt.legend(loc='upper right', fontsize=12, frameon=False)
```

## 4. Multiple Plots

### Subplots
- `subplots()`: Create a figure with multiple subplots
- `sharex`, `sharey`: Share x or y axes among subplots

```python
fig, (ax1, ax2) = plt.subplots(2, 1, sharex=True, figsize=(8, 6))
ax1.plot(x, np.sin(x))
ax2.plot(x, np.cos(x))
```

## 5. Specialized Plots

### Bar Plots
- `bar()`: Create a bar plot
  - `width`: Set bar width
  - `align`: Set alignment ('center', 'edge')

```python
categories = ['A', 'B', 'C', 'D']
values = [3, 7, 2, 5]
plt.bar(categories, values, width=0.5, align='center')
```

### Histograms
- `hist()`: Create a histogram
  - `bins`: Set number of bins or bin edges
  - `density`: Normalize the histogram

```python
data = np.random.randn(1000)
plt.hist(data, bins=30, density=True, alpha=0.7)
```

## 6. Saving and Displaying

### Saving Figures
- `savefig()`: Save the figure to a file
  - Supported formats: png, pdf, svg, eps, etc.
  - `dpi`: Set resolution for raster formats
  - `bbox_inches`: Trim extra whitespace

```python
plt.savefig('my_plot.png', dpi=300, bbox_inches='tight')
```

### Displaying Plots
- `show()`: Display all open figures
- `close()`: Close the current figure

```python
plt.show()
plt.close()
```

## 7. Styling

### Built-in Styles
- `style.use()`: Use a predefined style

```python
plt.