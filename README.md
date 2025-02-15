Creates and returns a interactable sunburst plot and image display for tree structured data and brain images.

Parameters:

    - data_by_region: DataFrame which contains linking sunburst nodes to Z-slices. 
        This should contain atlas ontology information. Essential columns are 'id','parent_id','acronym','parent_acronym'. 
        The dataframe should be able to construct one hiearchical tree. 
        The dataframe can have data variables. This can be cell density, results of statistical analysis etc...
        The data variables can be specified by data_variable later.
    - data_by_img: 3D numpy array with float values. This can be effect size, normalized density etc.
    - annotated_atlas_img: 3D numpy array of the atlas with annotations.
    - outputpath: Directory to save exported figures.
    - atlas_df: DataFrame containing region information (with 'id' and 'name' columns). # not used anymore
    - colormap: Colormap used for image processing (default: plt.cm.coolwarm).
    - tree_node_names: Column name for the sunburst slice labels (default: 'acronym').
    - tree_node_parents: Column name for the sunburst parent relationships (default: 'parent_acronym').
    - data_variable: Column name for coloring the sunburst (default: 'rejected').
    - sunburst_continuous_scale: Colorscale list for continuous color. If None, defaults to viridis.
    - sunburst_range_color: Two-element list [vmin, vmax] to set the range for continuous color.



You can run the funcion like below

    import active_sunburst as sunburst    
    sunburst.run_app(data_by_region, data_by_img, annotated_atlas_img, outputpath, data_variable = 'normalized_density',sunburst_range_color = [0,2],colormap =  plt.cm.viridis)

It will generate something like this
![me](https://github.com/kenjp1223/Sunburst-Wholebrain/blob/main/demo-interactive-plotting.gif)
