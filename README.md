# Thread FeatureScript

## Thread Feature
Parameter option:
>   * Thread size M1 ~ M10
>   * Length of the Thread\
[Source Code](https://github.com/JCTGY/onshape_CAD_FeatureScript/blob/master/thread.fs)\
[Onshape Document](https://cad.onshape.com/documents/fa2c2ec63e032fe923d391dc/w/6056dc84910a12dddbff2ca8/e/0c6dea32aea85828cc3f2808)

Thread size from [FULLER: Basic Metric Thread Chart](https://www.fullerfasteners.com/tech/basic-metric-thread-chart-m1-m100-2/)\
Custom own pitch size and cut size: \
In the main function, can change the var pitch and var cutter_size\
Note that the default is in millimeter
```
        var cSys is CoordSystem = coordSystem(othreadAxis.origin, xDirection, zDirection);
        var pitch is ValueWithUnits = pitchSize(context, definition);
        
        createCylinder(context, id, definition, othreadAxis, threadRad);
        createHelixCutter(context, id, definition, xDirection, zDirection, othreadAxis, threadRad, pitch);
        var cutPlane is array = [];
        var cutterSize = getVariable(context, "cutterSize");
        cutPlane = append(cutPlane, qCreatedBy(id + "helix1", EntityType.EDGE));
 ```
![Thread](https://user-images.githubusercontent.com/46547632/60761322-a9beb980-9ffa-11e9-9629-4548d5cfa08b.gif)
