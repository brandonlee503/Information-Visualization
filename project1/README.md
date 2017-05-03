# D3 Radar Chart
[bl.ocks.org link](http://bl.ocks.org/chrisrzhou/raw/2421ac6541b68c1680f8/)

A radar chart visualizes multivariate data in a 2D chart of three or more quantitative variables represented on axes.

The project is created using AngularJS and D3.js.

------

## Description
-   This is a variation of the [original][] and [improved][] D3 radar chart.

-   Major improvements include:
    -   Refactoring D3 components (`levels`, `labels`, `axes`, `polygons`, `legend`), which now can be controlled through the `config`
        object.
    -   Abstracting the building and rendering portions of the D3 visualization.
    -   Aside from the basic stacked view, this variation includes a facetting option to plot the graphs in a facet grid.

-   Use the configuration parameters to adjust the plot to your tastes, and you can also choose to view the plots stacked vs facetted.

-   The data input has to be a 4-column CSV (headers MUST be included) conforming to the data schema of:
  -   `group (int/string)`: data to be grouped into an object to plot the required polygon on the radar chart.
  -   `axis (int/string)`: the axis of the radar charts (dimensions of the multivariate data).
  -   `value (int)`: the data value of the given record.
  -   `description (int/string)`: not a mandatory field, and additional columns after this are accepted as well.

-   All D3 logic is contained in the `radar.js` file.  You should be able to look at just this file if you intend to use the
    visualization logic without AngularJS.

------

## Files
-   **`index.html`**: Main HTML file.

-   **`app.js`**: AngularJS core logic to connect Javascript components and D3 visualization updates with user interactions. The
    directive `onReadFile` handles file uploads and the directive `radar` draws the D3 visualization.

-   **`radar.js`**: All D3 logic is contained in this file.  You should use this file if you are looking solely to use D3 without
    AngularJS.

-   **`radarDraw.js`**: This is the directive-link function called by the AngularJS directive `radar` in `app.js`.  Funnels the dataset
    from the angular app into the D3 drawing logic called from `radar.js`.

-   **`style.css`**: stylesheet containing optional D3 classes that can be adjusted (commented out)

-   **`data.csv`**: Three CSV-data files for sample downloads and uploads to the app.

------

## Other Notes
-   You may notice Angular digest errors in the console due to `$scope.$watch`.  Not too familiar on resolving these issues.
-   A big help from this [fiddle][] to help implement an AngularJS `FileReader`.

<!-- external links -->
[original]: http://bl.ocks.org/tpreusse/2bc99d74a461b8c0acb1
[improved]: http://bl.ocks.org/nbremer/6506614
[fiddle]: http://jsfiddle.net/alexsuch/6aG4x/

<!-- ga beacon -->
![Analytics](https://ga-beacon.appspot.com/UA-58181799-1/2421ac6541b68c1680f8)