if(ANDROID OR IOS)
  ocv_module_disable(gpu)
endif()

set(the_description "GPU-accelerated Computer Vision")

ocv_warnings_disable(CMAKE_CXX_FLAGS /wd4127 /wd4100 /wd4324 /wd4512 /wd4515 -Wundef -Wmissing-declarations -Wshadow -Wunused-parameter)

ocv_define_module(gpu opencv_calib3d opencv_objdetect opencv_gpuarithm opencv_gpuwarping OPTIONAL opencv_gpulegacy)

if(HAVE_CUDA)
  add_subdirectory(perf4au)
endif()
