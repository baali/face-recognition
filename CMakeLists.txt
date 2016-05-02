cmake_minimum_required(VERSION 2.8)
project( FaceRecognition )
find_package( OpenCV REQUIRED )

add_executable( imgCapture src/face_train.cpp )
target_link_libraries( imgCapture ${OpenCV_LIBS} )

add_executable(facerec_demo src/facerec_demo.cpp)
target_link_libraries(facerec_demo opencv_core opencv_face opencv_imgproc opencv_highgui)

add_executable(facerec_video src/facerec_video.cpp)
target_link_libraries(facerec_video opencv_face opencv_core opencv_imgproc opencv_highgui opencv_objdetect opencv_imgproc)
target_compile_features(facerec_video PRIVATE cxx_range_for)
