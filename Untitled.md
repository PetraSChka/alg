```python
import plotly.express as px
from plotly.subplots import make_subplots
import pandas as pd
import datetime as dt

blocks = [
    [2,3,4,1,2],
    [4,3,1,4,1],
    [3,2,4,2,1],
    [4,2,1,4,3],
    [3,1,2,4,1]
    ]

asyncMode = [

    dict(
        process=1,
        block=1,
        duration=dt.datetime.fromtimestamp(2).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(0).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=1,
        block=2,
        duration=dt.datetime.fromtimestamp(5).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(2).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=1,
        block=3,
        duration=dt.datetime.fromtimestamp(9).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(5).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=1,
        block=4,
        duration=dt.datetime.fromtimestamp(10).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(9).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=1,
        block=5,
        duration=dt.datetime.fromtimestamp(12).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(10).strftime('%Y-%m-%d %H:%M:%S')
    ),

    dict(
        process=2,
        block=1,
        duration=dt.datetime.fromtimestamp(6).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(2).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=2,
        block=2,
        duration=dt.datetime.fromtimestamp(9).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(6).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=2,
        block=3,
        duration=dt.datetime.fromtimestamp(10).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(9).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=2,
        block=4,
        duration=dt.datetime.fromtimestamp(14).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(10).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=2,
        block=5,
        duration=dt.datetime.fromtimestamp(15).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(14).strftime('%Y-%m-%d %H:%M:%S')
    ),

    # the third process

    dict(
        process=3,
        block=1,
        duration=dt.datetime.fromtimestamp(9).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(6).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=3,
        block=2,
        duration=dt.datetime.fromtimestamp(11).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(9).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=3,
        block=3,
        duration=dt.datetime.fromtimestamp(15).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(11).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=3,
        block=4,
        duration=dt.datetime.fromtimestamp(17).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(15).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=3,
        block=5,
        duration=dt.datetime.fromtimestamp(18).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(17).strftime('%Y-%m-%d %H:%M:%S')
    ),

    dict(
        process=4,
        block=1,
        duration=dt.datetime.fromtimestamp(13).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(9).strftime('%Y-%m-%d %H:%M:%S') 
    ),
    dict(
        process=4,
        block=2,
        duration=dt.datetime.fromtimestamp(15).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(13).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=4,
        block=3,
        duration=dt.datetime.fromtimestamp(16).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(15).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=4,
        block=4,
        duration=dt.datetime.fromtimestamp(21).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(17).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=4,
        block=5,
        duration=dt.datetime.fromtimestamp(24).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(21).strftime('%Y-%m-%d %H:%M:%S')
    ),

    dict(
        process=5,
        block=1,
        duration=dt.datetime.fromtimestamp(16).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(13).strftime('%Y-%m-%d %H:%M:%S') 
    ),
    dict(
        process=5,
        block=2,
        duration=dt.datetime.fromtimestamp(17).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(16).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=5,
        block=3,
        duration=dt.datetime.fromtimestamp(19).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(17).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=5,
        block=4,
        duration=dt.datetime.fromtimestamp(25).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(21).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=5,
        block=5,
        duration=dt.datetime.fromtimestamp(26).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(25).strftime('%Y-%m-%d %H:%M:%S')
    ),
]

sync1Mode = [

    dict(
        process=1,
        block=1,
        duration=dt.datetime.fromtimestamp(2).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(0).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=1,
        block=2,
        duration=dt.datetime.fromtimestamp(5).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(2).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=1,
        block=3,
        duration=dt.datetime.fromtimestamp(9).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(5).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=1,
        block=4,
        duration=dt.datetime.fromtimestamp(10).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(9).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=1,
        block=5,
        duration=dt.datetime.fromtimestamp(12).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(10).strftime('%Y-%m-%d %H:%M:%S')
    ),

    dict(
        process=2,
        block=1,
        duration=dt.datetime.fromtimestamp(6).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(2).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=2,
        block=2,
        duration=dt.datetime.fromtimestamp(9).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(6).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=2,
        block=3,
        duration=dt.datetime.fromtimestamp(10).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(9).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=2,
        block=4,
        duration=dt.datetime.fromtimestamp(14).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(10).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=2,
        block=5,
        duration=dt.datetime.fromtimestamp(15).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(14).strftime('%Y-%m-%d %H:%M:%S')
    ),

    dict(
        process=3,
        block=1,
        duration=dt.datetime.fromtimestamp(9).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(6).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=3,
        block=2,
        duration=dt.datetime.fromtimestamp(11).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(9).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=3,
        block=3,
        duration=dt.datetime.fromtimestamp(15).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(11).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=3,
        block=4,
        duration=dt.datetime.fromtimestamp(17).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(15).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=3,
        block=5,
        duration=dt.datetime.fromtimestamp(18).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(17).strftime('%Y-%m-%d %H:%M:%S')
    ),

    dict(
        process=4,
        block=1,
        duration=dt.datetime.fromtimestamp(14).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(10).strftime('%Y-%m-%d %H:%M:%S') 
    ),
    dict(
        process=4,
        block=2,
        duration=dt.datetime.fromtimestamp(16).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(14).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=4,
        block=3,
        duration=dt.datetime.fromtimestamp(17).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(16).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=4,
        block=4,
        duration=dt.datetime.fromtimestamp(21).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(17).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=4,
        block=5,
        duration=dt.datetime.fromtimestamp(24).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(21).strftime('%Y-%m-%d %H:%M:%S')
    ),

    dict(
        process=5,
        block=1,
        duration=dt.datetime.fromtimestamp(18).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(15).strftime('%Y-%m-%d %H:%M:%S') 
    ),
    dict(
        process=5,
        block=2,
        duration=dt.datetime.fromtimestamp(19).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(18).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=5,
        block=3,
        duration=dt.datetime.fromtimestamp(21).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(19).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=5,
        block=4,
        duration=dt.datetime.fromtimestamp(25).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(21).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=5,
        block=5,
        duration=dt.datetime.fromtimestamp(26).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(25).strftime('%Y-%m-%d %H:%M:%S')
    ),
]

sync2Mode = [
    
    dict(
        process=1,
        block=1,
        duration=dt.datetime.fromtimestamp(2).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(0).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=1,
        block=2,
        duration=dt.datetime.fromtimestamp(11).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(8).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=1,
        block=3,
        duration=dt.datetime.fromtimestamp(15).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(11).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=1,
        block=4,
        duration=dt.datetime.fromtimestamp(16).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(15).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=1,
        block=5,
        duration=dt.datetime.fromtimestamp(25).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(23).strftime('%Y-%m-%d %H:%M:%S')
    ),

    # the second process

    dict(
        process=2,
        block=1,
        duration=dt.datetime.fromtimestamp(6).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(2).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=2,
        block=2,
        duration=dt.datetime.fromtimestamp(13).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(11).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=2,
        block=3,
        duration=dt.datetime.fromtimestamp(16).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(15).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=2,
        block=4,
        duration=dt.datetime.fromtimestamp(20).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(16).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=2,
        block=5,
        duration=dt.datetime.fromtimestamp(26).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(25).strftime('%Y-%m-%d %H:%M:%S')
    ),

    dict(
        process=3,
        block=1,
        duration=dt.datetime.fromtimestamp(9).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(6).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=3,
        block=2,
        duration=dt.datetime.fromtimestamp(15).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(13).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=3,
        block=3,
        duration=dt.datetime.fromtimestamp(20).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(16).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=3,
        block=4,
        duration=dt.datetime.fromtimestamp(22).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(20).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=3,
        block=5,
        duration=dt.datetime.fromtimestamp(27).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(26).strftime('%Y-%m-%d %H:%M:%S')
    ),

    dict(
        process=4,
        block=1,
        duration=dt.datetime.fromtimestamp(13).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(9).strftime('%Y-%m-%d %H:%M:%S') 
    ),
    dict(
        process=4,
        block=2,
        duration=dt.datetime.fromtimestamp(16).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(15).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=4,
        block=3,
        duration=dt.datetime.fromtimestamp(21).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(20).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=4,
        block=4,
        duration=dt.datetime.fromtimestamp(26).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(22).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=4,
        block=5,
        duration=dt.datetime.fromtimestamp(30).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(27).strftime('%Y-%m-%d %H:%M:%S')
    ),

    dict(
        process=5,
        block=1,
        duration=dt.datetime.fromtimestamp(16).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(13).strftime('%Y-%m-%d %H:%M:%S') 
    ),
    dict(
        process=5,
        block=2,
        duration=dt.datetime.fromtimestamp(18).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(16).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=5,
        block=3,
        duration=dt.datetime.fromtimestamp(23).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(21).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=5,
        block=4,
        duration=dt.datetime.fromtimestamp(30).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(26).strftime('%Y-%m-%d %H:%M:%S')
    ),
    dict(
        process=5,
        block=5,
        duration=dt.datetime.fromtimestamp(31).strftime('%Y-%m-%d %H:%M:%S'),
        start=dt.datetime.fromtimestamp(30).strftime('%Y-%m-%d %H:%M:%S')
    ),
]

c_df = pd.DataFrame(asyncMode)
c_fig = px.timeline(c_df, x_start="start", x_end="duration", y="process", color="block")
c_fig.show()

c_df = pd.DataFrame(sync1Mode)
c_fig = px.timeline(c_df, x_start="start", x_end="duration", y="process", color="block")
c_fig.show()

c_df = pd.DataFrame(sync2Mode)
c_fig = px.timeline(c_df, x_start="start", x_end="duration", y="process", color="block")
c_fig.show()
```


