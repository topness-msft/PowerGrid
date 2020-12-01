## PowerGrid: Responsive Layout Canvas Component
**PowerGrid** is a Canvas Component that simplifies designing Power Apps to a responsive layout grid (as used with [SharePoint](https://docs.microsoft.com/en-us/sharepoint/dev/design/grid-and-responsive-design) or in [Material Design](https://material.io/design/layout/responsive-layout-grid.html)).  While this isn't a fully automatic layout like the [Canvas Layout Container](https://powerapps.microsoft.com/en-us/blog/new-layout-containers-in-canvas-apps-make-responsive-apps-easier/), it does allow you to more easily make your app identify and respond to specified [pixel width breakpoints](https://docs.microsoft.com/en-us/sharepoint/dev/design/grid-and-responsive-design#breakpoints), and manage control placement according to a [grid layout](https://docs.microsoft.com/en-us/sharepoint/dev/design/grid-and-responsive-design#page-type-grids).  An example of this is below, where the contents are aligned to a column layout, until the window is resized below the "small" breakpoint, where the image shrinks and the body text moves to consume the full width (click for a more in depth demo):
[![PowerGrid Demo](https://github.com/topness-msft/PowerGrid/blob/main/media/PowerGridGif.gif)](https://www.youtube.com/watch?v=QkPObHk9hzk "PowerGrid Demo")
To use PowerGrid, import the solution and reference the component library.  Then, add the PowerGrid component to your app, setting the PowerGrid width and height properties to App.Width and App.Height, respectively.

PowerGrid has these input properties:
| Name | Type | Description |
|--|--|--|
| Fill Color | Color | Color of the grids (when visible) |
| Inner Padding | Number | Distance between columns (pixels) |
| Gutter | Number | Distance between edges of container and columns (pixels)|
| Show Columns | Boolean | Toggles column visibility |
| Breakpoints | Table | Table of pixel breakpoints and labels (see example below) |

The default breakpoints are set as below:

> Table({Size:840, Label: "small"},{Size:1024, Label:
> "medium"},{Size:1440, Label: "large"},{Size:1920, Label: "xlarge"})

PowerGrid has these **Output** properties:
| Name | Type | Description |
|--|--|--|
| Breakpoint | Record | The current breakpoint (both Size and Label) |
| Layout | Record | The column and control layout values |

**Example PowerGrid.Layout properties:**
PowerGrid.Layout.Column1.Left: the leftmost edge of column 1
PowerGrid.Layout.Column3.Right: pixel position of the rightmost edge of column 3
PowerGrid.Top: the pixel position of the grid top (actual column location factoring in gutter)
PowerGrid.Height: the pixel height of the columns
