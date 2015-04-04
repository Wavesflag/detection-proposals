Detection Proposals
===================

Evaluation of detection proposal algorithms. The code belongs to the BMVC paper **How good are detection proposals, really?** and an upcoming journal paper. Have a look at the [Project Page](http://www.mpi-inf.mpg.de/departments/computer-vision-and-multimodal-computing/research/object-recognition-and-scene-understanding/how-good-are-detection-proposals-really/) for more information.


Please contact me if you're having trouble with the code!


Plot evaluation curves
----------------------

1. Get the data that you want to use from the [Project Page](http://www.mpi-inf.mpg.de/departments/computer-vision-and-multimodal-computing/research/object-recognition-and-scene-understanding/how-good-are-detection-proposals-really/).
2. Edit `get_config.m` to point to the right locations for images, candidates and so on.
3. Make sure you either start matlab in the root directory of the code or run `startup.m` manually once.
4. Run `plot_recall_voc07.m`, curves will be in the figures subdirectory.


Benchmark your own method
-------------------------

1. Follow **Plot evaluation curves**.
2. Write a wrapper function that takes an image and the number of proposal boxes and returns the proposals and scores. Proposals are a nx4 matrix, where n is the number of proposals and every row has the format `[x1 y1 x2 y2]` (x and y are 1-based image coordinates). See `method_wrappers/` for examples.
2. Add your method to `shared/get_method_configs.m`
3. Run `compute_recall_candidates_voc07.m` passing only the config of your method as an argument. If your method is slow, you probably want to parallelize it in a cluster.
4. Run `plot_recall_voc07.m`, curves will be in the figures subdirectory.

You don't have to use `compute_recall_candidates_voc07.m`, but you can have a look to get an idea about how to save the candidates in the right format so, `plot_recall_voc07.m` will be able to read it.