<div>                            <div id="7de57e19-0384-48df-a54e-eaf5e8b674a5" class="plotly-graph-div" style="height:525px; width:100%;"></div>            <script type="text/javascript">                require(["plotly"], function(Plotly) {                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("7de57e19-0384-48df-a54e-eaf5e8b674a5")) {                    Plotly.newPlot(                        "7de57e19-0384-48df-a54e-eaf5e8b674a5",                        [{"alignmentgroup": "True", "base": ["1970-01-01 03:00:00", "1970-01-01 03:00:02", "1970-01-01 03:00:05", "1970-01-01 03:00:09", "1970-01-01 03:00:10", "1970-01-01 03:00:02", "1970-01-01 03:00:06", "1970-01-01 03:00:09", "1970-01-01 03:00:10", "1970-01-01 03:00:14", "1970-01-01 03:00:06", "1970-01-01 03:00:09", "1970-01-01 03:00:11", "1970-01-01 03:00:15", "1970-01-01 03:00:17", "1970-01-01 03:00:09", "1970-01-01 03:00:13", "1970-01-01 03:00:15", "1970-01-01 03:00:17", "1970-01-01 03:00:21", "1970-01-01 03:00:13", "1970-01-01 03:00:16", "1970-01-01 03:00:17", "1970-01-01 03:00:21", "1970-01-01 03:00:25"], "hovertemplate": "start=%{base}<br>duration=%{x}<br>process=%{y}<br>block=%{marker.color}<extra></extra>", "legendgroup": "", "marker": {"color": [1, 2, 3, 4, 5, 1, 2, 3, 4, 5, 1, 2, 3, 4, 5, 1, 2, 3, 4, 5, 1, 2, 3, 4, 5], "coloraxis": "coloraxis"}, "name": "", "offsetgroup": "", "orientation": "h", "showlegend": false, "textposition": "auto", "type": "bar", "x": [2000.0, 3000.0, 4000.0, 1000.0, 2000.0, 4000.0, 3000.0, 1000.0, 4000.0, 1000.0, 3000.0, 2000.0, 4000.0, 2000.0, 1000.0, 4000.0, 2000.0, 1000.0, 4000.0, 3000.0, 3000.0, 1000.0, 2000.0, 4000.0, 1000.0], "xaxis": "x", "y": [1, 1, 1, 1, 1, 2, 2, 2, 2, 2, 3, 3, 3, 3, 3, 4, 4, 4, 4, 4, 5, 5, 5, 5, 5], "yaxis": "y"}],                        {"barmode": "overlay", "coloraxis": {"colorbar": {"title": {"text": "block"}}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "legend": {"tracegroupgap": 0}, "margin": {"t": 60}, "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "xaxis": {"anchor": "y", "domain": [0.0, 1.0], "type": "date"}, "yaxis": {"anchor": "x", "domain": [0.0, 1.0], "title": {"text": "process"}}},                        {"responsive": true}                    ).then(function(){

var gd = document.getElementById('7de57e19-0384-48df-a54e-eaf5e8b674a5');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                });            </script>        </div>



<div>                            <div id="10518c73-7412-4807-bc6b-49e002befceb" class="plotly-graph-div" style="height:525px; width:100%;"></div>            <script type="text/javascript">                require(["plotly"], function(Plotly) {                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("10518c73-7412-4807-bc6b-49e002befceb")) {                    Plotly.newPlot(                        "10518c73-7412-4807-bc6b-49e002befceb",                        [{"alignmentgroup": "True", "base": ["1970-01-01 03:00:00", "1970-01-01 03:00:02", "1970-01-01 03:00:05", "1970-01-01 03:00:09", "1970-01-01 03:00:10", "1970-01-01 03:00:02", "1970-01-01 03:00:06", "1970-01-01 03:00:09", "1970-01-01 03:00:10", "1970-01-01 03:00:14", "1970-01-01 03:00:06", "1970-01-01 03:00:09", "1970-01-01 03:00:11", "1970-01-01 03:00:15", "1970-01-01 03:00:17", "1970-01-01 03:00:10", "1970-01-01 03:00:14", "1970-01-01 03:00:16", "1970-01-01 03:00:17", "1970-01-01 03:00:21", "1970-01-01 03:00:15", "1970-01-01 03:00:18", "1970-01-01 03:00:19", "1970-01-01 03:00:21", "1970-01-01 03:00:25"], "hovertemplate": "start=%{base}<br>duration=%{x}<br>process=%{y}<br>block=%{marker.color}<extra></extra>", "legendgroup": "", "marker": {"color": [1, 2, 3, 4, 5, 1, 2, 3, 4, 5, 1, 2, 3, 4, 5, 1, 2, 3, 4, 5, 1, 2, 3, 4, 5], "coloraxis": "coloraxis"}, "name": "", "offsetgroup": "", "orientation": "h", "showlegend": false, "textposition": "auto", "type": "bar", "x": [2000.0, 3000.0, 4000.0, 1000.0, 2000.0, 4000.0, 3000.0, 1000.0, 4000.0, 1000.0, 3000.0, 2000.0, 4000.0, 2000.0, 1000.0, 4000.0, 2000.0, 1000.0, 4000.0, 3000.0, 3000.0, 1000.0, 2000.0, 4000.0, 1000.0], "xaxis": "x", "y": [1, 1, 1, 1, 1, 2, 2, 2, 2, 2, 3, 3, 3, 3, 3, 4, 4, 4, 4, 4, 5, 5, 5, 5, 5], "yaxis": "y"}],                        {"barmode": "overlay", "coloraxis": {"colorbar": {"title": {"text": "block"}}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "legend": {"tracegroupgap": 0}, "margin": {"t": 60}, "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "xaxis": {"anchor": "y", "domain": [0.0, 1.0], "type": "date"}, "yaxis": {"anchor": "x", "domain": [0.0, 1.0], "title": {"text": "process"}}},                        {"responsive": true}                    ).then(function(){

var gd = document.getElementById('10518c73-7412-4807-bc6b-49e002befceb');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                });            </script>        </div>



<div>                            <div id="455ebd57-4ac3-4ff8-8ea8-1337432da605" class="plotly-graph-div" style="height:525px; width:100%;"></div>            <script type="text/javascript">                require(["plotly"], function(Plotly) {                    window.PLOTLYENV=window.PLOTLYENV || {};                                    if (document.getElementById("455ebd57-4ac3-4ff8-8ea8-1337432da605")) {                    Plotly.newPlot(                        "455ebd57-4ac3-4ff8-8ea8-1337432da605",                        [{"alignmentgroup": "True", "base": ["1970-01-01 03:00:00", "1970-01-01 03:00:08", "1970-01-01 03:00:11", "1970-01-01 03:00:15", "1970-01-01 03:00:23", "1970-01-01 03:00:02", "1970-01-01 03:00:11", "1970-01-01 03:00:15", "1970-01-01 03:00:16", "1970-01-01 03:00:25", "1970-01-01 03:00:06", "1970-01-01 03:00:13", "1970-01-01 03:00:16", "1970-01-01 03:00:20", "1970-01-01 03:00:26", "1970-01-01 03:00:09", "1970-01-01 03:00:15", "1970-01-01 03:00:20", "1970-01-01 03:00:22", "1970-01-01 03:00:27", "1970-01-01 03:00:13", "1970-01-01 03:00:16", "1970-01-01 03:00:21", "1970-01-01 03:00:26", "1970-01-01 03:00:30"], "hovertemplate": "start=%{base}<br>duration=%{x}<br>process=%{y}<br>block=%{marker.color}<extra></extra>", "legendgroup": "", "marker": {"color": [1, 2, 3, 4, 5, 1, 2, 3, 4, 5, 1, 2, 3, 4, 5, 1, 2, 3, 4, 5, 1, 2, 3, 4, 5], "coloraxis": "coloraxis"}, "name": "", "offsetgroup": "", "orientation": "h", "showlegend": false, "textposition": "auto", "type": "bar", "x": [2000.0, 3000.0, 4000.0, 1000.0, 2000.0, 4000.0, 2000.0, 1000.0, 4000.0, 1000.0, 3000.0, 2000.0, 4000.0, 2000.0, 1000.0, 4000.0, 1000.0, 1000.0, 4000.0, 3000.0, 3000.0, 2000.0, 2000.0, 4000.0, 1000.0], "xaxis": "x", "y": [1, 1, 1, 1, 1, 2, 2, 2, 2, 2, 3, 3, 3, 3, 3, 4, 4, 4, 4, 4, 5, 5, 5, 5, 5], "yaxis": "y"}],                        {"barmode": "overlay", "coloraxis": {"colorbar": {"title": {"text": "block"}}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "legend": {"tracegroupgap": 0}, "margin": {"t": 60}, "template": {"data": {"bar": [{"error_x": {"color": "#2a3f5f"}, "error_y": {"color": "#2a3f5f"}, "marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "bar"}], "barpolar": [{"marker": {"line": {"color": "#E5ECF6", "width": 0.5}}, "type": "barpolar"}], "carpet": [{"aaxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "baxis": {"endlinecolor": "#2a3f5f", "gridcolor": "white", "linecolor": "white", "minorgridcolor": "white", "startlinecolor": "#2a3f5f"}, "type": "carpet"}], "choropleth": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "choropleth"}], "contour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "contour"}], "contourcarpet": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "contourcarpet"}], "heatmap": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmap"}], "heatmapgl": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "heatmapgl"}], "histogram": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "histogram"}], "histogram2d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2d"}], "histogram2dcontour": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "histogram2dcontour"}], "mesh3d": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "type": "mesh3d"}], "parcoords": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "parcoords"}], "pie": [{"automargin": true, "type": "pie"}], "scatter": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter"}], "scatter3d": [{"line": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatter3d"}], "scattercarpet": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattercarpet"}], "scattergeo": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergeo"}], "scattergl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattergl"}], "scattermapbox": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scattermapbox"}], "scatterpolar": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolar"}], "scatterpolargl": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterpolargl"}], "scatterternary": [{"marker": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "type": "scatterternary"}], "surface": [{"colorbar": {"outlinewidth": 0, "ticks": ""}, "colorscale": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "type": "surface"}], "table": [{"cells": {"fill": {"color": "#EBF0F8"}, "line": {"color": "white"}}, "header": {"fill": {"color": "#C8D4E3"}, "line": {"color": "white"}}, "type": "table"}]}, "layout": {"annotationdefaults": {"arrowcolor": "#2a3f5f", "arrowhead": 0, "arrowwidth": 1}, "coloraxis": {"colorbar": {"outlinewidth": 0, "ticks": ""}}, "colorscale": {"diverging": [[0, "#8e0152"], [0.1, "#c51b7d"], [0.2, "#de77ae"], [0.3, "#f1b6da"], [0.4, "#fde0ef"], [0.5, "#f7f7f7"], [0.6, "#e6f5d0"], [0.7, "#b8e186"], [0.8, "#7fbc41"], [0.9, "#4d9221"], [1, "#276419"]], "sequential": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]], "sequentialminus": [[0.0, "#0d0887"], [0.1111111111111111, "#46039f"], [0.2222222222222222, "#7201a8"], [0.3333333333333333, "#9c179e"], [0.4444444444444444, "#bd3786"], [0.5555555555555556, "#d8576b"], [0.6666666666666666, "#ed7953"], [0.7777777777777778, "#fb9f3a"], [0.8888888888888888, "#fdca26"], [1.0, "#f0f921"]]}, "colorway": ["#636efa", "#EF553B", "#00cc96", "#ab63fa", "#FFA15A", "#19d3f3", "#FF6692", "#B6E880", "#FF97FF", "#FECB52"], "font": {"color": "#2a3f5f"}, "geo": {"bgcolor": "white", "lakecolor": "white", "landcolor": "#E5ECF6", "showlakes": true, "showland": true, "subunitcolor": "white"}, "hoverlabel": {"align": "left"}, "hovermode": "closest", "mapbox": {"style": "light"}, "paper_bgcolor": "white", "plot_bgcolor": "#E5ECF6", "polar": {"angularaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "radialaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "scene": {"xaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "yaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}, "zaxis": {"backgroundcolor": "#E5ECF6", "gridcolor": "white", "gridwidth": 2, "linecolor": "white", "showbackground": true, "ticks": "", "zerolinecolor": "white"}}, "shapedefaults": {"line": {"color": "#2a3f5f"}}, "ternary": {"aaxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "baxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}, "bgcolor": "#E5ECF6", "caxis": {"gridcolor": "white", "linecolor": "white", "ticks": ""}}, "title": {"x": 0.05}, "xaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}, "yaxis": {"automargin": true, "gridcolor": "white", "linecolor": "white", "ticks": "", "title": {"standoff": 15}, "zerolinecolor": "white", "zerolinewidth": 2}}}, "xaxis": {"anchor": "y", "domain": [0.0, 1.0], "type": "date"}, "yaxis": {"anchor": "x", "domain": [0.0, 1.0], "title": {"text": "process"}}},                        {"responsive": true}                    ).then(function(){

var gd = document.getElementById('455ebd57-4ac3-4ff8-8ea8-1337432da605');
var x = new MutationObserver(function (mutations, observer) {{
        var display = window.getComputedStyle(gd).display;
        if (!display || display === 'none') {{
            console.log([gd, 'removed!']);
            Plotly.purge(gd);
            observer.disconnect();
        }}
}});

// Listen for the removal of the full notebook cells
var notebookContainer = gd.closest('#notebook-container');
if (notebookContainer) {{
    x.observe(notebookContainer, {childList: true});
}}

// Listen for the clearing of the current output cell
var outputEl = gd.closest('.output');
if (outputEl) {{
    x.observe(outputEl, {childList: true});
}}

                        })                };                });            </script>        </div>



```python
def critical(matrix):
    i=j=0
    time = matrix[0][0]
    
    while i < len(matrix) - 1:
        while j < len(matrix) - 1:
            if matrix[i][j+1] > matrix[i+1][j]:
                j+=1
                time += matrix[i][j]
                continue
            else:
                time += matrix[i+1][j]
                break
        i+=1
    return time
```


```python
print(critical(blocks))
```

    16
    


```python

```
