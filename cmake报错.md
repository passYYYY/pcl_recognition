global_hypothesis_verification.cpp
pcl版本1.8 
    GoHv.setResolution (hv_resolution_);
    // GoHv.setResolutionOccupancyGrid (hv_occupancy_grid_resolution_);注释掉此行
    GoHv.setInlierThreshold (hv_inlier_th_);
    GoHv.setOcclusionThreshold (hv_occlusion_th_);
    GoHv.setRegularizer (hv_regularizer_);
    GoHv.setRadiusClutter (hv_rad_clutter_);
    GoHv.setClutterRegularizer (hv_clutter_reg_);
    GoHv.setDetectClutter (hv_detect_clutter_);
    GoHv.setRadiusNormals (hv_rad_normals_);
    
    
implicit_shape_model.cpp
pcl::features::ISMVoteList<pcl::PointXYZ>Ptr 修改为
boost::shared_ptr<pcl::features::ISMVoteList<pcl::PointXYZ>> vote_list = ism.findObjects(
        model,
        testing_cloud,
        testing_normals,
        testing_class); 

对‘vtkRenderingOpenGL2_AutoInit_Destruct()’未定义的引用
    发现居然是cmakelists文件出了错误，结果很意外。object_recognition_kitchen没有target_link_lib
    target_link_libraries (object_recognition_kitchen object_recognizer ${PCL_LIBRARIES})
